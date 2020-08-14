# Describe Cloud Concepts (15-20%)

### Describe the benefits and considerations of using cloud services
- describe terms such as High Availability, Scalability, Elasticity, Agility, Fault Tolerance, and Disaster Recovery
- describe the principles of economies of scale
   - Microsoft Learn: [Economies of scale](https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing/3b-economies-of-scale)
- describe the differences between Capital Expenditure (CapEx) and Operational Expenditure (OpEx)
   - Microsort Learn: [Capital expenditure (CapEx) versus operational expenditure (OpEx)](https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing/3c-capex-vs-opex)
- describe the consumption-based model

### Describe the differences between Infrastructure-as-a-Service (IaaS), Platform-as-a-Service (PaaS) and Software-as-a-Service (SaaS)
- describe Infrastructure-as-a-Service (IaaS)
   - [What is IaaS?](https://azure.microsoft.com/en-gb/overview/what-is-iaas/)
   - [Azure infrastructure as a service (IaaS)](https://azure.microsoft.com/en-gb/overview/what-is-azure/iaas/#overview)
- describe Platform-as-a-Service (PaaS)
   - [What is PaaS?](https://azure.microsoft.com/en-gb/overview/what-is-paas/)
- describe Software-as-a-Service (SaaS)
   - [What is SaaS?](https://azure.microsoft.com/en-gb/overview/what-is-saas/)
- compare and contrast the three different service types

### Describe the differences between Public, Private and Hybrid cloud models
- describe Public cloud
- describe Private cloud
- describe Hybrid cloud
- compare and contrast the three different cloud models
   - [What are public, private, and hybrid clouds?](https://azure.microsoft.com/en-us/overview/what-are-private-public-hybrid-clouds/)

# Describe Core Azure Services (30-35%)
### Describe the core Azure architectural components
- describe Regions
   - [Azure global infrastructure](https://azure.microsoft.com/en-us/global-infrastructure/)
   - [Azure regions](https://azure.microsoft.com/en-us/global-infrastructure/regions/)
- describe Availability Zones
   - [Regions and Availability Zones in Azure](https://docs.microsoft.com/en-us/azure/availability-zones/az-overview)
- describe Resource Groups
- describe Azure Resource Manager
   - [What is Azure Resource Manager?](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/overview)
   - [What are ARM templates?](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/overview)
   - Extra: [Azure resource providers and types](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/resource-providers-and-types)
   - Extra: [Move resources to a new resource group or subscription](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/move-resource-group-and-subscription)
- describe the benefits and usage of core Azure architectural components
   - [Azure Resource Manager vs. classic deployment: Understand deployment models and the state of your resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/deployment-models)

### Describe some of the core products available in Azure
- describe products available for Compute such as Virtual Machines, Virtual Machine Scale Sets, App Services, Azure Container Instances (ACI) and Azure Kubernetes Service (AKS)
   - [Windows virtual machines in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/overview)
   - [Linux virtual machines in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/overview)
   - [What are virtual machine scale sets?](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview)
   - [App Service overview](https://docs.microsoft.com/en-us/azure/app-service/overview)
   - [Introduction to Azure App Service on Linux](https://docs.microsoft.com/en-us/azure/app-service/containers/app-service-linux-intro)
   - [Azure App Service plan overview](https://docs.microsoft.com/en-us/azure/app-service/overview-hosting-plans)
   - [Scale up an app in Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/manage-scale-up)
   - [Get started with Autoscale in Azure](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/autoscale-get-started)
   - [App Service pricing](https://azure.microsoft.com/en-gb/pricing/details/app-service/windows/)
   - [What is Azure Container Instances?](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-overview)
   - [Choose an Azure compute service for your application](https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)
   - [Kubernetes core concepts for Azure Kubernetes Service (AKS)](https://docs.microsoft.com/en-us/azure/aks/concepts-clusters-workloads)
   - [Azure Kubernetes Service (AKS)](https://docs.microsoft.com/en-us/azure/aks/intro-kubernetes)
   - [Introduction to private Docker container registries in Azure](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-intro)
- describe products available for Networking such as Virtual Network, Load Balancer, VPN Gateway, Application Gateway and Content Delivery Network
   - [What is Azure Virtual Network?](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview)
   - [Overview of load-balancing options in Azure](https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/load-balancing-overview)
   - [What is Azure Load Balancer?](https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-overview)
   - [What is Azure Application Gateway?](https://docs.microsoft.com/en-us/azure/application-gateway/overview)
   - [Azure Application Gateway features](https://docs.microsoft.com/en-us/azure/application-gateway/features)
   - [What is Traffic Manager?](https://docs.microsoft.com/en-us/azure/traffic-manager/traffic-manager-overview)
   - [About Point-to-Site VPN](https://docs.microsoft.com/en-us/azure/vpn-gateway/point-to-site-about)
   - [What is VPN Gateway?](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways)
   - [VPN Gateway design](https://docs.microsoft.com/en-us/azure/vpn-gateway/design)
   - [Virtual network peering](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview)
   - [ExpressRoute overview](https://docs.microsoft.com/en-us/azure/expressroute/expressroute-introduction)
   - [What is a content delivery network on Azure?](https://docs.microsoft.com/en-us/azure/cdn/cdn-overview)
- describe products available for Storage such as Blob Storage, Disk Storage, File Storage, and Archive Storage
   - [What is Azure Blob storage?](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview)
   - [Introduction to Azure Blob storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction)
   - [Azure Blob storage: hot, cool, and archive access tiers](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-storage-tiers?tabs=azure-portal)
   - [What is Azure Files?](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction)
   - [Introduction to Azure managed disks](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/managed-disks-overview)
- describe products available for Databases such as Cosmos DB, Azure SQL Database, Azure Database for MySQL, Azure Database for PostgreSQL, Azure Database Migration service
   - [Welcome to Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction)
   - [What is Azure SQL Database?](https://docs.microsoft.com/en-us/azure/azure-sql/database/sql-database-paas-overview)
   - [What is Azure SQL Managed Instance?](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview)
   - [What is Azure Database for MySQL?](https://docs.microsoft.com/en-us/azure/mysql/overview)
   - [What is Azure Database for PostgreSQL?](https://docs.microsoft.com/en-us/azure/postgresql/overview)
   - [What is Azure Database Migration Service?](https://docs.microsoft.com/en-us/azure/dms/dms-overview)
- describe the Azure Marketplace and its usage scenarios

### Describe some of the solutions available on Azure
- describe Internet of Things (IoT) and products that are available for IoT on Azure such as IoT Hub and IoT Central
   - [Azure technologies and services for creating IoT solutions](https://docs.microsoft.com/en-us/azure/iot-fundamentals/iot-services-and-technologies)
   - [What is Azure IoT Hub?](https://docs.microsoft.com/en-us/azure/iot-hub/about-iot-hub)
   - [What is Azure IoT Central?](https://docs.microsoft.com/en-us/azure/iot-central/core/overview-iot-central)
   - [Take a tour of the Azure IoT Central UI](https://docs.microsoft.com/en-us/azure/iot-central/core/overview-iot-central-tour)
   - [What is Azure IoT Edge](https://docs.microsoft.com/en-us/azure/iot-edge/about-iot-edge)
- describe Big Data and Analytics and products that are available for Big Data and Analytics such as Azure Synapse Analytics, HDInsight, and Azure Databricks
   - [What is Azure Synapse Analytics (formerly SQL DW)?](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is)
   - [Azure Synapse Analytics (formerly SQL DW) architecture](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql-data-warehouse/massively-parallel-processing-mpp-architecture)
   - [What is PolyBase?](https://docs.microsoft.com/en-us/sql/relational-databases/polybase/polybase-guide?view=azure-sqldw-latest)
   - [Introduction to Azure Data Lake Storage Gen2](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction)
   - [What is Azure HDInsight?](https://docs.microsoft.com/en-us/azure/hdinsight/hdinsight-overview)
   - [What is Azure Databricks?](https://docs.microsoft.com/en-us/azure/databricks/scenarios/what-is-azure-databricks)
   - [Azure Event Hubs — A big data streaming platform and event ingestion service](https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about)
   - [What is Azure Stream Analytics?](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction)
- describe Artificial Intelligence (AI) and products that are available for AI such as Azure Machine Learning Service and Studio
   - [What is Azure Machine Learning?](https://docs.microsoft.com/en-gb/azure/machine-learning/overview-what-is-azure-ml)
   - [Azure Machine Learning vs Machine Learning Studio (classic)](https://docs.microsoft.com/en-gb/azure/machine-learning/compare-azure-ml-to-studio-classic)
   - [What are Azure Cognitive Services?](https://docs.microsoft.com/en-gb/azure/cognitive-services/welcome)
   - [About Azure Bot Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-overview-introduction)
- describe Serverless computing and Azure products that are available for serverless computing such as Azure Functions, Logic Apps, and Event Grid
   - [An introduction to Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview)
   - [Overview - What is Azure Logic Apps?](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
   - [Connectors for Azure Logic Apps](https://docs.microsoft.com/en-us/azure/connectors/apis-list)
   - [What is Azure Event Grid?](https://docs.microsoft.com/en-us/azure/event-grid/overview)
   - [Choose between Azure messaging services - Event Grid, Event Hubs, and Service Bus](https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services)
   - [Events, Data Points, and Messages - Choosing the right Azure messaging service for your data](https://azure.microsoft.com/en-us/blog/events-data-points-and-messages-choosing-the-right-azure-messaging-service-for-your-data/)
- describe DevOps solutions available on Azure such as Azure DevOps and Azure DevTest Labs
   - [What is Azure DevOps?](https://docs.microsoft.com/en-us/azure/devops/user-guide/what-is-azure-devops?view=azure-devops)
   - [What features and services do I get with Azure DevOps?](https://docs.microsoft.com/en-us/azure/devops/user-guide/services?view=azure-devops)
   - [What is Azure Repos?](https://docs.microsoft.com/en-us/azure/devops/repos/get-started/what-is-repos?view=azure-devops) 
   - [What is Azure Pipelines?](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops)
   - [What is Azure Boards?](https://docs.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops&tabs=agile-process)
   - [Exploratory and manual testing scenarios and capabilities](https://docs.microsoft.com/en-us/azure/devops/test/overview?view=azure-devops)
   - [What is Azure Artifacts?](https://docs.microsoft.com/en-us/azure/devops/artifacts/overview?view=azure-devops)
   - [About Azure DevTest Labs](https://docs.microsoft.com/en-us/azure/devtest-labs/devtest-lab-overview)
- describe the benefits and outcomes of using Azure solutions

### Describe Azure management tools
- describe Azure tools such as Azure Portal, Azure PowerShell, Azure CLI and Cloud Shell
- describe Azure Advisor
   - [Introduction to Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-overview)
   - [Improve the reliability of your application by using Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-high-availability-recommendations)
   - [Make resources more secure with Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-security-recommendations)
   - [Improve the performance of Azure applications by using Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-performance-recommendations)
   - [Reduce service costs by using Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-cost-recommendations)
   - [Achieve operational excellence by using Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-operational-excellence-recommendations)

# Describe Security, Privacy, Compliance, and Trust (25-30%)

### Describe securing network connectivity in Azure
- describe Network Security Groups (NSG)
   - [Network security groups](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview)
   - [Virtual network service tags](https://docs.microsoft.com/en-us/azure/virtual-network/service-tags-overview)
- describe Application Security Groups (ASG)
   - [Application security groups](https://docs.microsoft.com/en-us/azure/virtual-network/application-security-groups)
- describe User Defined Routes (UDR)
   - [Virtual network traffic routing](https://docs.microsoft.com/en-gb/azure/virtual-network/virtual-networks-udr-overview)
- describe Azure Firewall
   - [What is Azure Firewall?](https://docs.microsoft.com/en-us/azure/firewall/overview)
   - [Azure Firewall features](https://docs.microsoft.com/en-us/azure/firewall/features)
   - [What is Azure Web Application Firewall?](https://docs.microsoft.com/en-us/azure/web-application-firewall/overview)
   - [Azure Web Application Firewall on Azure Application Gateway](https://docs.microsoft.com/en-us/azure/web-application-firewall/ag/ag-overview)
   - [Azure Web Application Firewall on Azure Front Door](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview)
- describe Azure DDoS Protection
   - [Azure DDoS Protection Standard overview](https://docs.microsoft.com/en-us/azure/virtual-network/ddos-protection-overview)
- choose an appropriate Azure security solution

### Describe core Azure Identity services
- describe the difference between authentication and authorization
- describe Azure Active Directory
   - [What is Azure Active Directory?](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)
   - [What is Azure AD Privileged Identity Management?](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-configure)
   - [What is Azure Active Directory Identity Protection?](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/overview-identity-protection)
   - [What is Conditional Access?](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)
   - [What are managed identities for Azure resources?](https://docs.microsoft.com/en-us/azure/active-directory/managed-identities-azure-resources/overview)
   - [Azure Active Directory pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
   - [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/license-users-groups)
- describe Azure Multi-Factor Authentication

### Describe security tools and features of Azure
- describe Azure Security Center
   - [What is Azure Security Center?](https://docs.microsoft.com/en-us/azure/security-center/security-center-intro)
- describe Azure Security Center usage scenarios
- describe Key Vault
   - [About Azure Key Vault](https://docs.microsoft.com/en-us/azure/key-vault/general/overview)
- describe Azure Information Protection (AIP)
   - [What is Azure Information Protection?](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)
- describe Azure Advanced Threat Protection (ATP)
   - [What is Azure Advanced Threat Protection?](https://docs.microsoft.com/en-us/azure-advanced-threat-protection/what-is-atp)

### Describe Azure governance methodologies
- describe policies and initiatives with Azure Policy
   - [What is Azure Policy?](https://docs.microsoft.com/en-us/azure/governance/policy/overview)
- describe Role-Based Access Control (RBAC)
   - [What is Azure role-based access control (Azure RBAC)?](https://docs.microsoft.com/en-us/azure/role-based-access-control/overview)
   - [Classic subscription administrator roles, Azure roles, and Azure AD roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles)
- describe Locks
   - [Lock resources to prevent unexpected changes](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources)
- describe Azure Advisor security assistance
   - [Make resources more secure with Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-security-recommendations)
- describe Azure Blueprints
   - [What is Azure Blueprints?](https://docs.microsoft.com/en-us/azure/governance/blueprints/overview)
   - [Understand the lifecycle of an Azure Blueprint](https://docs.microsoft.com/en-us/azure/governance/blueprints/concepts/lifecycle)
   - [Understand resource locking in Azure Blueprints](https://docs.microsoft.com/en-us/azure/governance/blueprints/concepts/resource-locking)

### Describe monitoring and reporting options in Azure
- describe Azure Monitor
   - [Azure Monitor overview](https://docs.microsoft.com/en-us/azure/azure-monitor/overview)
   - [Azure Monitor data platform](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/data-platform)
   - [Logs in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/data-platform-logs)
   - [Metrics in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/data-platform-metrics)
   - [What is Application Insights?](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)
   - [Azure Activity log](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/activity-log)
- describe Azure Service Health
   - [Azure status overview](https://docs.microsoft.com/en-us/azure/service-health/azure-status-overview)
   - [Service Health overview](https://docs.microsoft.com/en-us/azure/service-health/service-health-overview)
- describe the use cases and benefits of Azure Monitor and Azure Service Health

### Describe privacy, compliance and data protection standards in Azure
- describe industry compliance terms such as GDPR, ISO and NIST
- describe the Microsoft Privacy Statement
   - [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement)
- describe the Trust center
- describe the Service Trust Portal
   - [Service Trust Portal](https://servicetrust.microsoft.com/)
- describe Compliance Manager
- determine if Azure is compliant for a business need
- describe Azure Government cloud services
- describe Azure China cloud services

# Describe Azure Pricing, Service Level Agreements, and Lifecycles (20-25%)

### Describe Azure subscriptions

- describe an Azure Subscription
   - [Azure subscription and service limits, quotas, and constraints](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits)
- describe the uses and options with Azure subscriptions such access control and offer types
- describe subscription management using Management groups
   - [What are Azure management groups?](https://docs.microsoft.com/en-us/azure/governance/management-groups/overview)

### Describe planning and management of costs
- describe options for purchasing Azure products and services
- describe options around Azure Free account
- describe the factors affecting costs such as resource types, services, locations, ingress and egress traffic
- describe Zones for billing purposes
   - [Bandwidth Pricing Details](https://azure.microsoft.com/en-in/pricing/details/bandwidth/)
- describe the Pricing calculator
   - [Pricing calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- describe the Total Cost of Ownership (TCO) calculator
   - [Total Cost of Ownership (TCO) Calculator](https://azure.microsoft.com/en-us/pricing/tco/calculator/)
- describe best practices for minimizing Azure costs such as performing cost analysis, creating spending limits and quotas, using tags to identify cost owners, using Azure reservations and using Azure Advisor recommendations
   - [Use tags to organize your Azure resources and management hierarchy](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources)
   - [What are Azure Reservations?](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/save-compute-costs-reservations)
- describe Azure Cost Management
   - [What is Azure Cost Management and Billing?](https://docs.microsoft.com/en-us/azure/cost-management-billing/cost-management-billing-overview)
   - [Prevent unexpected charges with Azure billing and cost management](https://docs.microsoft.com/en-us/azure/cost-management-billing/manage/getting-started)

### Describe Azure Service Level Agreements (SLAs)
- describe a Service Level Agreement (SLA)
   - [SLA summary for Azure services](https://azure.microsoft.com/en-us/support/legal/sla/summary/)
- describe Composite SLAs
- describe how to determine an appropriate SLA for an application

### Describe service lifecycle in Azure
- describe Public and Private Preview features
- describe the term General Availability (GA)
- describe how to monitor feature updates and product changes

# Retired from the exam

### Describe the support options available with Azure
- Understand describe support plans that are available such as Developer, Standard, Professional Direct and Premier
   - [Compare support plans](https://azure.microsoft.com/en-us/support/plans/)
- Understand describe how to open a support ticket
   - [Create an Azure support request](https://docs.microsoft.com/en-us/azure/azure-portal/supportability/how-to-create-azure-support-request)
- Understand describe available support channels outside of support plan channels
- describe the Knowledge Center