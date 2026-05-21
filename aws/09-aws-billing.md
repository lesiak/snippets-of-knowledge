# Billing and Pricing

### Billing dashboard/bills
- [Using the AWS Billing and Cost Management home page](https://docs.aws.amazon.com/cost-management/latest/userguide/view-billing-dashboard.html)
> The data on this page comes from AWS Cost Explorer. If you haven’t used Cost Explorer before, it’s automatically enabled for you once you visit this page. 
>
> You can use the following widgets:
> - Cost summary (with forecasting for current month)
> - Cost monitor (quick view of your cost and usage budgets and any cost anomalies that AWS detected)
> - Cost breakdown
> - Recommended actions
> - Savings opportunities
> - Top trends

| Data field                      | Period  | Output      | Use for                |
|---------------------------------|---------|-------------|------------------------|
| AWS account ID                  | Monthly | PDF and CSV | Simple monthly reports |
| Service (EC2)                   |         |             |                        |
| Usage Type (BoxUsage:t3:large)  |         |             |                        |
| Operation (Runinstance)         |         |             |                        |
| Item Description (OS & Pricing) |         |             |                        |
| Usage Quantity                  |         |             |                        |
| Cost                            |         |             |                        |

### AWS Cost Explorer
- [Analyzing your costs and usage with AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)
> AWS Cost Explorer is a tool that enables you to view and analyze your costs and usage. You can explore your usage and costs using the main graph, the Cost Explorer cost and usage reports, or the Cost Explorer RI reports. You can view data for up to the last 13 months, forecast how much you're likely to spend for the next 12 months, and get recommendations for what Reserved Instances to purchase. You can use Cost Explorer to identify areas that need further inquiry and see trends that you can use to understand your costs.
>
> You can view your costs and usage using the Cost Explorer user interface free of charge. You can also access your data programmatically using the Cost Explorer API. Each paginated API request incurs a charge of $0.01. You can't disable Cost Explorer after you enable it.
>
> In addition, Cost Explorer provides preconfigured views that display at-a-glance information about your cost trends and give you a head start on customizing views that suit your needs.

| Data field                 | Period              | Output               | Use for                    |
|----------------------------|---------------------|----------------------|----------------------------|
| All fields from Bills File | Monthly (Last 12 M) | Billing Dashboard UI | Daily/weekly cost tracking |
| User Defined Tags          | Daily               | CSV (no programatic access)        | Leverage Cost Awareness    |
| API Operation              |                     | Cost Explorer API    | Trend and Budget analysis  |
| Region A/Z                 |                     |                      |                            |
| Platform (OS)              |                     |                      |                            |
| Purchase Option            |                     |                      |                            |
| Tenancy                    |                     |                      |                            |

- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
- [AWS Cost Explorer Video](https://www.youtube.com/watch?v=xTIR5cvOfPc)
- [AWS Cost Explorer API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_Operations_AWS_Cost_Explorer_Service.html)

### Cost and Usage Report
- [What are AWS Cost and Usage Reports?](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)
> AWS Cost and Usage Reports (AWS CUR) contains the most comprehensive set of cost and usage data available. You can use Cost and Usage Reports to publish your AWS billing reports to an Amazon Simple Storage Service (Amazon S3) bucket that you own. You can receive reports that break down your costs by the hour, day, or month, by product or product resource, or by tags that you define yourself. AWS updates the report in your bucket once a day in comma-separated value (CSV) format.

| Data field                 | Period | Output | Use for                |
|----------------------------|--------|--------|------------------------|
| All fields from Bills File | Hourly | S3     | Hourly/Daily reporting |
| Resource-id                | Daily  |        |                        |
| API Operation              |        |        |                        |
| Region A/Z                 |        |        |                        |
| Platform (OS)              |        |        |                        |
| Purchase Option            |        |        |                        |
| Tenancy                    |        |        |                        |

- [AWS Compute Optimizer FAQs](https://aws.amazon.com/compute-optimizer/faqs/)
  > AWS Compute Optimizer helps you identify the optimal AWS resource configurations, such as Amazon Elastic Compute Cloud (EC2) instance types, Amazon Elastic Block Store (EBS) volume configurations, task sizes of Amazon Elastic Container Service (ECS) services on AWS Fargate, commercial software licenses, AWS Lambda function memory sizes, and Amazon Relational Database Service (RDS) DB instance classes, using machine learning to analyze historical utilization metrics. Compute Optimizer provides a set of APIs and a console experience to help you reduce costs and increase workload performance by recommending the optimal AWS resources for your AWS workloads.
- [Configuring AWS Budgets actions](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-controls.html)
  > AWS Budgets is a tool that enables you to set custom cost and usage budgets. You can set your budget amount, and AWS provides you with estimated charges and forecasted costs for your AWS usage. Configuring the budgets in the Billing and Cost Management console is a recommended step.
  >
  > AWS Budgets can execute budget actions (like preventing additional resource provisioning) using an IAM role with the necessary permissions.
  > 
  > Configuring alerts in AWS Budgets and linking a budget action to an IAM role for automatic prevention of additional resource provisioning is a correct and efficient way to manage costs.
- [Reserved Instances and Savings Plans discount sharing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ri-turn-off.html)
- [AWS Trusted Advisor check reference](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor-check-reference.html)
   - Cost optimization
   - Performance
   - Security
   - Fault tolerance
   - Service limits
   - Operational Excellence

# Architecture & Design
- [Rapidly recover mission-critical systems in a disaster](https://aws.amazon.com/blogs/publicsector/rapidly-recover-mission-critical-systems-in-a-disaster/)
- [A Beginner's Guide to Scaling to 11 Million+ Users on Amazon's AWS](https://highscalability.com/a-beginners-guide-to-scaling-to-11-million-users-on-amazons/)
- [Creating Your Own EC2 Spot Market](https://netflixtechblog.com/creating-your-own-ec2-spot-market-6dd001875f5)
- [Creating Your Own EC2 Spot Market — Part 2](https://netflixtechblog.com/creating-your-own-ec2-spot-market-part-2-106e53be9ed7)
