* [The Open Guide to Amazon Web Services](https://github.com/open-guides/og-aws)

# IAM
- [Identity-based policies and resource-based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)
- [AWS global condition context keys | PrincipalOrgID](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)
- [Controlling access to and for IAM users and roles using tags | PrincipalTag](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html)

# Compute

## EC2
- [Elastic Network Interfaces in the Virtual Private Cloud](https://aws.amazon.com/blogs/aws/new-elastic-network-interfaces-in-the-virtual-private-cloud/)
- [On-Demand Capacity Reservations](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-capacity-reservations.html)
- [Block device mappings](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)
- [Add instance store volumes to your EC2 instance | Only at launch](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/add-instance-store-volumes.html)

## Cloud Watch
- [Enable or turn off detailed monitoring for your instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch-new.html)
- [Metrics collected by the CloudWatch agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/metrics-collected-by-CloudWatch-agent.html)
- [Sharing CloudWatch dashboards](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch-dashboard-sharing.html)
- [How do I turn on and configure enhanced networking on my EC2 instances?](https://repost.aws/knowledge-center/enable-configure-enhanced-networking)

### Cloud Watch Logs
- [Real-time processing of log data with subscriptions](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/Subscriptions.html)
- [Streaming CloudWatch Logs data to Amazon OpenSearch Service](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/CWL_OpenSearch_Stream.html)

## HPC
- [High Performance Computing Lens - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/high-performance-computing-lens/welcome.html)

## Batch
- [Multi-node parallel jobs](https://docs.aws.amazon.com/batch/latest/userguide/multi-node-parallel-jobs.html)

## Lambda
- [Invoking Lambda with events from other AWS services](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html)
- [Using Lambda with Amazon SQS](https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html)

## EKS
- [EKS | Enabling secret encryption on an existing cluster](https://docs.aws.amazon.com/eks/latest/userguide/enable-kms.html)
- [Private cluster requirements](https://docs.aws.amazon.com/eks/latest/userguide/private-clusters.html)
- [Metrics Server](https://kubernetes.io/docs/tasks/debug/debug-cluster/resource-metrics-pipeline/#metrics-server)
- [EKS Autoscaling](https://docs.aws.amazon.com/eks/latest/userguide/autoscaling.html)

# Networking  
## VPC
- [NAT gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)
- [NAT gateway basics](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-basics.html)
    - created in a specific Availability Zone 
    - implemented with redundancy in that zone
    - quota (of 5) of NAT gateways that you can create in each Availability Zone
- [Control traffic to your AWS resources using security groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)
- [Hybrid network connections](https://docs.aws.amazon.com/whitepapers/latest/hybrid-connectivity/hybrid-network-connections.html)
- [AWS PrivateLink concepts](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html)
- [Share your VPC with other accounts](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-sharing.html)
- [Control subnet traffic with NACL network access control lists](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
    - [Default network ACL | Allows all inbound and outbound](https://docs.aws.amazon.com/vpc/latest/userguide/default-network-acl.html)
    - Custom Network ACL | Denies all inbound and outbound by default
    
## VPN
- [What is AWS Site-to-Site VPN?](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html)
- [How AWS Site-to-Site VPN works | VPG & Customer Gateway](https://docs.aws.amazon.com/vpn/latest/s2svpn/how_it_works.html)
- [Site-to-Site VPN single and multiple VPN connection examples](https://docs.aws.amazon.com/vpn/latest/s2svpn/Examples.html)
  - Single Site-to-Site VPN connection
  - Single Site-to-Site VPN connection with a transit gateway
  - Multiple Site-to-Site VPN connections
  - Multiple Site-to-Site VPN connections with a transit gateway
  - Site-to-Site VPN connection with AWS Direct Connect
  - Private IP Site-to-Site VPN connection with AWS Direct Connect
- [Using redundant Site-to-Site VPN connections to provide failover](https://docs.aws.amazon.com/vpn/latest/s2svpn/vpn-redundant-connection.html)
- [Network-to-Amazon VPC connectivity options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/network-to-amazon-vpc-connectivity-options.html)
  - [AWS Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-site-to-site-vpn.html)
  - [AWS Transit Gateway + Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-transit-gateway-vpn.html)
  - [AWS Direct Connect](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect.html)
  - [AWS Direct Connect + AWS Transit Gateway](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-aws-transit-gateway.html)
  - [AWS Direct Connect + AWS Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-site-to-site-vpn.html)
  - [AWS Direct Connect + AWS Transit Gateway + AWS Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-aws-transit-gateway-vpn.html)
  - [AWS VPN CloudHub](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-vpn-cloudhub.html)
  - [AWS Transit Gateway + SD-WAN solutions](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-transit-gateway-sd-wan.html)
  - [Software VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/software-vpn.html)


## Direct Connect
- [Direct Connect gateways](https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways-intro.html)

## Load Balancers
- [Access logs for your Application Load Balancer | to S3 bucket](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-access-logs.html)
- [What is a Gateway Load Balancer?](https://docs.aws.amazon.com/elasticloadbalancing/latest/gateway/introduction.html)
- [Scaling network traffic inspection using AWS Gateway Load Balancer](https://aws.amazon.com/blogs/networking-and-content-delivery/scaling-network-traffic-inspection-using-aws-gateway-load-balancer/)
- [Health checks for your target groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html)
- [How do I attach backend instances with private IP addresses to my internet-facing load balancer in ELB?](https://repost.aws/knowledge-center/public-load-balancer-private-ec2)
- [Monitor your Network Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-monitoring.html)
   - CloudWatch metrics
   - VPC Flow Logs (One per network interface. There is one network interface per load balancer subnet)
   - Access logs
   - CloudTrail logs
- [Elastic Load Balancing adds support for Connection Draining](https://aws.amazon.com/about-aws/whats-new/2014/03/20/elastic-load-balancing-supports-connection-draining/)

## Cloudfront
- [Amazon CloudFront Dynamic Content Delivery](https://aws.amazon.com/cloudfront/dynamic-content/)
- [Amazon S3 + Amazon CloudFront](https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/)
- [Differences between CloudFront Functions and Lambda@Edge](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/edge-functions-choosing.html)
- [Restrict the geographic distribution of your content](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/georestrictions.html)
- [Use signed cookies](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-signed-cookies.html)

## API Gateway
- [Set up an API Gateway canary release deployment](https://docs.aws.amazon.com/apigateway/latest/developerguide/canary-release.html)
- [Set up VPC links for HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vpc-links.html)

## AppSync
- [GraphQL | Building Serverless APIs on AWS](https://aws.amazon.com/graphql/serverless-api/)

## Route53
- [DNS domain name format](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html)

# Storage

## EBS
- [Amazon EBS volume types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)
- [Amazon EBS fast snapshot restore](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-fast-snapshot-restore.html)
- [Amazon Data Lifecycle Manager | EBS snapshots and EBS-backed AMI](https://docs.aws.amazon.com/ebs/latest/userguide/snapshot-lifecycle.html)
- [Delete an Amazon EBS snapshot](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-deleting-snapshot.html)
- [EBS Snapshot Copy (Between Regions)](https://aws.amazon.com/blogs/aws/ebs-snapshot-copy/)
- [Amazon EBS encryption](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-encryption.html)
- [Amazon EBS–optimized EC2 instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html)

## EFS
- [How Amazon EFS works](https://docs.aws.amazon.com/efs/latest/ug/how-it-works.html)
- [Replicating file systems](https://docs.aws.amazon.com/efs/latest/ug/efs-replication.html)
- [Managing file system storage](https://docs.aws.amazon.com/efs/latest/ug/lifecycle-management-efs.html)

## S3
- [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)
- [Amazon S3 Object Lambda](https://aws.amazon.com/s3/features/object-lambda/)
- [Using S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html)
- [Create Write-Once-Read-Many Archive Storage with Amazon Glacier](https://aws.amazon.com/blogs/aws/glacier-vault-lock/)
- [S3 Lock Policies and Glacier Vault Lock](http://www.ebsguide.com/9-s3-lock-policies-and-glacier-vault-lock/)
- [AWS PrivateLink for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/privatelink-interface-endpoints.html)
- [Retrieving S3 Glacier Archives Using AWS Console](https://docs.aws.amazon.com/amazonglacier/latest/dev/downloading-an-archive-two-steps.html)
- [Amazon S3 Access Points](https://aws.amazon.com/s3/features/access-points/)
- [How to Prevent Uploads of Unencrypted Objects to Amazon S3](https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/)

## DynamoDB
- [DynamoDB on-demand and provisioned capacity](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/capacity.html)
- [Managing throughput capacity automatically with DynamoDB auto scaling](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/AutoScaling.html)
- [Change data capture for DynamoDB Streams](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html)
- [Using Kinesis Data Streams to capture changes to DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/kds.html)

## FSx
- [Mounting Amazon FSx file systems from on-premises or a peered Amazon VPC](https://docs.aws.amazon.com/fsx/latest/LustreGuide/mounting-on-premises.html)

## Storage gateway
- [Amazon S3 File Gateway](https://aws.amazon.com/storagegateway/file/s3/)
- [Amazon FSx File Gateway](https://aws.amazon.com/storagegateway/file/fsx/)

## DataSync
- [https://aws.amazon.com/datasync/features/](https://aws.amazon.com/datasync/features/)

## RDS
- [Configuring and managing a Multi-AZ deployment](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)
- [Multi-AZ DB instance deployments | Sync, Only Failover](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)
- [Multi-AZ DB cluster deployments | Sync, Failover & Reads](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/multi-az-db-clusters-concepts.html)
- [Working with DB instance read replicas | Async](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)
- [Stopping an Amazon RDS DB instance temporarily](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_StopInstance.html)
- [Creating a database account using IAM authentication](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.DBAccounts.html)
- [Managing capacity automatically with Amazon RDS storage autoscaling](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html#USER_PIOPS.Autoscaling)

## Caching
- [Authenticating with the Redis AUTH command](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/auth.html)
- [Comparing Redis OSS and Memcached](https://aws.amazon.com/elasticache/redis-vs-memcached/)
- [Turbocharge Amazon S3 with Amazon ElastiCache for Redis](https://aws.amazon.com/blogs/storage/turbocharge-amazon-s3-with-amazon-elasticache-for-redis/)

## Aurora
- [Replication with Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html)
- [Recovering an Amazon Aurora global database from an unplanned outage](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html#aurora-global-database-failover)

## Redshift
- [System and architecture overview](https://docs.aws.amazon.com/redshift/latest/dg/c_redshift_system_overview.html)
- [Querying external data using Amazon Redshift Spectrum](https://docs.aws.amazon.com/redshift/latest/dg/c-using-spectrum.html)

## Database Migration Service
- [What is AWS Database Migration Service?](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html)
- [Using an Amazon DynamoDB database as a target for AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.DynamoDB.html)
- [Creating tasks for ongoing replication using AWS DMS](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html)

# Data Migration & Transfer
## AWS Transfer Family
- [AWS Transfer Family | Secure File Transfer Service](https://aws.amazon.com/aws-transfer-family/)

# Integration
## SQS
- [Amazon SQS visibility timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)
- [Amazon SQS short and long polling](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html)

## Kinesis
- [Amazon Kinesis Data Streams](https://aws.amazon.com/kinesis/data-streams/)
- [Amazon Data Firehose Destinations](https://docs.aws.amazon.com/firehose/latest/dev/create-destination.html)
- [Amazon Kinesis Data Analytics for SQL Applications: How It Works](https://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works.html)
- [Amazon Managed Service for Apache Flink](https://aws.amazon.com/managed-service-apache-flink/)

# Analytics

## Athena
- [Amazon Athena FAQs](https://aws.amazon.com/athena/faqs/)
- [AWS Data Exchange](https://aws.amazon.com/data-exchange/)
- [Using Amazon Athena Federated Query](https://docs.aws.amazon.com/athena/latest/ug/connect-to-a-data-source.html)
- [Querying AWS CloudTrail logs](https://docs.aws.amazon.com/athena/latest/ug/cloudtrail-logs.html)

## EMR
- [What is Amazon EMR?](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)

# Security
- [What are AWS WAF, AWS Shield Advanced;, and AWS Firewall Manager?](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)
- [AWS Firewall Manager](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html)

## IAM Identity Center
- [Connect a self-managed directory in Active Directory to IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/connectonpremad.html)
- [Connect to a Microsoft AD directory](https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source-ad.html)

## Cognito
- [Amazon Cognito user pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html)
- [Amazon Cognito identity pools
](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-identity.html)

# Governance and Management

## Cloud Trail
- [What Is AWS CloudTrail?](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
- [Creating a trail for an organization](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html)
- [Analyzing log data with CloudWatch Logs Insights](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html)
- [Tutorial: Log AWS API calls using EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-log-api-call.html)
- [Monitoring AWS Config with Amazon EventBridge](https://docs.aws.amazon.com/config/latest/developerguide/monitor-config-with-cloudwatchevents.html)
- [AWS Config Managed rules - access-keys-rotated](https://docs.aws.amazon.com/config/latest/developerguide/access-keys-rotated.html)

## Systems Manager
- [Patching your Windows EC2 instances using AWS Systems Manager Patch Manager](https://aws.amazon.com/blogs/mt/patching-your-windows-ec2-instances-using-aws-systems-manager-patch-manager/)
- [Install or update packages | Run Command & State Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/distributor-working-with-packages-deploy.html)

## Configuration 
- [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)
- [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)
- [AWS System Manager Parameter Store vs Secrets Manager vs Environment Variation in Lambda, when to use which](https://stackoverflow.com/questions/63235425/aws-system-manager-parameter-store-vs-secrets-manager-vs-environment-variation-i)

## Backups
- [What is AWS Backup?](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html)

## GuardDuty
- [What is Amazon GuardDuty?](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)
- [Creating custom responses to GuardDuty findings with Amazon CloudWatch Events](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings_cloudwatch.html)

## Inspector
- [Amazon Inspector - Automated vulnerability management](https://aws.amazon.com/inspector/)

## License Manager 
- [AWS License Manager](https://aws.amazon.com/license-manager/)

## Service Catalog
- [AWS Service Catalog | Manage IaC templates](https://aws.amazon.com/servicecatalog/)


# ML
- [Amazon Comprehend - NLP](https://aws.amazon.com/comprehend/)
- [Amazon Kendra - Enterprise Search Engine](https://aws.amazon.com/kendra/)
- [Types of Amazon Macie findings](https://docs.aws.amazon.com/macie/latest/user/findings-types.html)

# Misc
- [AWS Private 5G](https://aws.amazon.com/private5g/)

# Billing and Pricing
- [AWS Compute Optimizer FAQs](https://aws.amazon.com/compute-optimizer/faqs/)
- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
- [AWS Cost Explorer Video](https://www.youtube.com/watch?v=xTIR5cvOfPc)
- [AWS Cost Explorer API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_Operations_AWS_Cost_Explorer_Service.html)
- [Configuring AWS Budgets actions](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-controls.html)

# Architecture & Design
- [Rapidly recover mission-critical systems in a disaster](https://aws.amazon.com/blogs/publicsector/rapidly-recover-mission-critical-systems-in-a-disaster/)