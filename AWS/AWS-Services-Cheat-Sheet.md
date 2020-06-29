## AWS Service Cheat Sheet

### Description

A complete list and **brief** description of all AWS services available in [AWS Documentation](https://docs.aws.amazon.com/) *(as of 05/2020)*. I found many similar lists but they contained incorrect information, so it became necessary to compile a new one from scratch. The groupings and ordering is consistent with official AWS documentation.

------

[TOC]

------

### Compute

| Service                                                                                                        | Description                                                                    |
| -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [EC2](https://docs.aws.amazon.com/ec2/?id=docs_gateway)                                                        | Virtual machines.                                                              |
| [Batch](https://docs.aws.amazon.com/batch/?id=docs_gateway)                                                    | Provisions compute resources in response to job submissions.                   |
| [Elastic Beanstalk](https://docs.aws.amazon.com/elastic-beanstalk/?id=docs_gateway)                            | Upload code, then EB automatically provisions, scales, and balances resources. |
| [EC2 Image Builder](https://docs.aws.amazon.com/imagebuilder/?id=docs_gateway)                                 | Automate the management of golden images.                                      |
| [Lambda](https://docs.aws.amazon.com/lambda/?id=docs_gateway)                                                  | Serverless functions triggered by HTTP events or timers.                       |
| [Launch Wizard](https://docs.aws.amazon.com/launchwizard/?id=docs_gateway)                                     | Interactive guidance for application deployment.                               |
| [Lightsail](https://docs.aws.amazon.com/lightsail/?id=docs_gateway)                                            | One-click deployment app and development stacks.                               |
| [ Outposts](https://docs.aws.amazon.com/outposts/?id=docs_gateway)                                             | Extends AWS services on-prem.                                                  |
| [ParallelCluster](https://docs.aws.amazon.com/parallelcluster/?id=docs_gateway)                                | Manage high performance computing clusters                                     |
| [SAM](https://docs.aws.amazon.com/serverless-application-model/?id=docs_gateway)                               | *Serverless Application Model* - framework for serverless applications.        |
| [Serverless Application Repository](https://docs.aws.amazon.com/serverless-application-model/?id=docs_gateway) | Repository for serverless architectures.                                       |

------

### Containers

| Service                                                 | Description                                                                           |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| [ECR](https://docs.aws.amazon.com/ecr/?id=docs_gateway) | *Elastic Container Registry* - Managed Docker container storage and management.       |
| [ECS](https://docs.aws.amazon.com/ecs/?id=docs_gateway) | *Elastic Container Service* - Run containers on EC2 (unmanaged) or Fargate (managed). |
| [EKS](https://docs.aws.amazon.com/eks/?id=docs_gateway) | *Elastic Kubernetes Service* - Manged Kubernetes as a service.                        |

------

### Storage

| Service                                                                        | Description                                                                        |
|:------------------------------------------------------------------------------ |:---------------------------------------------------------------------------------- |
| [S3](https://docs.aws.amazon.com/s3/?id=docs_gateway)                          | Object storage system.                                                             |
| [EBS](https://docs.aws.amazon.com/ebs/?id=docs_gateway)                        | Block-level storage for EC2                                                        |
| [EFS](https://docs.aws.amazon.com/efs/?id=docs_gateway)                        | Like NFS, can be mounted in EC2 or remotely. Linux only.                           |
| [FSx](https://docs.aws.amazon.com/fsx/?id=docs_gateway)                        | Windows and Lustre file system support.                                            |
| [S3 Glacier](https://docs.aws.amazon.com/glacier/?id=docs_gateway)             | Lowest cost storage, but with high retreval times and costs.                       |
| [Snowball](https://docs.aws.amazon.com/snowball/?id=docs_gateway)              | Physical storage for transfer of Tb or PB between on-prem and AWS.                 |
| [Storage Gateway](https://docs.aws.amazon.com/storagegateway/?id=docs_gateway) | Integrate on-prem and AWS storage for simplicity, performance, and cost reduction. |
| [Backup](https://docs.aws.amazon.com/aws-backup/?id=docs_gateway)              | Manged backup service for AWS and on-prem.                                         |

------

### Database

| Service                                                                           | Description                                                           |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/index.html) | Part of RDS, SQL and PostgreSQL compatible with 3x-5x the throughput. |
| [DocumentDB](https://docs.aws.amazon.com/documentdb/?id=docs_gateway)             | MongodDB compatible databases.                                        |
| [DynamoDB](https://docs.aws.amazon.com/dynamodb/?id=docs_gateway)                 | Managed seamlessly scalable NoSQL database services.                  |
| [ElastiCache](https://docs.aws.amazon.com/elasticache/?id=docs_gateway)           | Memcache and redis in-memory cache management.                        |
| [Keyspaces](https://docs.aws.amazon.com/keyspaces/?id=docs_gateway)               | Managed Apache Cassandra-compatible database.                         |
| [Neptune](https://docs.aws.amazon.com/neptune/?id=docs_gateway)                   | High performance graph database.                                      |
| [QLDB](https://docs.aws.amazon.com/qldb/?id=docs_gateway)                         | Fully managed quantum ledger database. Great for transactions.        |
| [RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/index.html)          | Scalable relational database services. Think SQL.                     |
| [Redshift](https://docs.aws.amazon.com/redshift/?id=docs_gateway)                 | PB scale data warehousing.                                            |

------

### Security, Identity, & Compliance

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [IAM](https://docs.aws.amazon.com/iam/?id=docs_gateway)      | *Identity & Access Management* - Control access to AWS resources. |
| [Artifact](https://docs.aws.amazon.com/artifact/?id=docs_gateway) | AWS security and compliance documents. E.g. SOC reports.     |
| [Cognito](https://docs.aws.amazon.com/cognito/?id=docs_gateway) | User authentication and authorization for apps. Easy federation. |
| [Detective](https://docs.aws.amazon.com/detective/?id=docs_gateway) | Collects logs and helps identify suspicious activities. Uses ML. |
| [Directory Service](https://docs.aws.amazon.com/directory-service/?id=docs_gateway) | Integrate Cloud Directory, Cognito, and AD DS with other AWS services. |
| [Firewall Manager](https://docs.aws.amazon.com/firewall-manager/?id=docs_gateway) | WAF administration across accounts and resources.            |
| [Cloud Directory](https://docs.aws.amazon.com/clouddirectory/?id=docs_gateway) | ?                                                            |
| [GuardDuty](https://docs.aws.amazon.com/guardduty/?id=docs_gateway) | Continuous security monitoring.                              |
| [Inspector](https://docs.aws.amazon.com/inspector/?id=docs_gateway) | Assesses resources for known vulnerabilities and best practice deviations. |
| [Macie](https://docs.aws.amazon.com/macie/?id=docs_gateway)  | Uses ML to help ***discover and protect*** sensitive data.   |
| [RAM](https://docs.aws.amazon.com/ram/?id=docs_gateway)      | *Resource Access Manager* - Share AWS resources with AWS accounts and organizations. |
| [Resource Groups](https://docs.aws.amazon.com/ARG/?id=docs_gateway) | Organize resources into groups for management.               |
| [Secrets Manager](https://docs.aws.amazon.com/secretsmanager/?id=docs_gateway) | Secrets key/value store. Can automatically rotate secrets.   |
| [Security Hub](https://docs.aws.amazon.com/securityhub/?id=docs_gateway) | Overview of security state across AWS resources, accounts, and third-party products. |
| [Shield](https://docs.aws.amazon.com/shield/?id=docs_gateway) | ***DDoS protection***. Standard included in WAF, Advanced at extra cost. |
| [Single Sign-On](https://docs.aws.amazon.com/singlesignon/?id=docs_gateway) | SSO portal where users can find assigned AWS accounts and applications. |
| [Tag Editor](https://docs.aws.amazon.com/ARG/latest/userguide/tag-editor.html?id=docs_gateway) | Words or phrases that act as metadata for identifying and organizing your AWS resources |
| [WAF](https://docs.aws.amazon.com/waf/?id=docs_gateway)      | Web Application Firewall.                                    |

------

### Cryptography & PKI

| Service                                                                                | Description                                                             |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [Cryptographic Services Overview](https://docs.aws.amazon.com/crypto/?id=docs_gateway) | Quick intro to crpytographic services.                                  |
| [PKI Services Overview](https://docs.aws.amazon.com/crypto/?id=docs_gateway)           | Quick intro to Private Key Infrastructure.                              |
| [CloudHSM](https://docs.aws.amazon.com/cloudhsm/?id=docs_gateway)                      | Hardware security modules for secure crpyto key generation.             |
| [KMS](https://docs.aws.amazon.com/kms/?id=docs_gateway)                                | Key Management Service - Manage secret keys securely.                   |
| [Certificate Manager](https://docs.aws.amazon.com/acm/?id=docs_gateway)                | Create and manage SSL/TLS certificates on AWS managed resources. (FREE) |

------

### Machine Learning (ML)

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [SageMaker](https://docs.aws.amazon.com/sagemaker/?id=docs_gateway) | Fully managed ML. Train models and deploy.                   |
| [Augmented AI (A2I)](https://docs.aws.amazon.com/augmented-ai/?id=docs_gateway) | Human review of machine learning predictions.                |
| [CodeGuru](https://docs.aws.amazon.com/codeguru/?id=docs_gateway) | Uses ML to assess JVM code for performance and defects.      |
| [CodeGuru Profiler](https://docs.aws.amazon.com/codeguru/latest/profiler-ug/index.html) | Collects performance data and provides recommendations using ML. |
| [CodeGuru Reviewer](https://docs.aws.amazon.com/codeguru/latest/reviewer-ug/index.html) | Detects potential defects in Java code using ML.             |
| [Comprehend](https://docs.aws.amazon.com/comprehend/?id=docs_gateway) | Uses natural language processing (NLP) to extract insights about documents. |
| [Elastic Inference](https://docs.aws.amazon.com/elastic-inference/?id=docs_gateway) | Low-cost GPU acceleration with support for TensorFlow, Apache MXNet, and ONNX |
| [Forecast](https://docs.aws.amazon.com/forecast/?id=docs_gateway) | Analyzes historical time-series data to forcast future points. |
| [Fraud Detector](https://docs.aws.amazon.com/frauddetector/?id=docs_gateway) | Fully managed detection of fake accounts and payment fraud   |
| [Kendra](https://docs.aws.amazon.com/kendra/?id=docs_gateway) | Search unstructured text using natural language.             |
| [Lex](https://docs.aws.amazon.com/lex/?id=docs_gateway)      | Build natural language voice and text chatbots.              |
| [Personalize](https://docs.aws.amazon.com/personalize/?id=docs_gateway) | Real-time personalized recommendations. Used on Amazon.com.  |
| [Polly](https://docs.aws.amazon.com/polly/?id=docs_gateway)  | Multilingual, lifelike TTS (text-to-speech)                  |
| [Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html) | Object, people, text, scene, activity recognition for images and video. |
| [Textract](https://docs.aws.amazon.com/textract/?id=docs_gateway) | OCR API.                                                     |
| [Translate](https://docs.aws.amazon.com/translate/?id=docs_gateway) | Text language translation.                                   |
| [Transcribe](https://docs.aws.amazon.com/transcribe/?id=docs_gateway) | Audio transcription                                          |
| [Deep Learning AMIs](https://docs.aws.amazon.com/dlami/?id=docs_gateway) | Machine images for deep learning practitioners and researchers. |
| [Deep Learning Containers](https://docs.aws.amazon.com/deep-learning-containers/?id=docs_gateway) | Docker images for deep learning practitioners and researchers. |
| [DeepComposer](https://docs.aws.amazon.com/deepcomposer/latest/devguide/what-it-is.html) | Physical ML-enabled musical keyboard.                        |
| [DeepLens](https://docs.aws.amazon.com/deeplens/?id=docs_gateway) | SDK for computer vision - includes hardware.                 |
| [DeepRacer](https://docs.aws.amazon.com/deepracer/?id=docs_gateway) | Autonomous 1/18th scale race car challenge often at AWS events. |
| [Apache MXNet](https://docs.aws.amazon.com/mxnet/?id=docs_gateway) | Open source framework to define, train, and deploy deep neural networks |

------

### Management & Governance

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Auto Scaling](https://docs.aws.amazon.com/autoscaling/?id=docs_gateway) | Scale Aurora, DynamoDB, EC2, and ECS based on rules and triggers. |
| [Chatbot](https://docs.aws.amazon.com/chatbot/?id=docs_gateway) | Process SNS notifcations to Slack or Chime.                  |
| [CloudFormation](https://docs.aws.amazon.com/cloudformation/?id=docs_gateway) | Automate infrastructure deployments.                         |
| [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) | Trace API calls to users or IP.                              |
| [CloudWatch](https://docs.aws.amazon.com/cloudwatch/?id=docs_gateway) | Monitor resources and applications in real-time.             |
| [Command Line Interface ( CLI)](https://docs.aws.amazon.com/cli/?id=docs_gateway) | Self explainitory                                            |
| [Compute Optimizer](https://docs.aws.amazon.com/compute-optimizer/?id=docs_gateway) | Uses ML to recommend Compute cost reduction measures.        |
| [Config](https://docs.aws.amazon.com/config/?id=docs_gateway) | Maps resource configurations and relationships. Tracks changes. |
| [Control Tower](https://docs.aws.amazon.com/controltower/?id=docs_gateway) | Cross-account governmance.                                   |
| [Data Lifecycle Manager](https://docs.aws.amazon.com/dlm/?id=docs_gateway) | Manage lifecycle of resources.                               |
| [Health](https://docs.aws.amazon.com/health/?id=docs_gateway) | Personalized info affecting your infrastructure.             |
| [License Manager](https://docs.aws.amazon.com/license-manager/?id=docs_gateway) | Manage BYOL                                                  |
| [Management Console](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html?id=docs_gateway) | Web GUI for management. Quit not if you didn't know that.    |
| [OpsWorks](https://docs.aws.amazon.com/opsworks/?id=docs_gateway) | Configuration management via Chef or Puppet.                 |
| [Organizations](https://docs.aws.amazon.com/organizations/?id=docs_gateway) | Consolidate and manage multiple accounts.                    |
| [Service Catalog](https://docs.aws.amazon.com/servicecatalog/?id=docs_gateway) | Manage approved products to end-users.                       |
| [Service Quotas](https://docs.aws.amazon.com/servicequotas/?id=docs_gateway) | Virw/manage quotas as workloads grow.                        |
| [Systems Manaer](https://docs.aws.amazon.com/systems-manager/?id=docs_gateway) | Operations & Application Management, Actions & Change, Instances & Nodes, and Shared Resources. |
| [Tools for Powershell](https://docs.aws.amazon.com/powershell/?id=docs_gateway) | Powershell tools                                             |
| [Trusted Advisor](https://docs.aws.amazon.com/aws-support/?id=docs_gateway) | Checks for cost related issues                               |
| [Well-Architected Tool](https://docs.aws.amazon.com/wellarchitected/?id=docs_gateway) | Best practices guidance.                                     |

------

### Developer Tools

| Service                                                                   | Description                                                          |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [Cloud9](https://docs.aws.amazon.com/cloud9/?id=docs_gateway)             | IDE - write, run, and debug code.                                    |
| [CodeBuild](https://docs.aws.amazon.com/codebuild/?id=docs_gateway)       | Continuous integration. Compiles and tests code, produces artifacts. |
| [CodeCommit](https://docs.aws.amazon.com/codecommit/?id=docs_gateway)     | Git.                                                                 |
| [CodeDeploy](https://docs.aws.amazon.com/codedeploy/?id=docs_gateway)     | Automate deployment.                                                 |
| [CodePipeline](https://docs.aws.amazon.com/codepipeline/?id=docs_gateway) | Continuous delivery. Automate steps to release.                      |
| [CodeStar](https://docs.aws.amazon.com/codestar/?id=docs_gateway)         | Quickly develop and deploy using tamplate code.                      |
| [Tools & SDKs](https://aws.amazon.com/tools/?id=docs_gateway)             | Self explainitory.                                                   |
| [X-Ray](https://docs.aws.amazon.com/xray/?id=docs_gateway)                | Integrate tracing in applications.                                   |

------

### Migration & Transfer

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Application Discovery Service](https://docs.aws.amazon.com/application-discovery/?id=docs_gateway) | Automatically discovers applications and dependencies on-prem. |
| [Database Migration Service](https://docs.aws.amazon.com/dms/?id=docs_gateway) | Migrate relational DB from *anywhere* to RDS.                |
| [DataSync](https://docs.aws.amazon.com/datasync/?id=docs_gateway) | Sync data between on-prem and AWS.                           |
| [Migration Hub](https://docs.aws.amazon.com/migrationhub/?id=docs_gateway) | Tools to track migration.                                    |
| [Schema Conversion Tool (SCT)](https://docs.aws.amazon.com/SchemaConversionTool/latest/userguide/CHAP_Welcome.html) | Converts database schema and code for use with target.       |
| [SMS](https://docs.aws.amazon.com/server-migration-service/?id=docs_gateway) | *Server Migration Services* - tools and server replications <u>from</u> on-prem |
| [Snowball](https://docs.aws.amazon.com/snowball/?id=docs_gateway) | Physical storage to transfer TB or PB of data.               |
| [Transfer Family](https://docs.aws.amazon.com/transfer/?id=docs_gateway) | FTP, SFTP, FTPS to S3 backend.                               |

------

### Networking & Content Delivery

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [API Gateway](https://docs.aws.amazon.com/apigateway/?id=docs_gateway) | Create scaleable REST and WebSocket APIs                     |
| [App Mesh](https://docs.aws.amazon.com/app-mesh/?id=docs_gateway) | Monitor and control microservices.                           |
| [Cloud Map](https://docs.aws.amazon.com/cloud-map/?id=docs_gateway) | Name and discover AWS resources.                             |
| [CloudFront](https://docs.aws.amazon.com/cloudfront/?id=docs_gateway) | CDN. Distributes content. Not a load balancer or router.     |
| [Direct Connect](https://docs.aws.amazon.com/directconnect/?id=docs_gateway) | Bypass ISP and connect directly to AWS.                      |
| [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/?id=docs_gateway) | Distribute incoming application traffic across multiple targets. |
| [Global Accelerator](https://docs.aws.amazon.com/global-accelerator/?id=docs_gateway) | Run applications on edge locations (CDN)                     |
| [Route 53](https://docs.aws.amazon.com/route53/?id=docs_gateway) | DNS with unique features.                                    |
| [VPC](https://docs.aws.amazon.com/vpc/?id=docs_gateway)      | Virtual network for AWS resources. Not just EC2.             |
| [VPN](https://docs.aws.amazon.com/vpn/?id=docs_gateway)      | Private tunnel to AWS. Does not bypass ISP.                  |

------

### Media Services

| Service                                                                                               | Description                                                             |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [Elastic Transcoder](https://docs.aws.amazon.com/elastic-transcoder/?id=docs_gateway)                 | Convert media in S3                                                     |
| [Elemental MediaConnect](https://docs.aws.amazon.com/mediaconnect/?id=docs_gateway)                   | Transport service for live video.                                       |
| [Elemental MediaConvert](https://docs.aws.amazon.com/mediaconvert/?id=docs_gateway)                   | Trancode offline video content for on-demand delivery.                  |
| [Elemental MediaLive](https://docs.aws.amazon.com/medialive/?id=docs_gateway)                         | Live outputs for streaming.                                             |
| [Elemental MediaPackage](https://docs.aws.amazon.com/mediapackage/?id=docs_gateway)                   | Just-in-time packaging of video streams. VOD, live-to-VOD, catch-up TV. |
| [Elemental MediaStore](https://docs.aws.amazon.com/mediastore/?id=docs_gateway)                       | High performance video object storage and asset management.             |
| [Elemental MediaTailor](https://docs.aws.amazon.com/mediatailor/?id=docs_gateway)                     | Server-side ad insertion.                                               |
| [Elemental Appliances & Software](https://docs.aws.amazon.com/elemental-on-premises/?id=docs_gateway) | Encode and package videon on-prem.                                      |

------

### Internet of Things (IoT)

| Service                                                                                     | Description                                                                |
| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [IoT Core](https://docs.aws.amazon.com/iot/?id=docs_gateway)                                | Communication between IoT and AWS via MQTT and HTTP.                       |
| [FreeRTOS](https://docs.aws.amazon.com/freertos/?id=docs_gateway)                           | Open source OS for microcontrollers.                                       |
| [IoT Analytics](https://docs.aws.amazon.com/iotanalytics/?id=docs_gateway)                  | Collect, process and store IoT data.                                       |
| [IoT Device Defender](https://docs.aws.amazon.com/iot-device-defender/?id=docs_gateway)     | Audit configs, monitor devices, and mitigate security risks.               |
| [IoT Device Management](https://docs.aws.amazon.com/iot-device-management/?id=docs_gateway) | Remotely manage IoT device inventory, configurations, and updates.         |
| [IoT Events](https://docs.aws.amazon.com/iotevents/?id=docs_gateway)                        | Monitor devices and set trigger actions.                                   |
| [IoT Greengrass](https://docs.aws.amazon.com/greengrass/?id=docs_gateway)                   | AWS services locally, ensuring operation during intermittent connectivity. |
| [IoT SiteWise](https://docs.aws.amazon.com/iot-sitewise/?id=docs_gateway)                   | Collect, organize, and analyze data from industrial equipment at scale.    |
| [IoT Things Graph](https://docs.aws.amazon.com/thingsgraph/?id=docs_gateway)                | Tools to translate communication standards/protocols to work with AWS.     |
| [IoT 1-Click](https://docs.aws.amazon.com/iot-1-click/?id=docs_gateway)                     | Trigger Lambda functions via simple physical devices.                      |

------

### Mobile

| Service                                                                | Description                                                                        |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [Amplify](https://docs.aws.amazon.com/amplify/?id=docs_gateway)        | Framework that provides continuous delivery and hosting for web apps.              |
| [AppSync](https://docs.aws.amazon.com/appsync/?id=docs_gateway)        | Managed GraphQL API service.                                                       |
| [Device Farm](https://docs.aws.amazon.com/devicefarm/?id=docs_gateway) | App testing service on physical devices hosted by AWS.                             |
| [Pinpoint](https://docs.aws.amazon.com/pinpoint/?id=docs_gateway)      | Targeted and transactional messages via email, SMS, voice, and Push notifications. |
| [SNS](https://docs.aws.amazon.com/sns/?id=docs_gateway)                | *Simple Notification Service* - Send and receive notifications from the cloud.     |

------

### End User Computing

| Service                                                                  | Description                                                          |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| [WorkSpaces](https://docs.aws.amazon.com/workspaces/?id=docs_gateway)    | Cloud-based virtual desktop environment for end-users. Think Citrix. |
| [AppStream 2.0](https://docs.aws.amazon.com/appstream2/?id=docs_gateway) | Managed application streaming. Also like Citrix.                     |
| [WorkDocs](https://docs.aws.amazon.com/workdocs/?id=docs_gateway)        | Managed enterprise-grade file storage and sharing service.           |
| [WorkLink](https://docs.aws.amazon.com/worklink/?id=docs_gateway)        | Access internal websites and apps from mobile devices.               |
| [WAM](https://docs.aws.amazon.com/wam/?id=docs_gateway)                  | *Workspaces Application Manager* - Manage applications in WorkSpaces |
| [NICE DCV](https://docs.aws.amazon.com/dcv/?id=docs_gateway)             | Remote 3D rendering.                                                 |

------

### Analytics

**Note:** *Data streams and streaming data may not be exactly what you think they are. Info [here.](https://aws.amazon.com/streaming-data/)*

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [AppFlow](https://docs.aws.amazon.com/appflow/?id=docs_gateway) | API integration of SaaS to AWS services. E.g. Slack to S3.   |
| [Athena](https://docs.aws.amazon.com/athena/?id=docs_gateway) | Analyze data in S3 using SQL queries.                        |
| [CloudSearch](https://docs.aws.amazon.com/cloudsearch/?id=docs_gateway) | Add search to your website. E.g. documents, forum posts, product info. |
| [Data Exchange](https://docs.aws.amazon.com/data-exchange/?id=docs_gateway) | Subscribe to products from data providers. Can copy to S3 for analytics. |
| [Data Pipeline](https://docs.aws.amazon.com/data-pipeline/?id=docs_gateway) | Automate the movement and transformation of data.            |
| [ES](https://docs.aws.amazon.com/elasticsearch-service/?id=docs_gateway) | *Elasticsearch Service* - Managed, open-source search and analytics engine. |
| [Elastic Map/Reduce (EMR)](https://docs.aws.amazon.com/emr/latest/ManagementGuide/index.html) | Run and scale big data frameworks. Hadoop.                   |
| [Glue](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html) | Managed ETL (Extract, Transform, Load). Categorize, clean, enrich data. |
| [Kinesis Video Streams](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/what-is-kinesis-video.html) | Capture, process, and store video streams for analytics and machine learning. |
| [Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html) | Real-time collection and processing of large data streams.   |
| [Kinesis Data Firehose](https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html) | Deliver real-time streaming data to S3, Redshift, ES, and Splunk. |
| [Kinesis Data Analytics](https://docs.aws.amazon.com/kinesis/?id=docs_gateway#amazon-kinesis-data-analytics) | Process and analyze streaming data using SQL, Java, or Scala. |
| [Kinesis Agent for Windows](https://docs.aws.amazon.com/kinesis-agent-windows/latest/userguide/index.html) | Collect, transform, and stream metrics from *any* Windows machine. |
| [Lake Formation](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html) | Set up and manage data lakes.                                |
| [MSK](https://docs.aws.amazon.com/msk/?id=docs_gateway)      | *Managed Streaming for Kafka * - Build apps that use Apache Kafka. |
| [QuickSight](https://docs.aws.amazon.com/quicksight/latest/user/welcome.html) | Scalable analytics service that can build visualizations and insights. |
| [Redshift](https://docs.aws.amazon.com/redshift/?id=docs_gateway) | Managed PB-scale data warehouse.                             |

------

### Application Integration

| Service                                                                       | Description |
| ----------------------------------------------------------------------------- | ----------- |
| [AppFlow](https://docs.aws.amazon.com/appflow/?id=docs_gateway)               |             |
| [EventBridge](https://docs.aws.amazon.com/eventbridge/?id=docs_gateway)       |             |
| [MQ](https://docs.aws.amazon.com/amazon-mq/?id=docs_gateway)                  |             |
| [SNS](https://docs.aws.amazon.com/sns/?id=docs_gateway)                       |             |
| [SQS](https://docs.aws.amazon.com/sqs/?id=docs_gateway)                       |             |
| [Step Functions](https://docs.aws.amazon.com/step-functions/?id=docs_gateway) |             |
| [SWF](https://docs.aws.amazon.com/swf/?id=docs_gateway)                       |             |

------

### Business Applications

| Service                                                                | Description |
| ---------------------------------------------------------------------- | ----------- |
| [Alexa for Business](https://docs.aws.amazon.com/a4b/?id=docs_gateway) |             |
| [Chime](https://docs.aws.amazon.com/chime/?id=docs_gateway)            |             |
| [WorkMail](https://docs.aws.amazon.com/workmail/?id=docs_gateway)      |             |

------

### Customer Enablement Services

| Service                                                                                 | Description |
| --------------------------------------------------------------------------------------- | ----------- |
| [Managed Services ](https://aws.amazon.com/managed-services/?id=docs_gateway)           |             |
| [Professional Services ](https://aws.amazon.com/professional-services/?id=docs_gateway) |             |
| [Support ](https://aws.amazon.com/premiumsupport/?id=docs_gateway)                      |             |
| [Training and Certification ](https://aws.amazon.com/training/?id=docs_gateway)         |             |
| [IQ](https://docs.aws.amazon.com/aws-iq/?id=docs_gateway)                               |             |

------

### Customer Engagement

| Service                                                                         | Description |
| ------------------------------------------------------------------------------- | ----------- |
| [Connect](https://docs.aws.amazon.com/connect/?id=docs_gateway)                 |             |
| [Pinpoint](https://docs.aws.amazon.com/pinpoint/?id=docs_gateway)               |             |
| [Simple Email Service ( SES)](https://docs.aws.amazon.com/ses/?id=docs_gateway) |             |

------

### Satellite

| Service                                                                       | Description |
| ----------------------------------------------------------------------------- | ----------- |
| [Ground Station](https://docs.aws.amazon.com/ground-station/?id=docs_gateway) |             |

------

### Robotics

| Service                                                             | Description |
| ------------------------------------------------------------------- | ----------- |
| [RoboMaker](https://docs.aws.amazon.com/robomaker/?id=docs_gateway) |             |

------

### Blockchain

| Service                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Managed Blockchain](https://docs.aws.amazon.com/managed-blockchain/latest/managementguide/index.html) | Decentralized, **trusted transactions** between multiple **parties**. |

------

### AR & VR

| Service                                                           | Description |
| ----------------------------------------------------------------- | ----------- |
| [Sumerian](https://docs.aws.amazon.com/sumerian/?id=docs_gateway) |             |

------

### Game Development

| Service                                                               | Description |
| --------------------------------------------------------------------- | ----------- |
| [GameLift](https://docs.aws.amazon.com/gamelift/?id=docs_gateway)     |             |
| [Lumberyard](https://docs.aws.amazon.com/lumberyard/?id=docs_gateway) |             |

### 

### 

### 

### 

### 

### 