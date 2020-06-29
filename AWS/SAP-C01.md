# AWS Solutions Architect Professional 2020

## Description

A compilation of active notes. The goal was to actively listen and memorize while noting, so these aren't ideal for at-a-glance studying. 

[TOC]

## Identity and Federation

### IAM Roles

**Types**

- EC2 Instance
- Service Roles (API gateway, etc)
- Cross Account Roles

**Policies**

- AWS Managed
- Customer Managed
- Inline Policies

**Caveats**

Deny overrides allow. Use Effect: Allow and NotAction to work around.

#### Conditions

**Syntax**

```
"Condition" : { "{condition-operator}" : { "{condition-key}" : "{condition-value}" }}
```

**Operators**

```
• String (StringEquals, StringNotEquals, StringLike...)
    • "Condition": {"StringEquals": {"aws:PrincipalTag/job-category": "iamuser-admin"}}
    • "Condition": {"StringLike": {"s3:prefix": [ "", "home/", "home/${aws:username}/" ]}}
• Numeric (NumericEquals, NumericNotEquals, NumericLessThan...)
• Date (DateEquals, DateNotEquals, DateLessThan...)
• Boolean (Bool):
    • “Condition": {"Bool": {"aws:SecureTransport": "true"}}
    • "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}}
• (Not)IpAddress:
    • "Condition": {"IpAddress": {"aws:SourceIp": "203.0.113.0/24"}}
• ArnEquals, ArnLike
    • Null: "Condition":{"Null":{"aws:TokenIssueTime":"true"}}
```

#### Policies and Tags

```json
Example: ${aws:username}
    "Resource":["arn:aws:s3:::mybucket/${aws:username}/*"]
AWS Specific:
    • aws:CurrentTime, aws:TokenIssueTime, aws:principaltype, aws:SecureTransport,             aws:SourceIp, aws:userid, ec2:SourceInstanceARN
Service Specific:
    • s3:prefix, s3:max-keys, s3:x-amz-acl, sns:Endpoint, sns:Protocol...
Tag Based:
    • iam:ResourceTag/key-name, aws:PrincipalTag/key-name...
```

**Username**

```
"Resource":["arn:aws:s3:::mybucket/${aws:username}/*"]
```

**AWS Specific**

```
aws:CurrentTime, aws:TokenIssueTime, aws:principaltype, aws:SecureTransport, aws:SourceIp, aws:userid, ec2:SourceInstanceARN
```

**Service Specific**

```json
s3:prefix, s3:max-keys, s3:x-amz-acl, sns:Endpoint, sns:Protocol...
```

**Tag Based**

```
iam:ResourceTag/key-name, aws:PrincipalTag/key-name...
```

#### IAM Roles vs Resource Based Policies

**Principal Role**

The Role assumed overrides any previous roles or permissions of the user, application, or service. 

**Resource Based Policy**

The prinicpal doesn't require any previous permissions.

------

## Security Token Service (STS)

### Overview

- Temporary security credentials
- Uses AssumeRole API
- Can switch roles within AWS accounts that you own
- Use IAM Access Analyzer

### STS APIs

| API                       | Description                                               |
| ------------------------- | --------------------------------------------------------- |
| AssumeRole                | Internal/cross-account.                                   |
| AssumeRoleWithSAML        | Same via SAML.                                            |
| AssumeRoleWithWebIdentity | via  IdP federation or Congnito federation (recommended). |
| GetSessionToken           | for MFA.                                                  |
| GetFederationToken        | temporary credentials for a federated user.               |

### Cross Account Access

**First-Party Cross Account Access**

Suppose you have two Accounts, Production and Development, and wish to grant development users access to a resource. This is ***inside your*** ***Zone of Trust.***

1. **On production account: ** Create a role that grants developer account access.
2. **On Development account**: Grant a group or users permission to assume the role.

**Third-Party Cross Account Access**

Suppose you hire a consulting group and would like them to be able to access resources but don't want to manage an additional IAM user. This is ***outside the Zone of Trust.***

**Requires:**

- 3rd Party AWS Account ID
- An External ID (unique, secret, and chosen by third party)
  - Unique
  - Secret between your account and third-party account.
  - Chosen by third party.
  - Prevents "Confused deputy" attacks and issues.
- Define permissions in IAM policy.

**Process:**

1. Account A provides role to Account B.
2. Account B assumes role using the External ID.

------

### Identity Federation

Allows users outside of AWS to assume temprary roles for accessing AWS resources. This eliminates the need of creating and managing IAM users.

#### Methods

- SAML 2.0
- Custom Identity Broker
- Web Identity Federation (with or without Cognito)
- SSO
- Non-SAML with AWS Microsoft AD

#### SAML 2.0 Federation

- Integrate AD/ADFS with AWS
- Provides access to AWS Console/CLI
- Enables web-based cross-domain SSO
- Uses AssumeRoleWithSAML API
- Federation through SAML is on it's way out

**Process**

![           Getting temporary security credentials based on a SAML assertion         ](./assets/saml-based-federation.diagram.png)

This example uses an app.

1. Client app makes request to IdP
2. IdP Authenticates user
3. Idp sends client SAML assertion
4. App calls AssumeRoleWithSAML (STS)
5. STS returns temporary credentials
6. App uses credentialls to access AWS resources

**Process - ADFS**

This example is for Console access and does not use an application.

![img](./assets/federated_auth_with_adfs_25.dc86ecbfbbf80af3f553e7374d2a55ad1afb7016.png)

1. User logs into portal via browser.
2. AD Identity Store authenticates user
3. Browser recieves SAML assertion
4. Browser posts SAML assertion to STS
5. STS returns credentials
6. Redirected to AWS Console

#### Custom Identity Broker

- Use *only if identity provider is not compatible with SAML 2.0*
- Identity broker determines the appropriate IAM policy
- Uses AssumeRole or GetFederationToken APIs.

**Process**

![Sample workflow using a custom identity broker application](./assets/enterprise-authentication-with-identity-broker-application.diagram.png)

1. User accesses Identity Broker
2. Identity broker authenticates user with the Corporate Identity Store.
3. Identity broker retrieves credentials from STS.
4. Browser/App recieves access to AWS APIs and is redirected to the AWS console.

#### Web Identity Federation - AssumeRoleWithWebIdentity

Remember, this is not recommended by AWS.

**Process**

![img](./assets/wif-overview.png)

#### Web Identity Federation - Cognito

- Preferred way for WIF
- Cognito:
  - Supports anonymous users
  - Supports MFA
  - Data synchronization

**Process**

![       Sample workflow using Amazon Cognito to federate users for a mobile application     ](./assets/mobile-app-web-identity-federation.diagram.png)

1. A customer starts app
2. Redirects to Login with Amazon and recieves an ID token
3. App uses Cognito to exchange ID token for Cognito token
4. App uses STS to exchange Cognito token for AWS credentials
5. Appp uses credentials to access AWS resources

**IAM Policy**

IAM Policies can identify users via IAM policy variables.

- cognito-identity.amazonaws.com:sub
- www.amazon.com:user_id
- graph.facebook.com:id
- accounts.google.com:sub

```json
"Condition": {"StringLike": {"s3:prefix": ["Amazon/appname/${www.amazon.com"iser_id}/*"]}}
```

#### Active Directory Federation Services

Similar to previous Identity Federation Providers, but ADFS is privately managed by the business or corporation. 

**Process**

![img](./assets/PierreLiddle-Diagram-072917-a.jpg)

1. User browses to URL with ADFS authentication
2. ADFS authenticates user with Active Directory
3. The browser recieves an AuthN response
4. Browser sends POST to AWS, passing the AuthN response
5. Browser is redirected to Console

------

### AWS Directory Services

**Active Directory Primer:**

- Central database of objects, users, computers, file shares, and security groups
- Central security, account, and permission management
- Objects organized in *trees*; groups of objects called *forests*.

**Overview**

| Service                  | Description                                             |
| ------------------------ | ------------------------------------------------------- |
| AWS Managed Microsoft AD | AD in VPC. Standalone or joined with on-prem AD.        |
| AD Connector             | Gateway to redirect to on-prem AD.                      |
| Simple AD                | AD-compatible directory. Cannot be joined with on-prem. |

#### AWS Managed Microsoft AD

Come back

####Simple AD

It may be apparent that the benefits of AWS Managed Microsoft AD are outweighed by the cost when it's not connected to the on-prem AD. In many less complex and demanding cases Simple AD may be what you're looking for. 

| Supports                                                | Doesn't Support                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------- |
| [SAMBA 4](https://www.samba.org/)                       | MFA                                                                   |
| EC2 (Linux or Windows)                                  | trust relationships                                                   |
| [Quicksight](https://aws.amazon.com/quicksight/)        | DNS dynamic update                                                    |
| [AWS SSO](https://aws.amazon.com/single-sign-on/)       | schema extensions                                                     |
| [Amazon WorkSpaces](https://aws.amazon.com/workspaces/) | LDAPS (secure LDAP)                                                   |
| [Amazon WorkDocs](https://aws.amazon.com/workdocs/)     | PowerShell AD cmdlets                                                 |
| [Amazon Chime](https://aws.amazon.com/chime/)           | FSMO role transfer                                                    |
| Kerberos                                                | [RDS for Microsoft SQL Server](https://aws.amazon.com/rds/sqlserver/) |
| Group Policies                                          |                                                                       |

#### AD Connector

AD Connector is used to *forward Active Directory authentication requests* to your on-prem Domain Controllers. The features it enables is very similar to AWS Managed Microsoft AD. 

| What it does                                                                                                             | What it doesn't do                                          |
| ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| [MFA](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ad_connector_mfa.html)                             | Caching users                                               |
| [EC2 (Windows)](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ad_connector_join_windows_instance.html) | Manage users                                                |
| [Workspaces](https://aws.amazon.com/workspaces/)                                                                         | Utilize forest trusts                                       |
| [WorkDocs](https://aws.amazon.com/workdocs/)                                                                             |                                                             |
| [WorkMail](https://aws.amazon.com/workmail/)                                                                             | [RDS for SQL Server](https://aws.amazon.com/rds/sqlserver/) |
| [QuickSight](https://aws.amazon.com/quicksight/)                                                                         |                                                             |
| [Chime](https://aws.amazon.com/chime/)                                                                                   |                                                             |
| [Connect](https://aws.amazon.com/connect/)                                                                               |                                                             |

#### Connecting AWS Managed AD to on-prem AD

If you don't use AD Connector to connect on-prem AD to AWS Managed Microsoft AD, what do you use? Well, that needs to be done via VPN or DX (Direct Connect). It's important to understand that you are creating a ***forest trust*** and not simply replicating your on-prem AD to AWS Managed Microsoft AD. For example: 

* Office forest: chicago.ad.contoso.com
* AWS forest: aws.ad.contoso.com

**Forest Trust Types**

* One-way AWS => On-Prem

* One-way On-Prem => AWS

* Two-way AWS <==> On-Prem

#### Solution Architecture: Active Directory Replication

Having your application infrastructure depend on a single point of failure (DX or VPN connection) isn't exactly resilient. An AD Replication can help minimize the risk in this case. Because you can't replicate directly to AWS Managed Microsoft AD you will instead create an EC2 instance to act as the replica of your on-prem AD, then establish the forest trust between the EC2 replica and AWS Managed Microsoft AD.

![image-20200602165334583](assets/image-20200602165334583.png)

#### Resources

[Which Directory Service to choose?](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html)

[AWS Managed Microsoft AD Administration Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/directory_microsoft_ad.html)

[Active Directory Connector Administration Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/directory_ad_connector.html)

[Simple AD Administration Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/directory_simple_ad.html)

## AWS Organizations

## AWS Resource Access Manager - RAM

## AWS SSO

****

## Practice Exams

| Name                                                               | Author    | Link                                                                                                                                                                                  |
| ------------------------------------------------------------------ | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AWS Certified Solutions Architect Professional Practice Exams 2020 | Jon Bonso | [Udemy](https://www.udemy.com/share/102yrMAkIdd1dRRHw=/)<br/>[TutorialsDojo](https://portal.tutorialsdojo.com/courses/aws-certified-solutions-architect-professional-practice-exams/) |



## Best Practices

| Service                    | Resource                                                                                                        |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- |
| AWS Managed Microsoft AD   | [Admin Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ms_ad_best_practices.html)        |
| Active Directory Connector | [Admin Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ad_connector_best_practices.html) |
| Simple AD                  | [Admin Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/simple_ad_best_practices.html)    |

## Labs and Tutorials

| Service                    | Resource                                                                                                                                                                                                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| AWS Managed Microsoft AD   | [Set up Test Lab](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ms_ad_tutorial_test_lab_base.html)<br/>[Create a Trust between AWS AD and on-prem](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ms_ad_tutorial_test_lab_trust.html) |
| Active Directory Connector | [Admin Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ad_connector_best_practices.html)                                                                                                                                                          |
| Simple AD                  | [Create a Simple AD](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/simple_ad_tutorial_create.html)                                                                                                                                                     |