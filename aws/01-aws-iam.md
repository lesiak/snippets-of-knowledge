# IAM
- [Identity-based policies and resource-based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)
- [Permissions boundaries for IAM entities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)
  - Gotcha: They can only be applied to roles or users, not IAM groups.
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
  - Properties of the principal
    - aws:PrincipalArn
    - aws:PrincipalAccount
    - aws:PrincipalOrgPaths
    - [aws:PrincipalOrgID](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html#condition-keys-principalorgid)
    - aws:PrincipalTag/tag-key
    - aws:PrincipalIsAWSService
    - aws:PrincipalServiceName
    - aws:PrincipalServiceNamesList
    - aws:PrincipalType
    - aws:userid
    - aws:username
  - Properties of a role session
  - Properties of the network
    - aws:SourceIp
    - aws:SourceVpc
    - aws:SourceVpce
    - aws:VpcSourceIp
  - Properties of the resource 
  - Properties of the request 
    - aws:RequestedRegion
    - aws:SourceAccount
    - aws:SourceOrgID
  
- [Controlling access to and for IAM users and roles using tags | PrincipalTag](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html)
- [How can I use IAM roles to restrict API calls from specific IP addresses to the AWS Management Console?](https://repost.aws/knowledge-center/iam-restrict-calls-ip-addresses)
- [Setting an account password policy for IAM users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html?icmpid=docs_iam_console)
- [Permit IAM users to change their own passwords](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_enable-user-change.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
  - Role
    > Roles can be assumed by the following:
    > - An IAM user in the same AWS account or another AWS account
    > - IAM roles in the same account
    > - Service principals, for use with AWS services and features like:
    > - Services that allow you to run code on compute services, like Amazon EC2 or AWS Lambda
    > - Features that perform actions to your resources on your behalf, like Amazon S3 object replication
    >  - Services that deliver temporary security credentials to your applications that run outside of AWS, such as IAM Roles Anywhere or Amazon ECS Anywhere
    > - An external user authenticated by an external identity provider (IdP) service that is compatible with SAML 2.0 or OpenID Connect
  - AWS service role
    > A service role is an IAM role that a service assumes to perform actions on your behalf.
  - AWS service-linked role
    > A service-linked role is a type of service role that is linked to an AWS service.
  > When a user assumes a role in AWS, the process involves the following steps:  
  > 1. AssumeRole API Call: The user makes an AssumeRole API call to AWS Security Token Service (STS). This call includes the ARN of the role to be assumed and optionally a session name and external ID.  
  > 2. Temporary Security Credentials: AWS STS returns a set of temporary security credentials (access key ID, secret access key, and session token) that the user can use to make AWS service requests.  
  > 3. Session Context: These temporary credentials include information about the assumed role, such as the role ARN and the session name. This information is embedded in the session token.  
  > 4. Request Signing: When the user makes requests to AWS services using the temporary credentials, the requests are signed with the session token. AWS services can decode the session token to determine the role being assumed.  
  > 5. Access Control: AWS services use the role's permissions to authorize the requests. The user's original permissions are not considered while they are acting under the assumed role.  
  > Here is an example of how a user might assume a role using the AWS SDK for Python (Boto3):
  > ```
  > import boto3
  > 
  > # Create an STS client
  > sts_client = boto3.client('sts')
  > 
  > # Assume a role
  > response = sts_client.assume_role(
  >  RoleArn='arn:aws:iam::123456789012:role/example-role',
  >  RoleSessionName='example-session'
  > )
  >
  > # Extract the temporary credentials
  > credentials = response['Credentials']
  > 
  > # Use the temporary credentials to create a new session
  > session = boto3.Session(
  >    aws_access_key_id=credentials['AccessKeyId'],
  >    aws_secret_access_key=credentials['SecretAccessKey'],
  >    aws_session_token=credentials['SessionToken']
  > )
  >
  > # Use the session to make requests to AWS services
  > s3_client = session.client('s3')
  > response = s3_client.list_buckets()
  > print(response)
  > ```
- [Policy summaries](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_understand.html)
- [AWS IAM Access Analyzer](https://aws.amazon.com/iam/access-analyzer/)
- [AWS account root user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html)
  - [Tasks that require root user credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html#root-user-tasks)