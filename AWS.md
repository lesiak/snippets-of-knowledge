* [The Open Guide to Amazon Web Services](https://github.com/open-guides/og-aws)

# IAM
- [Identity-based policies and resource-based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)
- [Permissions boundaries for IAM entities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)
- [When and where to use IAM permissions boundaries](https://aws.amazon.com/blogs/security/when-and-where-to-use-iam-permissions-boundaries/)
  > The predominant use case for permissions boundaries is to limit privileges available to IAM roles created by developers (referred to as delegated administrators in the IAM documentation) who have permissions to create and manage these roles.
  >
  > To limit access, the central administrator can attach a condition to the developer’s identity policy that helps ensure that the developer can only create a role if the role has a permissions boundary policy attached to it.
  > ```
  > "Effect": "Allow",
  > "Action": "iam:CreateRole",
  > "Condition": {
  >    "StringEquals": {
  >       "iam:PermissionsBoundary": "arn:aws:iam::<YourAccount_ID>:policy/<DevelopersPermissionsBoundary>"
  >    }
  > }
  > ```
- [AWS global condition context keys | PrincipalOrgID](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)
- [Controlling access to and for IAM users and roles using tags | PrincipalTag](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html)
- [How can I use IAM roles to restrict API calls from specific IP addresses to the AWS Management Console?](https://repost.aws/knowledge-center/iam-restrict-calls-ip-addresses)
- [Setting an account password policy for IAM users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html?icmpid=docs_iam_console)

# Compute

## EC2
- [Elastic Network Interfaces in the Virtual Private Cloud](https://aws.amazon.com/blogs/aws/new-elastic-network-interfaces-in-the-virtual-private-cloud/)
- [On-Demand Capacity Reservations](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-capacity-reservations.html)
- [Block device mappings](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)
- [Add instance store volumes to your EC2 instance | Only at launch](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/add-instance-store-volumes.html)
- [Elastic Network Adapter – High Performance Network Interface for Amazon EC2](https://aws.amazon.com/blogs/aws/elastic-network-adapter-high-performance-network-interface-for-amazon-ec2/)
- [Now Available – Elastic Fabric Adapter (EFA) for Tightly-Coupled HPC Workloads](https://aws.amazon.com/blogs/aws/now-available-elastic-fabric-adapter-efa-for-tightly-coupled-hpc-workloads/)
- [How do I turn on and configure enhanced networking on my EC2 instances?](https://repost.aws/knowledge-center/enable-configure-enhanced-networking)
- [Hibernate your Amazon EC2 instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Hibernate.html)
- [Instance purchasing options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html)
  > **Reserved Instances do not reserve capacity**
  >
  > RIs do not guarantee that the reserved instance type will be available when you need it. This is an important distinction, as it means that even if you have an RI, you may not be able to launch an instance of the reserved type if the AZ is fully utilized or if there's an outage.
- [Placement groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)

## EC2 Auto-Scaling
- [Step and simple scaling policies for Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html)
  > Step scaling and simple scaling policies scale the capacity of your Auto Scaling group in predefined increments based on CloudWatch alarms. You can define separate scaling policies to handle scaling out (increasing capacity) and scaling in (decreasing capacity) when an alarm threshold is breached.
- [Target tracking scaling policies for Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html)
- [Scaling policy based on Amazon SQS](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)

## Cloud Watch
- [Enable or turn off detailed monitoring for your instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch-new.html)
- [Metrics collected by the CloudWatch agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/metrics-collected-by-CloudWatch-agent.html)
- [Sharing CloudWatch dashboards](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch-dashboard-sharing.html)

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
- [Invoking Lambda functions with Amazon SNS notifications](https://docs.aws.amazon.com/lambda/latest/dg/with-sns.html)
- [Understanding Lambda function scaling](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)
   - Account quota of 1,000 concurrent executions across all functions in an AWS Region
   - Reserved Concurrency | reserve a portion of your account's concurrency for a function
   - Provisioned Concurrency |  pre-initialize a number of environment instances for a function.

## ECS
- [Amazon ECS task IAM role](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-iam-roles.html)
- [Amazon ECS container instance IAM role](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/instance_IAM_role.html)
- [AWS managed policies for Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/security-iam-awsmanpol.html)
  - [AmazonECSTaskExecutionRolePolicy](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/security-iam-awsmanpol.html#security-iam-awsmanpol-AmazonECSTaskExecutionRolePolicy) grants the permissions that are needed by the Amazon ECS container agent and AWS Fargate container agents to make AWS API calls on your behalf (pull image, write logs etc)
- [Automatically scale your Amazon ECS service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html)

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
    - Default SG allows inbound from from within the group and all outbound traffic
    - Custom SG denies all inbound and allows all outbound traffic by default
- [Hybrid network connections](https://docs.aws.amazon.com/whitepapers/latest/hybrid-connectivity/hybrid-network-connections.html)
- [AWS PrivateLink concepts](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html)
- [Share your VPC with other accounts](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-sharing.html)
- [Control subnet traffic with NACL network access control lists](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
    - [Default network ACL | Allows all inbound and outbound](https://docs.aws.amazon.com/vpc/latest/userguide/default-network-acl.html)
    - Custom Network ACL | Denies all inbound and outbound by default
    - Gotcha: Network ACL only applies to services in a subnet - cannot be used for CloudFront

## PrivateLink
- [What is AWS PrivateLink?](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)
  > AWS PrivateLink is a highly available, scalable technology that you can use to privately connect your VPC to services as if they were in your VPC. You do not need to use an internet gateway, NAT device, public IP address, AWS Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with the service from your private subnets. Therefore, you control the specific API endpoints, sites, and services that are reachable from your VPC.
- [Access AWS services through AWS PrivateLink](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html)
- [Securely Access Services Over AWS PrivateLink](https://docs.aws.amazon.com/whitepapers/latest/aws-privatelink/aws-privatelink.html)
- [Gateway endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/gateway-endpoints.html)
  - S3
  - DynamoDB
- [Share your services through AWS PrivateLink](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-share-your-services.html)
  > You can host your own AWS PrivateLink powered service, known as an endpoint service, and share it with other AWS customers.
  >
  > PrivateLink endpoint in consumer VPC
  > Load balancer (NLB or GLB) in provider VPC
    
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
    > With AWS Direct Connect + AWS Site-to-Site VPN, you can combine AWS Direct Connect connections with an AWS-managed VPN solution. AWS Direct Connect public VIFs establish a dedicated network connection between your network and public AWS resources such as an AWS Site-to-Site VPN endpoint. **Once you establish the connection to the service, you can create IPsec connections to the corresponding Amazon VPC virtual private gateways**.
  - [AWS Direct Connect + AWS Transit Gateway + AWS Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-aws-transit-gateway-vpn.html)
  - [AWS VPN CloudHub](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-vpn-cloudhub.html)
  - [AWS Transit Gateway + SD-WAN solutions](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-transit-gateway-sd-wan.html)
  - [Software VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/software-vpn.html)
- [Amazon VPC-to-Amazon VPC connectivity options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/amazon-vpc-to-amazon-vpc-connectivity-options.html)
  - [VPC peering](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/vpc-peering.html)
  - [AWS Transit Gateway](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-transit-gateway.html)
  - [AWS PrivateLink](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-privatelink.html)
  - [Software VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/software-vpn-1.html)
  - [Software VPN-to-AWS Site-to-Site VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/software-vpn-to-aws-site-to-site-vpn.html)
  - Gotcha: No Amazon-managed VPN between VPCs

## Direct Connect
- [Direct Connect gateways](https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways-intro.html)
- Do I need a Direct connect gateway to use AWS Direct Connect?  
  > **When you don't need a Direct Connect Gateway:**
  > **Single connection**: If you have a single AWS Direct Connect connection to a single AWS Region, you don't need a Direct Connect Gateway.
  > **When you need a Direct Connect Gateway:**
  > - Multiple AWS Regions
  > - Multiple AWS Accounts
  An AWS Direct Connect Gateway is a virtual router that allows you to manage and route traffic between your on-premises network and multiple AWS Regions or accounts. It's a logical component that sits between your on-premises network and AWS, providing a centralized point of management for your Direct Connect connections.
  > 
- [AWS Direct Connect Resiliency Recommendations](https://aws.amazon.com/directconnect/resiliency-recommendation/)

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
- [How do I use CloudFront to serve a static website that’s hosted on Amazon S3?](https://repost.aws/knowledge-center/cloudfront-serve-static-website)
- [Restrict access to an Amazon Simple Storage Service origin | origin access control (OAC) and origin access identity (OAI)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)
  > CloudFront provides two ways to send authenticated requests to an Amazon S3 origin: origin access control (OAC) and origin access identity (OAI). OAC helps you secure your origins, such as for Amazon S3. We recommend using OAC
- [Restrict access to an AWS Lambda function URL origin](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-lambda.html)
  > CloudFront provides origin access control (OAC) for restricting access to a Lambda function URL origin.
- [How do I restrict direct traffic to an Application Load Balancer and allow traffic through only CloudFront?](https://repost.aws/knowledge-center/waf-restrict-alb-allow-cloudfront)
  > To restrict direct traffic to an Application Load Balancer and allow access only through CloudFront, use one or both of the following solutions:
  > - AWS WAF
  > - Security groups
  >
  > Note: It's a best practice to combine the two following solutions.
  > 
  > To use AWS WAF to restrict direct traffic to an Application Load Balancer and allow traffic through only CloudFront, do the following:
  > 1. Configure CloudFront to add a custom HTTP header with a secret value in the requests that CloudFront sends to the Application Load Balancer.
  > 2. Create a rule in the AWS WAF web access control list (web ACL) associated with the Application Load Balancer. Use this rule to block requests that don't contain the custom HTTP header secret value.
  >
  > You can use security groups to restrict direct traffic to an Application Load Balancer and allow traffic through only CloudFront. To do this, use an AWS managed prefix list on security groups in the Application Load Balancer.
  >
  > To update an existing security group, follow the steps in Update the associated security groups. To associate your Application Load Balancer with a security group, complete the following:
  > 1. Open the Amazon EC2 console.
  > 2. Select Load balancers, and then select the Application Load Balancer that you want to restrict direct access to.
  > 3. Choose Security.
  > 4. Select the security group that you want to associate with your Application Load Balancer.
  > 5. To modify the inbound rules, select Edit inbound rules, and then update the configurations to your use case.
  > 6. To allow specific protocols, select the protocol and then choose Custom.
  > 7. For Source type, choose CloudFront, and then select your prefixes from the AWS managed prefix list.
  > 8. Choose Save.
  >
  > See [How to Automatically Update Your Security Groups for Amazon CloudFront and AWS WAF by Using AWS Lambda](https://aws.amazon.com/blogs/security/how-to-automatically-update-your-security-groups-for-amazon-cloudfront-and-aws-waf-by-using-aws-lambda/)

- [Optimize high availability with CloudFront origin failover](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/high_availability_origin_failover.html)
- [Differences between CloudFront Functions and Lambda@Edge](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/edge-functions-choosing.html)
- [Restrict the geographic distribution of your content](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/georestrictions.html)
- [Use signed cookies](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-signed-cookies.html)
- [Amazon CloudFront Pricing | Price Class](https://aws.amazon.com/cloudfront/pricing/)
- [Lambda@Edge Use cases](https://aws.amazon.com/lambda/edge/)
  - SIMPLIFY AND REDUCE ORIGIN INFRASTRUCTURE
    - Website Security and Privacy
    - Dynamic Web Application at the Edge
    - Search Engine Optimization (SEO)
    - Intelligently Route Across Origins and Data Centers
    - Bot Mitigation at the Edge
  - IMPROVED USER EXPERIENCE
    - Real-time Image Transformation
    - A/B Testing
    - User Authentication and Authorization
    - User Prioritization
- Gotcha: CloudFront cannot listen on UDP

## AWS Global Accelerator
- [What is AWS Global Accelerator?](https://docs.aws.amazon.com/global-accelerator/latest/dg/what-is-global-accelerator.html)

## API Gateway
- [Set up an API Gateway canary release deployment](https://docs.aws.amazon.com/apigateway/latest/developerguide/canary-release.html)
- [Set up VPC links for HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vpc-links.html)
- [Invoking a Lambda function using an Amazon API Gateway endpoint](https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway.html)

## AppSync
- [GraphQL | Building Serverless APIs on AWS](https://aws.amazon.com/graphql/serverless-api/)

## Route53
- [DNS domain name format](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html)
- [Configuring DNS failover](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-configuring.html)
- [Choosing a routing policy](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html)
  - Simple routing policy
  - Failover routing policy 
  - Geolocation routing policy
  - Geoproximity routing policy
  - Latency routing policy
  - IP-based routing policy
  - Multivalue answer routing policy
  - Weighted routing policy

# Storage

## EBS
- [Amazon EBS volume types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)
- [Amazon EBS fast snapshot restore](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-fast-snapshot-restore.html)
- [Amazon Data Lifecycle Manager | EBS snapshots and EBS-backed AMI](https://docs.aws.amazon.com/ebs/latest/userguide/snapshot-lifecycle.html)
- [Delete an Amazon EBS snapshot](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-deleting-snapshot.html)
- [EBS Snapshot Copy (Between Regions)](https://aws.amazon.com/blogs/aws/ebs-snapshot-copy/)
- [Amazon EBS encryption](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-encryption.html)
- [Amazon EBS–optimized EC2 instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html)
- [Attach a volume to multiple instances with Amazon EBS Multi-Attach](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volumes-multi.html)
  > Amazon EBS Multi-Attach enables you to attach a single Provisioned IOPS SSD (io1 or io2) volume to multiple instances that are in the same Availability Zone.

## EFS
- [How Amazon EFS works](https://docs.aws.amazon.com/efs/latest/ug/how-it-works.html)
- [Replicating file systems](https://docs.aws.amazon.com/efs/latest/ug/efs-replication.html)
- [Managing file system storage](https://docs.aws.amazon.com/efs/latest/ug/lifecycle-management-efs.html)
  > Lifecycle policies:
  > - Transition into IA
  > - Transition into Archive
  > - Transition into Standard
- [Amazon EFS Infrequent Access](https://aws.amazon.com/efs/features/infrequent-access/)
- [Managing mount targets](https://docs.aws.amazon.com/efs/latest/ug/accessing-fs.html)
  - For Amazon EFS file systems that use Regional storage classes, you can create a mount target in each Availability Zone in an AWS Region. 
  - For One Zone file systems, you can only create a single mount target in the same Availability Zone as the file system.

## S3
- [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)
- [Bucket policies for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html)
- [Identity-based policies for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security_iam_id-based-policy-examples.html)
- [Access control list (ACL) overview](https://docs.aws.amazon.com/AmazonS3/latest/userguide/acl-overview.html)
  >  With bucket policies, there is a single policy for the entire bucket, but object ACLs are specified for each object. We recommend that you keep ACLs turned off, except in unusual circumstances where you must individually control access for each object.
  >
  > When you grant access rights, you specify each grantee as a type="value" pair, where type is one of the following:
  > - `id` – If the value specified is the canonical user ID of an AWS account
  > - `uri` – If you are granting permissions to a predefined group
  > - `emailAddress` – If the value specified is the email address of an AWS account 
- [Amazon S3 Object Lambda](https://aws.amazon.com/s3/features/object-lambda/)
- [Using S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html)
- [Create Write-Once-Read-Many Archive Storage with Amazon Glacier](https://aws.amazon.com/blogs/aws/glacier-vault-lock/)
- [S3 Lock Policies and Glacier Vault Lock](http://www.ebsguide.com/9-s3-lock-policies-and-glacier-vault-lock/)
- [AWS PrivateLink for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/privatelink-interface-endpoints.html)
- [Retrieving S3 Glacier Archives Using AWS Console](https://docs.aws.amazon.com/amazonglacier/latest/dev/downloading-an-archive-two-steps.html)
- [Amazon S3 Access Points](https://aws.amazon.com/s3/features/access-points/)
- [How to Prevent Uploads of Unencrypted Objects to Amazon S3](https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/)
- [Key differences between a website endpoint and a REST API endpoint](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteEndpoints.html#WebsiteRestEndpointDiff)
- [Hosting a static website using Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [Deleting an object from an MFA delete-enabled bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingMFADelete.html)
  - x-amz-mfa header

## DynamoDB
- [DynamoDB on-demand and provisioned capacity](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/capacity.html)
- [Managing throughput capacity automatically with DynamoDB auto scaling](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/AutoScaling.html)
- [Change data capture for DynamoDB Streams](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html)
- [Using Kinesis Data Streams to capture changes to DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/kds.html)

## FSx
- [Mounting Amazon FSx file systems from on-premises or a peered Amazon VPC](https://docs.aws.amazon.com/fsx/latest/LustreGuide/mounting-on-premises.html)
- [Availability and durability: Single-AZ and Multi-AZ file systems](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/high-availability-multiAZ.html)
- [Amazon FSx for Lustre](https://aws.amazon.com/fsx/lustre/)
  > Access and process Amazon S3 data from a high-performance file system by linking your file systems to S3 buckets.

## Storage gateway
- [Amazon S3 File Gateway](https://aws.amazon.com/storagegateway/file/s3/)
- [Amazon FSx File Gateway](https://aws.amazon.com/storagegateway/file/fsx/)
- [AWS Storage Gateway Hardware Appliance](https://aws.amazon.com/storagegateway/hardware-appliance/)
  > The AWS Storage Gateway Hardware Appliance is a physical, standalone, validated server configuration for on-premises deployments. It comes pre-loaded with Storage Gateway software, and provides all the required CPU, memory, network, and SSD cache resources for creating and configuring File Gateway, Volume Gateway, or Tape Gateway. The Storage Gateway Hardware Appliance is designed to provide you with a simple out of the box experience that does not require any additional infrastructure, and is managed from the AWS Console or API.
  >
  > Compare AWS Storage gateway with AWS Storage gateway hardware appliance
  >
  > **AWS Storage Gateway (Software Appliance)**
  > A software appliance that can be installed on a virtual machine or a physical server in your on-premises environment.
  >
  > **AWS Storage Gateway Hardware Appliance**
  > * A pre-configured, physical appliance that is shipped to your location.

## DataSync
- [AWS DataSync features](https://aws.amazon.com/datasync/features/)
- [AWS DataSync FAQs](https://aws.amazon.com/datasync/faqs/)

## RDS
- [Configuring and managing a Multi-AZ deployment](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)
- [Multi-AZ DB instance deployments | Sync, Only Failover](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)
- [Multi-AZ DB cluster deployments | Sync, Failover & Reads](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/multi-az-db-clusters-concepts.html)
- [Working with DB instance read replicas | Async](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)
  - Gotcha: You cannot create an RDS Read Replica of a database that is running on Amazon EC2. 
- [Amazon RDS Read Replicas Now Support Multi-AZ Deployments](https://aws.amazon.com/about-aws/whats-new/2018/01/amazon-rds-read-replicas-now-support-multi-az-deployments/)
- [Encrypting Amazon RDS resources](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html)
- [Stopping an Amazon RDS DB instance temporarily](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_StopInstance.html)
- [Creating a database account using IAM authentication](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.DBAccounts.html)
- [Managing capacity automatically with Amazon RDS storage autoscaling](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html#USER_PIOPS.Autoscaling)
- [Encrypt an existing Amazon RDS for PostgreSQL DB instance | DMS to synchronize new data](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/encrypt-an-existing-amazon-rds-for-postgresql-db-instance.html)
- [Using SSL/TLS to encrypt a connection to a DB instance or cluster](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html)

## Aurora
- [Replication with Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html)
- [Recovering an Amazon Aurora global database from an unplanned outage](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html#aurora-global-database-failover)
- [Amazon Aurora storage and reliability](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.StorageReliability.html)
- [How is Aurora serverless different than aurora with autoscaling?](https://stackoverflow.com/questions/74352620/how-is-aurora-serverless-different-than-aurora-with-autoscaling)
  > **AWS Aurora Autoscaling** works by adding more number of reader instances to the Aurora Cluster and when it has to scale down, it remove the reader instances. Important here, this process takes some time to spin up the new reader instances as well to remove them, so you should configure your autoscaling policy accordingly. Autoscaling only add read capacity to Aurora Cluster.
  >
  > **AWS Aurora Serverless** continuously tracks utilization of resources such as CPU, memory, and network and scale any writer or reader instance. AWS Aurora Serverless scales instantly to hundreds of thousands of transactions in a fraction of a second, it adjusts capacity in fine-grained increments to provide the right amount of database resources that the application needs. Aurora Serverles increase write and read capacity to Aurora Cluster.

## Caching
- [Authenticating with the Redis AUTH command](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/auth.html)
- [Comparing Redis OSS and Memcached](https://aws.amazon.com/elasticache/redis-vs-memcached/)
- [Turbocharge Amazon S3 with Amazon ElastiCache for Redis](https://aws.amazon.com/blogs/storage/turbocharge-amazon-s3-with-amazon-elasticache-for-redis/)

## Redshift
- [System and architecture overview](https://docs.aws.amazon.com/redshift/latest/dg/c_redshift_system_overview.html)
- [Querying external data using Amazon Redshift Spectrum](https://docs.aws.amazon.com/redshift/latest/dg/c-using-spectrum.html)
- [Amazon Redshift Introduces Result Caching for Sub-Second Response for Repeat Queries](https://aws.amazon.com/about-aws/whats-new/2017/11/amazon-redshift-introduces-result-caching-for-sub-second-response-for-repeat-queries/)
  > Dashboard, visualization, and business intelligence (BI) tools that execute repeat queries will see a significant boost in performance due to result caching. In addition, result caching frees up resources to improve performance of all other queries. 



## Lake Formation
- [What is AWS Lake Formation?](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html)
- [Lake Formation tag-based access control](https://docs.aws.amazon.com/lake-formation/latest/dg/tag-based-access-control.html)

# Data Migration & Transfer
## Database Migration Service
- [What is AWS Database Migration Service?](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html)
- [Using an Amazon DynamoDB database as a target for AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.DynamoDB.html)
- [Creating tasks for ongoing replication using AWS DMS](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html)
- [Migrate an on-premises Microsoft SQL Server database to Amazon RDS for SQL Server](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/migrate-an-on-premises-microsoft-sql-server-database-to-amazon-rds-for-sql-server.html)
  - Using AWS DMS
  - Using native SQL Server tools

## AWS Transfer Family
- [AWS Transfer Family | Secure File Transfer Service](https://aws.amazon.com/aws-transfer-family/)

## Snow family:
- [AWS Snow Family](https://aws.amazon.com/snow/)
  - Snowcone: 8 TB HDD + 14TB SSD
  - SNOWBALL EDGE STORAGE OPTIMIZED 80 TB
  - SNOWBALL EDGE STORAGE OPTIMIZED 210 TB
  - SNOWBALL EDGE COMPUTE OPTIMIZED 28 TB

# Integration
## SQS
- [Amazon SQS visibility timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)
- [Amazon SQS short and long polling](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html)
- [Basic examples of Amazon SQS policies](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-basic-examples-of-sqs-policies.html)
  - Grant one permission to one AWS account
  - Grant two permissions to one AWS account
  - Grant all permissions to two AWS accounts
  - Grant cross-account permissions to a role and a username
  - Grant a permission to all users
  - Grant a time-limited permission to all users
  - Grant all permissions to all users in a CIDR range
  - Allowlist and blocklist permissions for users in different CIDR ranges

## SNS
- [What is Amazon SNS?](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)
  > While SNS provides some control over message delivery, such as:
  > 1. **Message filtering**: You can use message attributes and filtering policies to control which messages are delivered to specific subscribers.
  > 2. **Message throttling**: You can set a limit on the number of messages delivered per second to a subscriber.
  >
  > However, SNS does not provide direct control over the flow of messages or buffering, which means that if the consumer is not able to process messages quickly enough, they might be lost or delivered multiple times.

## Kinesis
- [Amazon Kinesis Data Streams Terminology and Concepts](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)
  - Gotcha: Amazon Kinesis Data Streams should be used for near-real time or real-time use cases instead of Amazon SQS
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

## QuickSight
- [Logging operations with AWS CloudTrail](https://docs.aws.amazon.com/quicksight/latest/user/logging-using-cloudtrail.html)

# Security
- [What are AWS WAF, AWS Shield Advanced;, and AWS Firewall Manager?](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)

## AWS Network Firewall
- [What is AWS Network Firewall?](https://docs.aws.amazon.com/network-firewall/latest/developerguide/what-is-aws-network-firewall.html)
- [How AWS Network Firewall works](https://docs.aws.amazon.com/network-firewall/latest/developerguide/how-it-works.html)

## Web Application Firewall
- [AWS WAF rules](https://docs.aws.amazon.com/waf/latest/developerguide/waf-rules.html)
- [Match rule statements](https://docs.aws.amazon.com/waf/latest/developerguide/waf-rule-statements-match.html)
  - Geographic match
  - IP set match
  - Label match rule statement
  - Regex match rule statement
  - Regex pattern set
  - Size constraint
  - SQLi attack
  - String match
  - XSS scripting attack
- [AWS Firewall Manager](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html)
- [AWS Certificate Manager](https://aws.amazon.com/certificate-manager/)
  >  provision, manage, and deploy public and private SSL/TLS certificates for use with AWS services and your internal connected resources. ACM removes the time-consuming manual process of purchasing, uploading, and renewing SSL/TLS certificates.

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

## AWS Organizations
- [Service control policies (SCPs)](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
  - SCPs affect only member accounts in the organization. They have no effect on users or roles in the management account.
  - Users and roles must still be granted permissions with appropriate IAM permission policies. A user without any IAM permission policies has no access, even if the applicable SCPs allow all services and all actions.
  - If a user or role has an IAM permission policy that grants access to an action that is also allowed by the applicable SCPs, the user or role can perform that action.
  - If a user or role has an IAM permission policy that grants access to an action that is either not allowed or explicitly denied by the applicable SCPs, the user or role can't perform that action.
  - SCPs affect all users and roles in attached accounts, including the root user. The only exceptions are those described in Tasks and entities not restricted by SCPs.
- [How do I move an account from an existing AWS Organization to another AWS Organization?](https://repost.aws/knowledge-center/organizations-move-accounts)
  > - Use the AWS Organizations console if you have only a few accounts to migrate.
  > - If you're migrating many accounts, then use the AWS Organizations API or AWS Command Line Interface (AWS CLI) to move the accounts instead.
- [How to Use AWS Organizations to Automate End-to-End Account Creation](https://aws.amazon.com/blogs/security/how-to-use-aws-organizations-to-automate-end-to-end-account-creation/)
  > - AWS Organizations API to create accounts
  > - CloudFormation to configure accounts

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
  > GuardDuty uses machine learning and anomaly detection to identify potential threats in your AWS environment, including network traffic, system calls, and DNS queries.
  >
  > GuardDuty is more focused on detecting and alerting on potential security threats, making it a better choice for protecting against attacks.
  > GuardDuty can detect various types of attacks, including:
  > * Network-based attacks, such as port scanning and SQL injection
  > * Malware and ransomware
  > * Unauthorized access to resources
  > * Anomalous API calls
- [Creating custom responses to GuardDuty findings with Amazon CloudWatch Events](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings_cloudwatch.html)

## Inspector
- [Amazon Inspector - Automated vulnerability management](https://aws.amazon.com/inspector/)
  > Inspector is focused on identifying vulnerabilities and compliance issues, which can help prevent attacks, but it does not detect or alert on active threats.

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