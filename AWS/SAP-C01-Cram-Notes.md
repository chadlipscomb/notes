# Exam Studies



## Networking

- Egress-Only IG id IPv6 only.
- The first 3 IP addresses of any private subnet is reserved for AWS.
- Only ALB and NLB support EIP.
- VPC's can resolve using on-prem DNS via DHCP option sets.
- NAT Gateways don't use SGs.
- Ephemeral ports are required to allow the server to communicate back to the client.
- DX is not highly available. [Link](https://docs.aws.amazon.com/directconnect/latest/UserGuide/getting_started.html)
- 



# Weaknesses

ECS - everything

DocumentDB

Blockchain

CloudFormation

Migration Strategies

RDS vs DynamoDB
Transit Gateway vs Direct Connect. Interregion vpc peering





https://d1.awsstatic.com/whitepapers/Security/DDoS_White_Paper.pdf

# S3

Requestor Pays can be set to have requestors pay transfer costs for buckets. Requires authentication.



# CloudFormation

### Resource Specification

### Resource Attributes

#### Creation Policy

#### DeletionPolicy

[DeletionPolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-deletionpolicy.html)

Policy that decides what happens when a stack is deleted

**Options**

| Option   | Description                                                  |
| -------- | ------------------------------------------------------------ |
| delete   | Deletes the resources and all contents. Default for all resources except RDS instances and clusters. S3 buckets must also be empty for the deletion to succeed. |
| snapshot | Creates a snapshot before deleting it. Compatible with EC2, ElastiCache, Neptune, RDS, and Redshift. |
| retain   | Keeps the resources after deletion. Consider for S3 buckets. |

#### DependsOn

#### Metadata

#### UpdatePolicy

#### UpdateReplacePolicy

# Storage Gateway

File Gateway - S3 u

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#TXTFormat)

# Route53

- Does not support DNSSEC.
- Alias records point directly to an AWS resource.
- 

#### Routing Policies

| Policy       | Use Case                                                     |
| ------------ | ------------------------------------------------------------ |
| Simple       | Routes to a single resource.                                 |
| Failover     | [Active-passive](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-types.html#dns-failover-types-active-passive) failover. |
| Geolocation  | Route based on location of ***users.***                      |
| Geoproximity | Route based on location of ***resources.***                  |
| Latency      | Route based on latency of resources.                         |
| Multivalue   | Random.                                                      |
| Weighted     | Proportional. E.g. 30/70% split.                             |

#### Supported DNS Records

| Type                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [A](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#AFormat) | Route to a single ***IPv4 resource***.                       |
| [AAAA](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#AAAAFormat) | Route to a single ***IPv6 resource***.                       |
| [CAA](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#CAAFormat) | Specifies ***authorized Certificate Authorities***.          |
| [CNAME](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#CNAMEFormat) | Route to ***another domain or subdomain.***                  |
| [MX](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#MXFormat) | Specifies ***mail server(s)***.                              |
| [NAPTR](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#NAPTRFormat) | Name Authority Pointer. Use Regex to ***convert one value into another***. |
| [NS](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#NSFormat) | Identifies ***name servers*** for the hosted zone. E.g. AWS's or GoDaddy. |
| [PTR](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#PTRFormat) | ***Resolves*** an ***IPv4 resource to a name***. Opposite of A. |
| [SOA](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#SOAFormat) | Start of Authority. Provides information about a domain.     |
| [SPF](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#SPFFormat) | Identify the sender of emails. Replaced by TXT.              |
| [SRV](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#SRVFormat) | Specifies host and port for services.                        |
| [TXT](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html#TXTFormat) | Associate text with a domain. Used for ownership verification. |



## Schema Conversion Tool

### Database Conversions

| Source Database                                         | Target Database on Amazon RDS                                |
| :------------------------------------------------------ | :----------------------------------------------------------- |
| Microsoft SQL Server (version 2008 and later)           | Amazon Aurora, MariaDB 10.2 and 10.3, Microsoft SQL Server, MySQL, PostgreSQL |
| MySQL (version 5.5 and later)                           | Aurora, MySQL, PostgreSQL. [Aurora MySQL not necessary](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Migrate.html). |
| Oracle (version 10.2 and later)                         | Aurora, MariaDB, MySQL, Oracle, PostgreSQL                   |
| PostgreSQL (version 9.1 and later)                      | Aurora MySQL, MySQL, PostgreSQL. *Not Aurora PostgreSQL*     |
| IBM Db2 LUW (versions 9.1, 9.5, 9.7, 10.5, and 11.1)    | Aurora, MySQL, PostgreSQL, MariaDB                           |
| Apache Cassandra (versions 2.0, 3.0, 3.1.1, and 3.11.2) | Amazon DynamoDB                                              |
| Sybase (16.0 and 15.7)                                  | Aurora, MySQL, PostgreSQL                                    |

### Warehouse Conversions

| Source Database                               | Target Database on Amazon Redshift |
| :-------------------------------------------- | :--------------------------------- |
| Greenplum Database (version 4.3 and later)    | Amazon Redshift                    |
| Microsoft SQL Server (version 2008 and later) | Amazon Redshift                    |
| Netezza (version 7.0.3 and later)             | Amazon Redshift                    |
| Oracle (version 10 and later)                 | Amazon Redshift                    |
| Teradata (version 13 and later)               | Amazon Redshift                    |
| Vertica (version 7.2.2 and later)             | Amazon Redshift                    |



