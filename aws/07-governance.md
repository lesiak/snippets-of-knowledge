# Governance and Management

## Cloud Trail
- [What Is AWS CloudTrail?](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
  > CloudTrail provides three ways to record events:
  > - Event history – The Event history provides a viewable, searchable, downloadable, and immutable record of the past 90 days of management events in an AWS Region. You can search events by filtering on a single attribute. You automatically have access to the Event history when you create your account. For more information, see Working with CloudTrail event history.
  >
  > There are no CloudTrail charges for viewing the Event history.
  > - CloudTrail Lake
  > - Trails – Trails capture a record of AWS activities, delivering and storing these events in an Amazon S3 bucket, with optional delivery to CloudWatch Logs and Amazon EventBridge. You can input these events into your security monitoring solutions. You can also use your own third-party solutions or solutions such as Amazon Athena to search and analyze your CloudTrail logs. You can create trails for a single AWS account or for multiple AWS accounts by using AWS Organizations. You can log Insights events to analyze your management events for anomalous behavior in API call rates and error rates. For more information, see Creating a trail for your AWS account.
- [Understanding CloudTrail events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-events.html)
  - Management events
  - Data events
  - Network activity events
  - Insights events
- [Working with CloudTrail event history](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)
   > - The Event history page on the CloudTrail console only shows management events. It does not show data events, Insights events, or network activity events.
   > - The event history is limited to the past 90 days of events. For an ongoing record of events in your AWS account, create an event data store or a trail.
- [Creating a trail for an organization](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html)
  > If you have created an organization in AWS Organizations, you can create a trail that logs all events for all AWS accounts in that organization. This is sometimes called an organization trail.
- [Working with CloudTrail trails](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-trails.html)
  > Trails capture a record of AWS activities, delivering and storing these events in an Amazon S3 bucket, with optional delivery to CloudWatch Logs and Amazon EventBridge.
- [Tutorial: Create an EventBridge rule that reacts to AWS API calls via CloudTrail](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-log-api-call.html)
- [Logging data events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-data-events-with-cloudtrail.html)
  - Examples: Logging data events for Amazon S3 objects
- [Sending events to CloudWatch Logs](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/send-cloudtrail-events-to-cloudwatch-logs.html)

## EventBridge
- [What Is Amazon EventBridge?](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html)
- [Event buses in Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-bus.html)
- [Amazon EventBridge Pipes](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-pipes.html)
- [Events in Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-events.html)
- [EventBridge is the evolution of Amazon CloudWatch Events](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-cwe-now-eb.html)
- [Receiving events from a SaaS partner with Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-saas.html)
- [Deprecated: How do I use Lambda to stop and start Amazon EC2 instances at regular intervals?](https://repost.aws/knowledge-center/start-stop-lambda-eventbridge)
  - Alternative: [Instance scheduler Automate starting and stopping AWS instances](https://docs.aws.amazon.com/solutions/latest/instance-scheduler-on-aws/solution-overview.html)
  -  - Alternative: [AWS Systems Manager | Stop and start EC2 instances automatically on a schedule using Quick Setup](https://docs.aws.amazon.com/systems-manager/latest/userguide/quick-setup-scheduler.html)

## AWS Organizations
### Authoriztion Policies in AWS Organizations
- [Authorization policies in AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_authorization_policies.html)
#### Scp
- [Service control policies (SCPs)](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)

  SCPs do not grant permissions to the IAM users and IAM roles in your organization. No permissions are granted by an SCP. An SCP defines a permission guardrail, or sets limits, on the actions that the IAM users and IAM roles in your organization can perform. 
  
  - SCPs affect only member accounts in the organization. They have no effect on users or roles in the management account.
  - Users and roles must still be granted permissions with appropriate IAM permission policies. A user without any IAM permission policies has no access, even if the applicable SCPs allow all services and all actions.
  - If a user or role has an IAM permission policy that grants access to an action that is also allowed by the applicable SCPs, the user or role can perform that action.
  - If a user or role has an IAM permission policy that grants access to an action that is either not allowed or explicitly denied by the applicable SCPs, the user or role can't perform that action.
  - SCPs affect all users and roles in attached accounts, including the root user. The only exceptions are those described in Tasks and entities not restricted by SCPs.
  - SCPs do not affect any service-linked role. Service-linked roles enable other AWS services to integrate with AWS Organizations and can't be restricted by SCPs.
- [SCP evaluation](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_evaluation.html)
- [Service control policy examples](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
#### Rcp
- [Resource control policies (RCPs)](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_rcps.html)
  
  RCPs alone are not sufficient in granting permissions to the resources in your organization. No permissions are granted by an RCP. An RCP defines a permissions guardrail, or sets limits, on the actions that identities can take on resources in your organizations.

### Management Policies in AWS Organizations
- [Management policies in AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_management_policies.html)

### Account management
- [How do I move an account from an existing AWS Organization to another AWS Organization?](https://repost.aws/knowledge-center/organizations-move-accounts)
  > - Use the AWS Organizations console if you have only a few accounts to migrate.
  > - If you're migrating many accounts, then use the AWS Organizations API or AWS Command Line Interface (AWS CLI) to move the accounts instead.
  >
  > In either case, perform these actions for each member account:
  > 1. Remove the member account from the old organization.
  > 2. Send an invite to the member account from the new organization.
  > 3. Accept the invite to the new organization from the member account.
  >
  > To join the old organization's management account to the new organization, complete the following steps:
  > 1. Remove the member accounts from the organization.
  > 2. Delete the old organization.
  > 3. Invite the old management account to the new organization as a member account.

- [How to Use AWS Organizations to Automate End-to-End Account Creation](https://aws.amazon.com/blogs/security/how-to-use-aws-organizations-to-automate-end-to-end-account-creation/)
  > - AWS Organizations API to create accounts
  > - CloudFormation to configure accounts
- [An easier way to control access to AWS resources by using the AWS organization of IAM principals](https://aws.amazon.com/blogs/security/control-access-to-aws-resources-by-using-the-aws-organization-of-iam-principals/)
  > AWS Identity and Access Management (IAM) now makes it easier for you to control access to your AWS resources by using the AWS organization of IAM principals (users and roles). For some services, you grant permissions using resource-based policies to specify the accounts and principals that can access the resource and what actions they can perform on it. Now, you can use a new condition key, `aws:PrincipalOrgID`, in these policies to require all principals accessing the resource to be from an account (including the master account) in the organization. For example, let’s say you have an Amazon S3 bucket policy and you want to restrict access to only principals from AWS accounts inside of your organization. To accomplish this, you can define the `aws:PrincipalOrgID` condition and set the value to your organization ID in the bucket policy.

### Resource Access Manager
- [What is AWS Resource Access Manager?](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html)
  > AWS Resource Access Manager (AWS RAM) helps you securely share your resources across AWS accounts, within your organization or organizational units (OUs), and with AWS Identity and Access Management (IAM) roles and users for supported resource types.
- [New AWS Resource Access Manager – Cross-Account Resource Sharing](https://aws.amazon.com/blogs/aws/new-aws-resource-access-manager-cross-account-resource-sharing/)
- [Shareable AWS resources](https://docs.aws.amazon.com/ram/latest/userguide/shareable.html)

## AWS Config
- [What Is AWS Config?](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)
- [How AWS Config Works](https://docs.aws.amazon.com/config/latest/developerguide/how-does-config-work.html)
- [AWS Config Managed rules](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html)
  > AWS Config provides AWS managed rules, which are predefined, customizable rules that AWS Config uses to evaluate whether your AWS resources comply with common best practices. For example, you could use a managed rule to quickly start assessing whether your Amazon Elastic Block Store (Amazon EBS) volumes are encrypted or whether specific tags are applied to your resources.
  >
  > You can customize the rule's parameters to define attributes that your resources must have to comply with the rule. For example, you can customize a parameter to specify that your security group should block incoming traffic to a specific port number.
  - [access-keys-rotated](https://docs.aws.amazon.com/config/latest/developerguide/access-keys-rotated.html)
  - [required-tags](https://docs.aws.amazon.com/config/latest/developerguide/required-tags.html)
  - [acm-certificate-expiration-check](https://docs.aws.amazon.com/config/latest/developerguide/acm-certificate-expiration-check.html)
- [Service-Linked AWS Config Rules](https://docs.aws.amazon.com/config/latest/developerguide/service-linked-awsconfig-rules.html)
- [Conformance Packs for AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/conformance-packs.html)
- [Remediating Noncompliant Resources with AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/remediation.html)
  > AWS Config allows you to remediate noncompliant resources that are evaluated by AWS Config Rules. AWS Config applies remediation using AWS Systems Manager Automation documents. These documents define the actions to be performed on noncompliant AWS resources evaluated by AWS Config Rules.
- [Monitoring AWS Config with Amazon EventBridge](https://docs.aws.amazon.com/config/latest/developerguide/monitor-config-with-cloudwatchevents.html)
  > Amazon EventBridge delivers a near real-time stream of system events that describe changes in AWS resources. Use Amazon EventBridge to detect and react to changes in the status of AWS Config events.
  >
  > You can create a rule that runs whenever there is a state transition, or when there is a transition to one or more states that are of interest. Then, based on rules you create, Amazon EventBridge invokes one or more target actions when an event matches the values you specify in a rule. Depending on the type of event, you might want to send notifications, capture event information, take corrective action, initiate events, or take other actions.
- [AWS Config events](https://docs.aws.amazon.com/eventbridge/latest/ref/events-ref-config.html)
  > AWS Config sends service events directly to EventBridge, as well as via AWS CloudTrail.
  >
  > AWS Config sends the following events directly to EventBridge:
  > - Config Rules Compliance Change
  > - Config Rules Re-evaluation Status
  >
  > To CloudTrail, it sends management API calls made directly to the AWS Config service itself.


## AWS Control Tower
- [What Is AWS Control Tower?](https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html)
  - Landing Zone
  - Controls
    > A control (sometimes called a guardrail) is a high-level rule that provides ongoing governance for your overall AWS environment. It's expressed in plain language. Three kinds of controls exist: *preventive*, *detective*, and *proactive*. Three categories of guidance apply to controls: *mandatory*, *strongly recommended*, or *elective*.
  - Account Factory
  - Dashboard
- [Control behavior and guidance](https://docs.aws.amazon.com/controltower/latest/controlreference/control-behavior.html)
  > **Control behavior**
  > - **Preventive** – A preventive control ensures that your accounts maintain compliance, because it disallows actions that lead to policy violations.
  > - **Detective** – A detective control detects noncompliance of resources within your accounts, such as policy violations, and provides alerts through the dashboard. The status of a detective control is either clear, in violation, or not enabled.
  > - **Proactive** – A proactive control scans your resources before they are provisioned, and makes sure that the resources are compliant with that control. Resources that are not compliant will not be provisioned. Proactive controls are implemented by means of AWS CloudFormation hooks, and they apply to resources that would be provisioned by AWS CloudFormation
  > 
  > **Implementation of control behavior**
  > - The preventive controls are implemented using Service Control Policies (SCPs), which are part of AWS Organizations.
  > - The detective controls are implemented using AWS Config rules.
  > - The proactive controls are implemented using AWS CloudFormation hooks.
- [How controls work](https://docs.aws.amazon.com/controltower/latest/userguide/how-controls-work.html)
  > For those who are familiar with AWS: 
  > - In AWS Control Tower preventive controls are implemented with service control policies (SCPs) and resource control policies (RCPs). 
  > - Detective controls are implemented with AWS Config rules.
  > - Proactive controls are implemented with AWS CloudFormation hooks.



## Systems Manager
- [What is AWS Systems Manager?](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html)
  > **What are the main features of Systems Manager?**
  >
  > The primary features of Systems Manager are shared between the unified console and the individual tools Systems Manager provides to help you manage nodes at scale.
  >
  > **Unified console**
  >
  > The unified console provides a centralized experience to view and manage your nodes. This console leverages several Systems Manager tools and more to provide you with the following:
  > - Centralized views of your nodes
  > - Detailed node insights
  > - Automated diagnosis and remediation of common node issues
  > 
  > For more information about the unified console, see What is the unified console?.
  >
  > **Tools**
  >
  > Tools consist of the individual capabilities of Systems Manager and their features such as Run Command, Session Manager, Automation, and Parameter Store. With Systems Manager tools you can do the following:
  > - Patch nodes at scale
  > - Securely connect to nodes without opening inbound ports
  > - Run commands remotely on nodes
  > - Securely store data referenced by applications
  > - Automate common systems administration tasks
  >
  > For more information about Systems Manager tools, see Using AWS Systems Manager tools.
- [What is the unified console?](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-unified-console.html)
- [Using AWS Systems Manager tools](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-tools.html)
  
- [AWS Systems Manager Node Management](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-instances-and-nodes.html)
  - Compliance
  - Distributor
    > Distributor, a tool in AWS Systems Manager, helps you package and publish software to AWS Systems Manager managed nodes. You can package and publish your own software or use Distributor to find and publish AWS-provided agent software packages, such as AmazonCloudWatchAgent, or third-party packages such as Trend Micro. Publishing a package advertises specific versions of the package's document to managed nodes that you identify using node IDs, AWS account IDs, tags, or an AWS Region.
    - [Install or update Distributor packages](https://docs.aws.amazon.com/systems-manager/latest/userguide/distributor-working-with-packages-deploy.html)
      > **Installing or updating a package one time**
      >
      > Uses **Run Command** with the command document AWS-ConfigureAWSPackage and your Distributor package already selected.
      >
      > **Scheduling a package installation or update**
      >
      >  Install on a schedule This command opens **State Manager**
  - Fleet Manager
  - Hybrid Activations
  - Inventory
  - **[Patch Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/patch-manager.html)**
    > You can use Patch Manager to apply patches for both operating systems and applications. (On Windows Server, application support is limited to updates for applications released by Microsoft.) You can use Patch Manager to install Service Packs on Windows nodes and perform minor version upgrades on Linux nodes.
  - **Run Command**
  - **[Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)**
  - **[State Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-state.html)**
    > State Manager, a tool in AWS Systems Manager, is a secure and scalable configuration management service that automates the process of keeping your managed nodes and other AWS resources in a state that you define.
    >
    > **State Manager associations**
    >
    > A State Manager association is a configuration that you assign to your AWS resources. The configuration defines the state that you want to maintain on your resources. For example, an association can specify that antivirus software must be installed and running on a managed node, or that certain ports must be closed.
    >
    > **Flexible scheduling options**
    >
    > Immediate or delayed processing
    - [Understanding how State Manager works](https://docs.aws.amazon.com/systems-manager/latest/userguide/state-manager-about.html)

- [AWS Systems Manager Change Management](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-actions-and-change.html)
  - Automation
  - Change Calendar
  - Change Manager
  - Documents
    > A Systems Manager document (SSM document) defines the actions that Systems Manager performs. SSM document types include Command documents, which are used by State Manager and Run Command, and Automation runbooks, which are used by Systems Manager Automation. Systems Manager includes dozens of pre-configured documents that you can use by specifying parameters at runtime. Documents can be expressed in JSON or YAML, and include steps and parameters that you specify.
  - Maintenance Windows
  - Quick Setup

- [AWS Systems Manager Application Management](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-application-management.html)
  - AppConfig
  - Application Manager
  - **Parameter Store**
  
- [AWS Systems Manager operations tools](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-ops-center.html)
  - CloudWatch Dashboards
  - Explorer
  - Incident Manager
  - OpsCenter

  Examples:https://docs.aws.amazon.com/aurora-dsql/latest/userguide/what-is-aurora-dsql.html
  - [Patching your Windows EC2 instances using AWS Systems Manager Patch Manager](https://aws.amazon.com/blogs/mt/patching-your-windows-ec2-instances-using-aws-systems-manager-patch-manager/)
  
  
## Configuration 
- [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)
  > You can use Parameter Store parameters with other Systems Manager tools and AWS services to retrieve secrets and configuration data from a central store. Parameters work with Systems Manager tools such as Run Command, Automation, and State Manager, tools in AWS Systems Manager. You can also reference parameters in a number of other AWS services, including the following:
  > - Amazon Elastic Compute Cloud (Amazon EC2)
  > - Amazon Elastic Container Service (Amazon ECS)
  > - AWS Secrets Manager
  > - AWS Lambda
  > - AWS CloudFormation
  > - AWS CodeBuild
  > - AWS CodePipeline
  > - AWS CodeDeploy
- [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)
  > Newer service. Supports key rotation 
  >
  > To implement password rotation lifecycles, use AWS Secrets Manager. You can rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle using Secrets Manager. 
  >
  > Reddit: 
  > I wrote the original launch post for secrets manager.
  > 
  > I remember raising the issue of the service’s similarity to parameter store, to the product manager of Secrets Manager, and then being told "no, it's completely different..."
  >
  > So then I showed a code sample of using the two services... and then a table comparing everything. Still nothing. The launch was going to happen no matter what anyone said.
  > 
  > I can see why you'd want a secrets manager service specifically and it's in a better place in 2021 than it was in 2018... but they launched way too early and at way too high of a price point.
- [AWS Secrets Manager: Store, Distribute, and Rotate Credentials Securely](https://aws.amazon.com/blogs/aws/aws-secrets-manager-store-distribute-and-rotate-credentials-securely/)
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
  >
  > **Foundational threat detection** - When you enable GuardDuty in an AWS account, GuardDuty automatically starts ingesting the foundational data sources associated with that account. These data sources include
  > - AWS CloudTrail management events
  > - VPC flow logs (from Amazon EC2 instances)
  > - DNS logs.
  >
  > **Extended Threat Detection** – This capability detects multi-stage attacks that span foundational data source  
  >
  > **Use-case focused GuardDuty protection plans**
  >
  > - S3 Protection (S3 data access events and S3 configurations)
  > - EKS Protection (Amazon EKS cluster control plane activity by analyzing Amazon EKS audit logs.)
  > - Runtime Monitoring (on-host, operating system-level activity)
  > - Malware Protection for EC2
  > - Malware Protection for S3
  > - RDS Protection
  - Lambda Protection
- [Creating custom responses to GuardDuty findings with Amazon CloudWatch Events](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings_cloudwatch.html)
  > GuardDuty creates an event for Amazon CloudWatch Events when any change in findings takes place. Finding changes that will create a CloudWatch event include newly generated findings or newly aggregated findings. Events are emitted on a best effort basis.
- [GuardDuty finding types](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_finding-types-active.html)
  - [GuardDuty EC2 finding types](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_finding-types-ec2.html)
    - [An EC2 instance is querying a domain name that is associated with cryptocurrency-related activity.](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_finding-types-ec2.html#cryptocurrency-ec2-bitcointoolbdns)

## Inspector
- [Amazon Inspector - Automated vulnerability management](https://aws.amazon.com/inspector/)
  > Inspector is focused on identifying vulnerabilities and compliance issues, which can help prevent attacks, but it does not detect or alert on active threats.
- [Amazon Inspector Overview Demo](https://www.youtube.com/watch?v=Nx8s7lwapoE)

## License Manager
- [What is AWS License Manager?](https://docs.aws.amazon.com/license-manager/latest/userguide/license-manager.html)
- [How License Manager works](https://docs.aws.amazon.com/license-manager/latest/userguide/license-manager-overview.html)

## Service Catalog
- [AWS Service Catalog | Manage IaC templates](https://aws.amazon.com/servicecatalog/)


# ML
- [Amazon Comprehend - NLP](https://aws.amazon.com/comprehend/)
- [Amazon Kendra - Enterprise Search Engine](https://aws.amazon.com/kendra/)
- [What is Amazon Macie?](https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html)
- [Types of Amazon Macie findings](https://docs.aws.amazon.com/macie/latest/user/findings-types.html)
  - SensitiveData:S3Object/Credentials
  - SensitiveData:S3Object/CustomIdentifier
  - SensitiveData:S3Object/Financial
  - SensitiveData:S3Object/Multiple
  - SensitiveData:S3Object/Personal
    > The object contains sensitive personal information—personally identifiable information (PII) such as passport numbers or driver's license identification numbers, personal health information (PHI) such as health insurance or medical identification numbers, or a combination of PII and PHI.
- [Automating the analysis of multi-speaker audio files using Amazon Transcribe and Amazon Athena](https://aws.amazon.com/blogs/machine-learning/automating-the-analysis-of-multi-speaker-audio-files-using-amazon-transcribe-and-amazon-athena/)
- [Amazon Textract](https://aws.amazon.com/textract/)