<div align="center">

<img src="./assets/z2h.jpeg" alt="Azure AZ-305 Zero to Hero Banner">

<br><br>

<img src="https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
<img src="https://img.shields.io/badge/AZ--305-Solution%20Architect-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/Level-Intermediate%20to%20Advanced-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/Well--Architected-Framework-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
<img src="https://img.shields.io/badge/Cloud%20Adoption-Framework-569A31?style=for-the-badge&logo=microsoftazure&logoColor=white">

<br>

<img src="https://img.shields.io/badge/Architecture-Labs-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Contributions-Welcome-brightgreen?style=for-the-badge">

</div>

<div align="center">

# Azure AZ-305 — Zero to Hero

### ☁️ From Azure architecture fundamentals to enterprise solution design — comprehensive explanations, architecture patterns, hands-on labs, and real-world scenarios.

</div>

---

## 📖 About This Repository

**Azure AZ-305 — Zero to Hero** is a structured, architecture-focused learning repository designed to build the skills required to design secure, scalable, reliable, performant, and cost-effective solutions on Microsoft Azure.

Every section is organized into its own folder with a dedicated `README.md` covering in-depth architecture concepts, diagrams, service comparisons, architecture decisions, hands-on labs, and real-world scenarios. The content progresses logically — from architecture fundamentals and governance to enterprise networking, compute, application architecture, data solutions, business continuity, and migration.

By the end of this course, you will be able to:

- ✅ Translate business and technical requirements into Azure solution architectures
- ✅ Apply the Azure Well-Architected Framework to design reliable, secure, performant, and cost-effective solutions
- ✅ Design cloud adoption strategies using the Cloud Adoption Framework and Azure Landing Zones
- ✅ Design enterprise identity, governance, authorization, and security architectures
- ✅ Design secure and highly available Azure network architectures using Hub-Spoke, Virtual WAN, Private Link, VPN, ExpressRoute, and Azure Firewall
- ✅ Select the appropriate compute platform using Virtual Machines, VM Scale Sets, App Service, Containers, AKS, Functions, and Azure Batch
- ✅ Design scalable application architectures using APIs, caching, messaging, event-driven patterns, and serverless technologies
- ✅ Design relational, NoSQL, storage, and data platform solutions based on workload requirements
- ✅ Design high availability, backup, disaster recovery, and multi-region solutions using RPO and RTO requirements
- ✅ Plan Azure migration and modernization strategies using Azure Migrate and the Cloud Adoption Framework
- ✅ Design centralized monitoring, logging, and observability solutions using Azure Monitor, Log Analytics, and Application Insights
- ✅ Evaluate Azure services, architecture alternatives, trade-offs, performance, security, reliability, and cost before making design decisions
- ✅ Document architecture decisions using Architecture Decision Records (ADRs)
- ✅ Build real-world Azure solution architectures through hands-on labs, scenarios, and projects

---

## 📚 Table of Contents

## 📚 Table of Contents

## 1. Architecture Fundamentals

This section introduces the core concepts of solution architecture and builds the foundation required for AZ-305. It focuses on how architects understand problems, translate requirements into architecture, evaluate design options, and make decisions based on reliability, security, performance, cost, and operational needs.

📂 **[Explore → Architecture Fundamentals](./Architecture%20Fundamentals/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 1.1 | [Introduction to Solution Architecture](./Architecture%20Fundamentals/Introduction%20to%20Solution%20Architecture/) | What solution architecture is, the purpose of architecture, architecture lifecycle, and how business problems are translated into technology solutions |
| 1.2 | [Solutions Architect Role and Responsibilities](./Architecture%20Fundamentals/Solutions%20Architect%20Role%20and%20Responsibilities/) | Responsibilities of a Solutions Architect, stakeholder collaboration, architecture ownership, and the difference between architect, administrator, developer, and DevOps roles |
| 1.3 | [Business and Technical Requirements](./Architecture%20Fundamentals/Business%20and%20Technical%20Requirements/) | Business, functional, non-functional, and technical requirements, constraints, assumptions, dependencies, priorities, and requirement traceability |
| 1.4 | [Architecture Decision-Making](./Architecture%20Fundamentals/Architecture%20Decision-Making/) | Identifying solution options, defining evaluation criteria, comparing alternatives, analyzing risks, and selecting the most appropriate architecture |
| 1.5 | [Architecture Quality Attributes](./Architecture%20Fundamentals/Architecture%20Quality%20Attributes/) | Reliability, security, performance, availability, scalability, maintainability, observability, recoverability, and other qualities that define a successful architecture |
| 1.6 | [Architecture Design Principles](./Architecture%20Fundamentals/Architecture%20Design%20Principles/) | Design for failure, least privilege, defense in depth, Zero Trust, loose coupling, separation of concerns, stateless design, automation, fault isolation, and design for change |
| 1.7 | [Architecture Patterns and Styles](./Architecture%20Fundamentals/Architecture%20Patterns%20and%20Styles/) | N-tier, monolithic, modular monolith, microservices, serverless, API-centric, event-driven, synchronous, asynchronous, queue-based, and publish-subscribe architectures |
| 1.8 | [Scalability, Availability and Resiliency](./Architecture%20Fundamentals/Scalability%2C%20Availability%20and%20Resiliency/) | Scalability, elasticity, high availability, resiliency, fault tolerance, failure handling, recovery, and designing systems to continue operating during failures |
| 1.9 | [Architecture Trade-offs](./Architecture%20Fundamentals/Architecture%20Trade-offs/) | Cost vs availability, performance vs cost, security vs usability, consistency vs availability, complexity vs flexibility, and other architectural trade-offs |
| 1.10 | [Architecture Documentation and ADRs](./Architecture%20Fundamentals/Architecture%20Documentation%20and%20ADRs/) | Architecture diagrams, logical and physical views, data and network flows, Architecture Decision Records, design documentation, reviews, and communicating architectural decisions |

---

---

## 2. Azure Well-Architected Framework

This section explains the **Azure Well-Architected Framework (WAF)** and how its principles are applied when designing Azure solutions. It covers reliability, security, cost optimization, operational excellence, performance efficiency, and the trade-offs between these pillars.

📂 **[Explore → Azure Well-Architected Framework](./Azure%20Well-Architected%20Framework/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 2.1 | [WAF Overview](./Azure%20Well-Architected%20Framework/WAF%20Overview/) | Introduction to the Well-Architected Framework and its purpose |
| 2.2 | [Reliability](./Azure%20Well-Architected%20Framework/Reliability/) | Designing solutions that remain available and recover from failures |
| 2.3 | [Security](./Azure%20Well-Architected%20Framework/Security/) | Applying security principles throughout the architecture |
| 2.4 | [Cost Optimization](./Azure%20Well-Architected%20Framework/Cost%20Optimization/) | Optimizing Azure solutions for cost efficiency |
| 2.5 | [Operational Excellence](./Azure%20Well-Architected%20Framework/Operational%20Excellence/) | Designing solutions that are easy to operate, monitor, and improve |
| 2.6 | [Performance Efficiency](./Azure%20Well-Architected%20Framework/Performance%20Efficiency/) | Designing solutions that efficiently meet performance requirements |
| 2.7 | [Architecture Trade-offs](./Azure%20Well-Architected%20Framework/Architecture%20Trade-offs/) | Understanding trade-offs between WAF pillars |
| 2.8 | [Well-Architected Review](./Azure%20Well-Architected%20Framework/Well-Architected%20Review/) | Reviewing an architecture against WAF principles |
| 2.9 | [WAF Design Checklist](./Azure%20Well-Architected%20Framework/WAF%20Design%20Checklist/) | Practical checklist for evaluating Azure architectures |

---

## 3. Cloud Adoption Framework and Azure Landing Zones

This section explains how organizations plan, adopt, govern, and manage Azure at enterprise scale using the **Cloud Adoption Framework (CAF)** and **Azure Landing Zones**. It covers cloud adoption strategy, governance, management groups, subscriptions, policies, compliance, resource organization, and enterprise-scale architecture.

📂 **[Explore → Cloud Adoption Framework and Azure Landing Zones](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 3.1 | [Cloud Adoption Framework Overview](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Cloud%20Adoption%20Framework%20Overview/) | Introduction to CAF and its role in Azure adoption |
| 3.2 | [CAF Strategy](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Strategy/) | Defining business motivations, outcomes, and adoption strategy |
| 3.3 | [CAF Plan](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Plan/) | Planning people, workloads, skills, and migration activities |
| 3.4 | [CAF Ready](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Ready/) | Preparing the Azure environment for adoption |
| 3.5 | [CAF Adopt](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Adopt/) | Migrating and modernizing workloads |
| 3.6 | [CAF Govern](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Govern/) | Establishing governance and compliance |
| 3.7 | [CAF Manage](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/CAF%20Manage/) | Managing, monitoring, and improving cloud environments |
| 3.8 | [Azure Landing Zones](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Azure%20Landing%20Zones/) | Landing zone concepts and enterprise Azure architecture |
| 3.9 | [Platform Landing Zone](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Platform%20Landing%20Zone/) | Shared platform services and centralized capabilities |
| 3.10 | [Application Landing Zone](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Application%20Landing%20Zone/) | Application workload environments within the enterprise architecture |
| 3.11 | [Management Group Architecture](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Management%20Group%20Architecture/) | Structuring Azure resources and subscriptions at scale |
| 3.12 | [Subscription Strategy](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Subscription%20Strategy/) | Designing subscription boundaries and organization |
| 3.13 | [Azure Policy and Compliance](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Azure%20Policy%20and%20Compliance/) | Enforcing organizational standards and compliance |
| 3.14 | [Resource Organization and Tagging](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Resource%20Organization%20and%20Tagging/) | Naming, tagging, resource groups, and resource organization |
| 3.15 | [Governance at Scale](./Cloud%20Adoption%20Framework%20and%20Azure%20Landing%20Zones/Governance%20at%20Scale/) | Applying governance consistently across enterprise environments |

---

## 4. Identity and Authorization Architecture

This section focuses on designing identity and access solutions for Azure and hybrid environments. It covers Microsoft Entra ID, authentication, authorization, workload identities, managed identities, Conditional Access, privileged access, Azure RBAC, on-premises authorization, and secrets, certificates, and key management.

📂 **[Explore → Identity and Authorization Architecture](./Identity%20and%20Authorization%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 4.1 | [Identity Architecture](./Identity%20and%20Authorization%20Architecture/Identity%20Architecture/) | Identity concepts and identity architecture principles |
| 4.2 | [Authentication and Authorization](./Identity%20and%20Authorization%20Architecture/Authentication%20and%20Authorization/) | Authentication vs authorization and architectural decisions |
| 4.3 | [Microsoft Entra ID Architecture](./Identity%20and%20Authorization%20Architecture/Microsoft%20Entra%20ID%20Architecture/) | Designing identity architecture using Microsoft Entra ID |
| 4.4 | [Workload Identities](./Identity%20and%20Authorization%20Architecture/Workload%20Identities/) | Identity solutions for applications, services, and workloads |
| 4.5 | [Managed Identities](./Identity%20and%20Authorization%20Architecture/Managed%20Identities/) | System-assigned and user-assigned managed identities |
| 4.6 | [Hybrid Identity](./Identity%20and%20Authorization%20Architecture/Hybrid%20Identity/) | Integrating on-premises identity with Azure |
| 4.7 | [External Identities and B2B](./Identity%20and%20Authorization%20Architecture/External%20Identities%20and%20B2B/) | Designing external collaboration and guest access |
| 4.8 | [Conditional Access](./Identity%20and%20Authorization%20Architecture/Conditional%20Access/) | Designing policy-based access controls |
| 4.9 | [Privileged Identity Management](./Identity%20and%20Authorization%20Architecture/Privileged%20Identity%20Management/) | Designing just-in-time privileged access |
| 4.10 | [Azure RBAC Architecture](./Identity%20and%20Authorization%20Architecture/Azure%20RBAC%20Architecture/) | Designing authorization for Azure resources |
| 4.11 | [On-Premises Authorization](./Identity%20and%20Authorization%20Architecture/On-Premises%20Authorization/) | Designing authorization for hybrid and on-premises resources |
| 4.12 | [Secrets, Certificates and Keys](./Identity%20and%20Authorization%20Architecture/Secrets%20Certificates%20and%20Keys/) | Designing secure management of sensitive credentials |
| 4.13 | [Azure Key Vault Architecture](./Identity%20and%20Authorization%20Architecture/Azure%20Key%20Vault%20Architecture/) | Designing centralized secrets, certificates, and key management |
| 4.14 | [Zero Trust Identity](./Identity%20and%20Authorization%20Architecture/Zero%20Trust%20Identity/) | Applying Zero Trust principles to identity |

---

## 5. Network Architecture

This section covers the design of secure, scalable, highly available Azure networking solutions. It includes network topology, hub-and-spoke, Virtual WAN, hybrid connectivity, VPN, ExpressRoute, Private Link, DNS, network security, and global traffic management.

📂 **[Explore → Network Architecture](./Network%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 5.1 | [Network Architecture Principles](./Network%20Architecture/Network%20Architecture%20Principles/) | Core principles for designing Azure networks |
| 5.2 | [Hub-and-Spoke Architecture](./Network%20Architecture/Hub-and-Spoke%20Architecture/) | Designing centralized enterprise network topology |
| 5.3 | [Azure Virtual WAN](./Network%20Architecture/Azure%20Virtual%20WAN/) | Designing global networking using Virtual WAN |
| 5.4 | [VNet Peering](./Network%20Architecture/VNet%20Peering/) | Connecting virtual networks using peering |
| 5.5 | [Hybrid Network Architecture](./Network%20Architecture/Hybrid%20Network%20Architecture/) | Connecting Azure with on-premises environments |
| 5.6 | [VPN Gateway](./Network%20Architecture/VPN%20Gateway/) | Designing site-to-site and point-to-site connectivity |
| 5.7 | [ExpressRoute](./Network%20Architecture/ExpressRoute/) | Designing private dedicated connectivity to Azure |
| 5.8 | [ExpressRoute Global Reach](./Network%20Architecture/ExpressRoute%20Global%20Reach/) | Connecting on-premises locations through Microsoft's network |
| 5.9 | [Private Link and Private Endpoints](./Network%20Architecture/Private%20Link%20and%20Private%20Endpoints/) | Designing private access to Azure services |
| 5.10 | [Service Endpoints](./Network%20Architecture/Service%20Endpoints/) | Securing access from VNets to Azure services |
| 5.11 | [DNS Architecture](./Network%20Architecture/DNS%20Architecture/) | Designing DNS resolution in Azure and hybrid environments |
| 5.12 | [Network Segmentation](./Network%20Architecture/Network%20Segmentation/) | Designing secure network boundaries and segmentation |
| 5.13 | [Network Security Groups](./Network%20Architecture/Network%20Security%20Groups/) | Designing subnet and network interface access controls |
| 5.14 | [Azure Firewall](./Network%20Architecture/Azure%20Firewall/) | Designing centralized network security |
| 5.15 | [Web Application Firewall](./Network%20Architecture/Web%20Application%20Firewall/) | Protecting web applications from application-layer threats |
| 5.16 | [DDoS Protection](./Network%20Architecture/DDoS%20Protection/) | Designing protection against distributed denial-of-service attacks |
| 5.17 | [Load Balancer](./Network%20Architecture/Load%20Balancer/) | Designing Layer 4 load balancing |
| 5.18 | [Application Gateway](./Network%20Architecture/Application%20Gateway/) | Designing Layer 7 application load balancing |
| 5.19 | [Azure Front Door](./Network%20Architecture/Azure%20Front%20Door/) | Designing global application delivery and routing |
| 5.20 | [Traffic Manager](./Network%20Architecture/Traffic%20Manager/) | Designing DNS-based global traffic routing |
| 5.21 | [Network Service Selection](./Network%20Architecture/Network%20Service%20Selection/) | Comparing networking services and selecting the appropriate solution |

---

## 6. Compute Architecture

This section explains how to select the appropriate Azure compute platform based on workload requirements. It covers virtual machines, VM Scale Sets, App Service, containers, AKS, serverless computing, and batch processing.

📂 **[Explore → Compute Architecture](./Compute%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 6.1 | [Compute Selection](./Compute%20Architecture/Compute%20Selection/) | Selecting compute services based on workload requirements |
| 6.2 | [Virtual Machines](./Compute%20Architecture/Virtual%20Machines/) | Designing VM-based workloads |
| 6.3 | [VM Scale Sets](./Compute%20Architecture/VM%20Scale%20Sets/) | Designing scalable VM-based applications |
| 6.4 | [Availability Architecture](./Compute%20Architecture/Availability%20Architecture/) | Designing highly available compute solutions |
| 6.5 | [Azure App Service](./Compute%20Architecture/Azure%20App%20Service/) | Designing managed web application hosting |
| 6.6 | [Deployment Slots](./Compute%20Architecture/Deployment%20Slots/) | Designing safe application deployment strategies |
| 6.7 | [App Service Environment](./Compute%20Architecture/App%20Service%20Environment/) | Designing isolated App Service environments |
| 6.8 | [Container Architecture](./Compute%20Architecture/Container%20Architecture/) | Selecting and designing container-based workloads |
| 6.9 | [Azure Container Instances](./Compute%20Architecture/Azure%20Container%20Instances/) | Designing simple container workloads |
| 6.10 | [Azure Container Apps](./Compute%20Architecture/Azure%20Container%20Apps/) | Designing managed containerized applications |
| 6.11 | [Azure Kubernetes Service](./Compute%20Architecture/Azure%20Kubernetes%20Service/) | Designing enterprise Kubernetes workloads |
| 6.12 | [Azure Functions](./Compute%20Architecture/Azure%20Functions/) | Designing event-driven serverless compute |
| 6.13 | [Logic Apps](./Compute%20Architecture/Logic%20Apps/) | Designing workflow-based serverless solutions |
| 6.14 | [Azure Batch](./Compute%20Architecture/Azure%20Batch/) | Designing large-scale parallel and batch workloads |
| 6.15 | [Compute Service Selection](./Compute%20Architecture/Compute%20Service%20Selection/) | Comparing VM, App Service, containers, serverless, and batch solutions |

---

## 7. Application Architecture

This section covers architectural patterns for building scalable and resilient applications on Azure. It includes N-tier applications, monoliths, microservices, serverless applications, APIs, caching, configuration management, and automated application deployment.

📂 **[Explore → Application Architecture](./Application%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 7.1 | [Application Architecture Principles](./Application%20Architecture/Application%20Architecture%20Principles/) | Core principles for designing cloud applications |
| 7.2 | [N-Tier Architecture](./Application%20Architecture/N-Tier%20Architecture/) | Designing traditional multi-tier applications |
| 7.3 | [Monolithic Architecture](./Application%20Architecture/Monolithic%20Architecture/) | Understanding monolithic application design |
| 7.4 | [Modular Monolith](./Application%20Architecture/Modular%20Monolith/) | Designing modular monolithic applications |
| 7.5 | [Microservices Architecture](./Application%20Architecture/Microservices%20Architecture/) | Designing independently deployable application services |
| 7.6 | [Serverless Application Architecture](./Application%20Architecture/Serverless%20Application%20Architecture/) | Designing applications using managed serverless services |
| 7.7 | [API Architecture](./Application%20Architecture/API%20Architecture/) | Designing scalable and secure API solutions |
| 7.8 | [Azure API Management](./Application%20Architecture/Azure%20API%20Management/) | Managing, securing, publishing, and monitoring APIs |
| 7.9 | [API Security](./Application%20Architecture/API%20Security/) | Authentication, authorization, policies, and API protection |
| 7.10 | [API Versioning](./Application%20Architecture/API%20Versioning/) | Designing API lifecycle and version management |
| 7.11 | [Caching Architecture](./Application%20Architecture/Caching%20Architecture/) | Improving application performance with caching |
| 7.12 | [Azure Managed Redis](./Application%20Architecture/Azure%20Managed%20Redis/) | Designing distributed caching solutions |
| 7.13 | [Application Configuration](./Application%20Architecture/Application%20Configuration/) | Managing application configuration at scale |
| 7.14 | [Azure App Configuration](./Application%20Architecture/Azure%20App%20Configuration/) | Centralized application configuration management |
| 7.15 | [Automated Application Deployment](./Application%20Architecture/Automated%20Application%20Deployment/) | Designing automated deployment architectures |
| 7.16 | [Deployment Strategies](./Application%20Architecture/Deployment%20Strategies/) | Blue-green, canary, rolling, and rollback strategies |
| 7.17 | [CI/CD Architecture](./Application%20Architecture/CI-CD%20Architecture/) | Integrating application delivery pipelines into Azure architecture |

---

## 8. Messaging and Event Architecture

This section explains how to design asynchronous, event-driven, and message-based architectures using Azure messaging services. It covers Service Bus, Event Grid, Event Hubs, Storage Queues, and the architectural patterns used to select between them.

📂 **[Explore → Messaging and Event Architecture](./Messaging%20and%20Event%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 8.1 | [Messaging Architecture](./Messaging%20and%20Event%20Architecture/Messaging%20Architecture/) | Messaging concepts and asynchronous architecture |
| 8.2 | [Azure Service Bus](./Messaging%20and%20Event%20Architecture/Azure%20Service%20Bus/) | Enterprise messaging using queues and topics |
| 8.3 | [Service Bus Queues](./Messaging%20and%20Event%20Architecture/Service%20Bus%20Queues/) | Point-to-point messaging architecture |
| 8.4 | [Service Bus Topics and Subscriptions](./Messaging%20and%20Event%20Architecture/Service%20Bus%20Topics%20and%20Subscriptions/) | Publish-subscribe messaging |
| 8.5 | [Sessions and Message Ordering](./Messaging%20and%20Event%20Architecture/Sessions%20and%20Message%20Ordering/) | Maintaining message state and ordering |
| 8.6 | [Dead-Letter Queues](./Messaging%20and%20Event%20Architecture/Dead-Letter%20Queues/) | Handling failed and undeliverable messages |
| 8.7 | [Azure Event Grid](./Messaging%20and%20Event%20Architecture/Azure%20Event%20Grid/) | Event routing and event-driven architectures |
| 8.8 | [Azure Event Hubs](./Messaging%20and%20Event%20Architecture/Azure%20Event%20Hubs/) | High-throughput event ingestion and streaming |
| 8.9 | [Azure Storage Queues](./Messaging%20and%20Event%20Architecture/Azure%20Storage%20Queues/) | Simple queue-based workload processing |
| 8.10 | [Service Bus vs Event Grid vs Event Hubs](./Messaging%20and%20Event%20Architecture/Service%20Bus%20vs%20Event%20Grid%20vs%20Event%20Hubs/) | Selecting the correct messaging or event service |

---

## 9. Storage Architecture

This section covers the design of Azure storage solutions for different workload requirements. It includes Blob Storage, storage tiers, replication, Azure Files, ADLS Gen2, lifecycle management, durability, security, and storage service selection.

📂 **[Explore → Storage Architecture](./Storage%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 9.1 | [Storage Architecture Principles](./Storage%20Architecture/Storage%20Architecture%20Principles/) | Fundamentals of designing Azure storage solutions |
| 9.2 | [Azure Blob Storage](./Storage%20Architecture/Azure%20Blob%20Storage/) | Designing object storage solutions |
| 9.3 | [Storage Access Tiers](./Storage%20Architecture/Storage%20Access%20Tiers/) | Hot, Cool, Cold, and Archive tier selection |
| 9.4 | [Lifecycle Management](./Storage%20Architecture/Lifecycle%20Management/) | Automatically managing storage data throughout its lifecycle |
| 9.5 | [Storage Replication](./Storage%20Architecture/Storage%20Replication/) | LRS, ZRS, GRS, GZRS, RA-GRS, and RA-GZRS |
| 9.6 | [Storage Durability](./Storage%20Architecture/Storage%20Durability/) | Designing storage for durability and availability |
| 9.7 | [Azure Files](./Storage%20Architecture/Azure%20Files/) | Designing managed file share solutions |
| 9.8 | [Azure File Sync](./Storage%20Architecture/Azure%20File%20Sync/) | Synchronizing on-premises file servers with Azure |
| 9.9 | [Azure Data Lake Storage Gen2](./Storage%20Architecture/Azure%20Data%20Lake%20Storage%20Gen2/) | Designing storage for analytics and big data |
| 9.10 | [Storage Security](./Storage%20Architecture/Storage%20Security/) | SAS, encryption, immutable storage, versioning, and soft delete |
| 9.11 | [Private Storage Access](./Storage%20Architecture/Private%20Storage%20Access/) | Securing storage access using private endpoints |
| 9.12 | [Storage Service Selection](./Storage%20Architecture/Storage%20Service%20Selection/) | Selecting the appropriate Azure storage service |

---

## 10. Database Architecture

This section explains how to select and design Azure database solutions based on workload, performance, scalability, availability, consistency, and cost requirements. It covers Azure SQL, SQL Managed Instance, SQL Server on Azure VMs, and Azure Cosmos DB.

📂 **[Explore → Database Architecture](./Database%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 10.1 | [Database Selection](./Database%20Architecture/Database%20Selection/) | Selecting databases based on application requirements |
| 10.2 | [Relational vs NoSQL](./Database%20Architecture/Relational%20vs%20NoSQL/) | Comparing relational and non-relational database architectures |
| 10.3 | [Azure SQL Database](./Database%20Architecture/Azure%20SQL%20Database/) | Designing managed relational database solutions |
| 10.4 | [SQL Managed Instance](./Database%20Architecture/SQL%20Managed%20Instance/) | Designing highly compatible managed SQL workloads |
| 10.5 | [SQL Server on Azure VM](./Database%20Architecture/SQL%20Server%20on%20Azure%20VM/) | Designing SQL workloads requiring VM-level control |
| 10.6 | [DTU vs vCore](./Database%20Architecture/DTU%20vs%20vCore/) | Understanding Azure SQL purchasing and sizing models |
| 10.7 | [Azure SQL Serverless](./Database%20Architecture/Azure%20SQL%20Serverless/) | Designing variable and intermittent database workloads |
| 10.8 | [Hyperscale](./Database%20Architecture/Hyperscale/) | Designing highly scalable Azure SQL databases |
| 10.9 | [Elastic Pools](./Database%20Architecture/Elastic%20Pools/) | Sharing resources across multiple Azure SQL databases |
| 10.10 | [Database Scalability](./Database%20Architecture/Database%20Scalability/) | Vertical, horizontal, read-scale, and workload scaling |
| 10.11 | [Geo-Replication and Failover Groups](./Database%20Architecture/Geo-Replication%20and%20Failover%20Groups/) | Designing database geo-redundancy and failover |
| 10.12 | [Azure Cosmos DB](./Database%20Architecture/Azure%20Cosmos%20DB/) | Designing globally distributed NoSQL solutions |
| 10.13 | [Cosmos DB Partitioning](./Database%20Architecture/Cosmos%20DB%20Partitioning/) | Designing partition keys and scalable data distribution |
| 10.14 | [Cosmos DB Consistency](./Database%20Architecture/Cosmos%20DB%20Consistency/) | Selecting consistency models based on workload requirements |
| 10.15 | [Cosmos DB Global Distribution](./Database%20Architecture/Cosmos%20DB%20Global%20Distribution/) | Designing multi-region Cosmos DB solutions |
| 10.16 | [Database Backup and Recovery](./Database%20Architecture/Database%20Backup%20and%20Recovery/) | Designing database protection and recovery |
| 10.17 | [Database Service Selection](./Database%20Architecture/Database%20Service%20Selection/) | Comparing Azure SQL, Managed Instance, SQL VM, and Cosmos DB |

---

## 11. Data Architecture

This section covers the architecture of modern Azure data platforms. It explains data lakes, data warehouses, lakehouses, ingestion, ETL/ELT, batch and streaming workloads, data integration, and analytics.

📂 **[Explore → Data Architecture](./Data%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 11.1 | [Data Architecture Principles](./Data%20Architecture/Data%20Architecture%20Principles/) | Core principles for designing cloud data platforms |
| 11.2 | [Data Lake](./Data%20Architecture/Data%20Lake/) | Designing large-scale raw and processed data storage |
| 11.3 | [Data Warehouse](./Data%20Architecture/Data%20Warehouse/) | Designing structured analytical data platforms |
| 11.4 | [Lakehouse Architecture](./Data%20Architecture/Lakehouse%20Architecture/) | Combining data lake flexibility with warehouse capabilities |
| 11.5 | [Azure Data Lake Storage](./Data%20Architecture/Azure%20Data%20Lake%20Storage/) | Storage architecture for analytical workloads |
| 11.6 | [Azure Data Factory](./Data%20Architecture/Azure%20Data%20Factory/) | Designing data integration and pipeline architectures |
| 11.7 | [Azure Synapse Analytics](./Data%20Architecture/Azure%20Synapse%20Analytics/) | Designing enterprise analytics architectures |
| 11.8 | [Azure Databricks](./Data%20Architecture/Azure%20Databricks/) | Designing data engineering and analytics workloads |
| 11.9 | [ETL vs ELT](./Data%20Architecture/ETL%20vs%20ELT/) | Selecting appropriate data transformation approaches |
| 11.10 | [Batch Processing](./Data%20Architecture/Batch%20Processing/) | Designing scheduled and large-scale batch workloads |
| 11.11 | [Stream Processing](./Data%20Architecture/Stream%20Processing/) | Designing real-time data processing architectures |
| 11.12 | [Data Integration](./Data%20Architecture/Data%20Integration/) | Integrating data across applications and platforms |
| 11.13 | [Data Analysis](./Data%20Architecture/Data%20Analysis/) | Designing solutions for analytical workloads |

---

## 12. Business Continuity and Disaster Recovery

This section focuses on designing solutions that remain available during failures and can recover within defined business requirements. It covers RPO, RTO, availability zones, multi-region architectures, backup, recovery, Azure Site Recovery, failover, and failback.

📂 **[Explore → Business Continuity and Disaster Recovery](./Business%20Continuity%20and%20Disaster%20Recovery/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 12.1 | [Business Continuity Fundamentals](./Business%20Continuity%20and%20Disaster%20Recovery/Business%20Continuity%20Fundamentals/) | Understanding business continuity and disaster recovery |
| 12.2 | [RPO and RTO](./Business%20Continuity%20and%20Disaster%20Recovery/RPO%20and%20RTO/) | Defining recovery objectives for solution architecture |
| 12.3 | [Availability Zones](./Business%20Continuity%20and%20Disaster%20Recovery/Availability%20Zones/) | Designing zone-resilient architectures |
| 12.4 | [Multi-Region Architecture](./Business%20Continuity%20and%20Disaster%20Recovery/Multi-Region%20Architecture/) | Designing solutions across Azure regions |
| 12.5 | [Active-Active Architecture](./Business%20Continuity%20and%20Disaster%20Recovery/Active-Active%20Architecture/) | Designing simultaneously active regional solutions |
| 12.6 | [Active-Passive Architecture](./Business%20Continuity%20and%20Disaster%20Recovery/Active-Passive%20Architecture/) | Designing standby disaster recovery architectures |
| 12.7 | [Azure Backup](./Business%20Continuity%20and%20Disaster%20Recovery/Azure%20Backup/) | Designing backup and recovery solutions |
| 12.8 | [Recovery Services Vault](./Business%20Continuity%20and%20Disaster%20Recovery/Recovery%20Services%20Vault/) | Designing centralized backup management |
| 12.9 | [Backup Vault](./Business%20Continuity%20and%20Disaster%20Recovery/Backup%20Vault/) | Designing backup protection for supported workloads |
| 12.10 | [Compute Backup and Recovery](./Business%20Continuity%20and%20Disaster%20Recovery/Compute%20Backup%20and%20Recovery/) | Protecting and recovering compute workloads |
| 12.11 | [Database Backup and Recovery](./Business%20Continuity%20and%20Disaster%20Recovery/Database%20Backup%20and%20Recovery/) | Protecting relational and NoSQL databases |
| 12.12 | [Unstructured Data Recovery](./Business%20Continuity%20and%20Disaster%20Recovery/Unstructured%20Data%20Recovery/) | Protecting storage and file-based workloads |
| 12.13 | [Azure Site Recovery](./Business%20Continuity%20and%20Disaster%20Recovery/Azure%20Site%20Recovery/) | Designing disaster recovery and replication |
| 12.14 | [Failover and Failback](./Business%20Continuity%20and%20Disaster%20Recovery/Failover%20and%20Failback/) | Planning recovery operations |
| 12.15 | [Disaster Recovery Patterns](./Business%20Continuity%20and%20Disaster%20Recovery/Disaster%20Recovery%20Patterns/) | Common Azure DR architecture patterns |

---

## 13. Migration and Modernization

This section explains how to assess, plan, migrate, and modernize workloads using Azure and the Cloud Adoption Framework. It covers migration strategies, the 7 Rs, Azure Migrate, database migration, unstructured data migration, and application modernization.

📂 **[Explore → Migration and Modernization](./Migration%20and%20Modernization/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 13.1 | [Migration Architecture](./Migration%20and%20Modernization/Migration%20Architecture/) | Fundamentals of designing cloud migration solutions |
| 13.2 | [CAF for Migration](./Migration%20and%20Modernization/CAF%20for%20Migration/) | Applying the Cloud Adoption Framework to migration |
| 13.3 | [Migration Assessment](./Migration%20and%20Modernization/Migration%20Assessment/) | Assessing workloads before migration |
| 13.4 | [Migration Planning](./Migration%20and%20Modernization/Migration%20Planning/) | Planning migration waves, dependencies, and sequencing |
| 13.5 | [The 7 Rs of Migration](./Migration%20and%20Modernization/The%207%20Rs%20of%20Migration/) | Rehost, Refactor, Rearchitect, Rebuild, Repurchase, Retain, and Retire |
| 13.6 | [Azure Migrate](./Migration%20and%20Modernization/Azure%20Migrate/) | Discovering, assessing, and migrating workloads |
| 13.7 | [Server and VM Migration](./Migration%20and%20Modernization/Server%20and%20VM%20Migration/) | Migrating on-premises servers and virtual machines |
| 13.8 | [Database Migration](./Migration%20and%20Modernization/Database%20Migration/) | Designing database migration strategies |
| 13.9 | [Unstructured Data Migration](./Migration%20and%20Modernization/Unstructured%20Data%20Migration/) | Migrating files and object data to Azure |
| 13.10 | [Azure Data Box](./Migration%20and%20Modernization/Azure%20Data%20Box/) | Offline data transfer for large-scale migrations |
| 13.11 | [AzCopy and Storage Mover](./Migration%20and%20Modernization/AzCopy%20and%20Storage%20Mover/) | Designing data transfer and migration solutions |
| 13.12 | [Application Modernization](./Migration%20and%20Modernization/Application%20Modernization/) | Modernizing legacy applications using Azure services |
| 13.13 | [Legacy Modernization Patterns](./Migration%20and%20Modernization/Legacy%20Modernization%20Patterns/) | Selecting modernization approaches based on requirements |

---

## 14. Monitoring and Observability Architecture

This section covers the design of centralized monitoring, logging, alerting, and observability solutions in Azure. It includes Azure Monitor, Log Analytics, Application Insights, diagnostic settings, log routing, metrics, logs, traces, and cross-resource monitoring.

📂 **[Explore → Monitoring and Observability Architecture](./Monitoring%20and%20Observability%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 14.1 | [Observability Fundamentals](./Monitoring%20and%20Observability%20Architecture/Observability%20Fundamentals/) | Understanding logs, metrics, and traces |
| 14.2 | [Azure Monitor](./Monitoring%20and%20Observability%20Architecture/Azure%20Monitor/) | Designing centralized Azure monitoring |
| 14.3 | [Metrics](./Monitoring%20and%20Observability%20Architecture/Metrics/) | Monitoring resource and application performance |
| 14.4 | [Logs](./Monitoring%20and%20Observability%20Architecture/Logs/) | Collecting and analyzing Azure logs |
| 14.5 | [Activity Logs](./Monitoring%20and%20Observability%20Architecture/Activity%20Logs/) | Monitoring subscription-level management operations |
| 14.6 | [Resource Logs](./Monitoring%20and%20Observability%20Architecture/Resource%20Logs/) | Collecting resource-specific diagnostic information |
| 14.7 | [Diagnostic Settings](./Monitoring%20and%20Observability%20Architecture/Diagnostic%20Settings/) | Routing platform logs and metrics to destinations |
| 14.8 | [Log Analytics](./Monitoring%20and%20Observability%20Architecture/Log%20Analytics/) | Centralized log storage and analysis |
| 14.9 | [Application Insights](./Monitoring%20and%20Observability%20Architecture/Application%20Insights/) | Monitoring application performance and behavior |
| 14.10 | [Centralized Logging](./Monitoring%20and%20Observability%20Architecture/Centralized%20Logging/) | Designing enterprise-wide logging architectures |
| 14.11 | [Log Routing](./Monitoring%20and%20Observability%20Architecture/Log%20Routing/) | Designing how logs are collected and routed |
| 14.12 | [Alert Architecture](./Monitoring%20and%20Observability%20Architecture/Alert%20Architecture/) | Designing alerts and response mechanisms |
| 14.13 | [Cross-Subscription and Cross-Region Monitoring](./Monitoring%20and%20Observability%20Architecture/Cross-Subscription%20and%20Cross-Region%20Monitoring/) | Designing centralized monitoring at scale |

---

## 15. Cost Optimization Architecture

This section explains how cost should be considered as part of Azure solution design. It covers workload sizing, scaling, reservations, savings plans, storage and database costs, cost allocation, and architecture-level cost trade-offs.

📂 **[Explore → Cost Optimization Architecture](./Cost%20Optimization%20Architecture/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 15.1 | [Cost Optimization Principles](./Cost%20Optimization%20Architecture/Cost%20Optimization%20Principles/) | Core principles for designing cost-effective Azure solutions |
| 15.2 | [Compute Cost Optimization](./Cost%20Optimization%20Architecture/Compute%20Cost%20Optimization/) | Optimizing compute resources and workload sizing |
| 15.3 | [Storage Cost Optimization](./Cost%20Optimization%20Architecture/Storage%20Cost%20Optimization/) | Selecting storage tiers and replication based on cost and requirements |
| 15.4 | [Database Cost Optimization](./Cost%20Optimization%20Architecture/Database%20Cost%20Optimization/) | Optimizing database capacity and purchasing models |
| 15.5 | [Serverless Cost Optimization](./Cost%20Optimization%20Architecture/Serverless%20Cost%20Optimization/) | Understanding consumption-based architecture costs |
| 15.6 | [Right-Sizing](./Cost%20Optimization%20Architecture/Right-Sizing/) | Selecting appropriate resource capacity |
| 15.7 | [Reservations](./Cost%20Optimization%20Architecture/Reservations/) | Reducing costs for predictable workloads |
| 15.8 | [Savings Plans](./Cost%20Optimization%20Architecture/Savings%20Plans/) | Optimizing eligible compute spending |
| 15.9 | [Cost Allocation](./Cost%20Optimization%20Architecture/Cost%20Allocation/) | Allocating costs across teams, applications, and environments |
| 15.10 | [Architecture Cost Trade-offs](./Cost%20Optimization%20Architecture/Architecture%20Cost%20Trade-offs/) | Balancing cost against reliability, performance, and security |

---

## 16. Azure Service Selection and Comparisons

This section focuses on one of the most important Solutions Architect skills — choosing the right Azure service for a specific requirement. It provides architecture-level comparisons between similar services and explains when each option should be selected.

📂 **[Explore → Azure Service Selection and Comparisons](./Azure%20Service%20Selection%20and%20Comparisons/)**

| # | Comparison | Description |
|---|------------|-------------|
| 16.1 | [VM vs VM Scale Sets](./Azure%20Service%20Selection%20and%20Comparisons/VM%20vs%20VM%20Scale%20Sets/) | Choosing between individual VMs and scalable VM groups |
| 16.2 | [VM vs App Service](./Azure%20Service%20Selection%20and%20Comparisons/VM%20vs%20App%20Service/) | Comparing infrastructure control with managed application hosting |
| 16.3 | [App Service vs Container Apps](./Azure%20Service%20Selection%20and%20Comparisons/App%20Service%20vs%20Container%20Apps/) | Choosing between managed web applications and containers |
| 16.4 | [Container Apps vs AKS](./Azure%20Service%20Selection%20and%20Comparisons/Container%20Apps%20vs%20AKS/) | Choosing the appropriate container orchestration platform |
| 16.5 | [Functions vs Logic Apps](./Azure%20Service%20Selection%20and%20Comparisons/Functions%20vs%20Logic%20Apps/) | Comparing serverless compute and workflow automation |
| 16.6 | [Load Balancer vs Application Gateway](./Azure%20Service%20Selection%20and%20Comparisons/Load%20Balancer%20vs%20Application%20Gateway/) | Comparing Layer 4 and Layer 7 load balancing |
| 16.7 | [Application Gateway vs Front Door](./Azure%20Service%20Selection%20and%20Comparisons/Application%20Gateway%20vs%20Front%20Door/) | Choosing regional or global application delivery |
| 16.8 | [Front Door vs Traffic Manager](./Azure%20Service%20Selection%20and%20Comparisons/Front%20Door%20vs%20Traffic%20Manager/) | Comparing global traffic routing approaches |
| 16.9 | [VPN vs ExpressRoute](./Azure%20Service%20Selection%20and%20Comparisons/VPN%20vs%20ExpressRoute/) | Comparing encrypted internet connectivity with private connectivity |
| 16.10 | [Private Endpoint vs Service Endpoint](./Azure%20Service%20Selection%20and%20Comparisons/Private%20Endpoint%20vs%20Service%20Endpoint/) | Comparing private IP connectivity and service endpoint security |
| 16.11 | [NSG vs Firewall vs WAF](./Azure%20Service%20Selection%20and%20Comparisons/NSG%20vs%20Firewall%20vs%20WAF/) | Selecting the correct network security control |
| 16.12 | [Service Bus vs Event Grid](./Azure%20Service%20Selection%20and%20Comparisons/Service%20Bus%20vs%20Event%20Grid/) | Comparing messaging and event routing |
| 16.13 | [Event Hubs vs Event Grid](./Azure%20Service%20Selection%20and%20Comparisons/Event%20Hubs%20vs%20Event%20Grid/) | Comparing event streaming and event routing |
| 16.14 | [Storage Queue vs Service Bus](./Azure%20Service%20Selection%20and%20Comparisons/Storage%20Queue%20vs%20Service%20Bus/) | Choosing simple queues or enterprise messaging |
| 16.15 | [Azure SQL vs Managed Instance](./Azure%20Service%20Selection%20and%20Comparisons/Azure%20SQL%20vs%20Managed%20Instance/) | Choosing the appropriate managed SQL platform |
| 16.16 | [Azure SQL vs Cosmos DB](./Azure%20Service%20Selection%20and%20Comparisons/Azure%20SQL%20vs%20Cosmos%20DB/) | Choosing relational or globally distributed NoSQL architecture |
| 16.17 | [Blob Storage vs Azure Files](./Azure%20Service%20Selection%20and%20Comparisons/Blob%20Storage%20vs%20Azure%20Files/) | Choosing object or file storage |
| 16.18 | [Blob Storage vs ADLS Gen2](./Azure%20Service%20Selection%20and%20Comparisons/Blob%20Storage%20vs%20ADLS%20Gen2/) | Choosing storage based on analytics requirements |

---

## 17. Azure Architecture Patterns

This section brings individual Azure services together into reusable architecture patterns. It demonstrates how common enterprise solutions are designed for high availability, scalability, security, hybrid connectivity, global applications, microservices, serverless workloads, and disaster recovery.

📂 **[Explore → Azure Architecture Patterns](./Azure%20Architecture%20Patterns/)**

| # | Architecture Pattern | Description |
|---|----------------------|-------------|
| 17.1 | [Highly Available Web Application](./Azure%20Architecture%20Patterns/Highly%20Available%20Web%20Application/) | Designing a resilient web application architecture |
| 17.2 | [N-Tier Application](./Azure%20Architecture%20Patterns/N-Tier%20Application/) | Designing traditional multi-tier workloads |
| 17.3 | [Microservices Architecture](./Azure%20Architecture%20Patterns/Microservices%20Architecture/) | Designing distributed microservices platforms |
| 17.4 | [Serverless Architecture](./Azure%20Architecture%20Patterns/Serverless%20Architecture/) | Designing event-driven serverless applications |
| 17.5 | [Event-Driven Architecture](./Azure%20Architecture%20Patterns/Event-Driven%20Architecture/) | Designing loosely coupled event-driven systems |
| 17.6 | [API-Centric Architecture](./Azure%20Architecture%20Patterns/API-Centric%20Architecture/) | Designing API-first enterprise applications |
| 17.7 | [Hybrid Cloud Architecture](./Azure%20Architecture%20Patterns/Hybrid%20Cloud%20Architecture/) | Designing Azure and on-premises integrated environments |
| 17.8 | [Multi-Region Architecture](./Azure%20Architecture%20Patterns/Multi-Region%20Architecture/) | Designing globally distributed applications |
| 17.9 | [Enterprise Landing Zone](./Azure%20Architecture%20Patterns/Enterprise%20Landing%20Zone/) | Designing enterprise Azure foundations |
| 17.10 | [Enterprise Data Platform](./Azure%20Architecture%20Patterns/Enterprise%20Data%20Platform/) | Designing scalable enterprise data architectures |
| 17.11 | [Disaster Recovery Architecture](./Azure%20Architecture%20Patterns/Disaster%20Recovery%20Architecture/) | Designing resilient recovery architectures |
| 17.12 | [Legacy Modernization Architecture](./Azure%20Architecture%20Patterns/Legacy%20Modernization%20Architecture/) | Modernizing traditional applications using Azure |

---

## 18. Architecture Decision Records

This section introduces **Architecture Decision Records (ADRs)** for documenting important architectural decisions. Each decision captures the context, requirements, alternatives, selected solution, trade-offs, and consequences.

📂 **[Explore → Architecture Decision Records](./Architecture%20Decision%20Records/)**

| # | Sub-Topic | Description |
|---|-----------|-------------|
| 18.1 | [What is an ADR?](./Architecture%20Decision%20Records/What%20is%20an%20ADR/) | Understanding the purpose of architecture decision records |
| 18.2 | [ADR Structure](./Architecture%20Decision%20Records/ADR%20Structure/) | Standard structure used to document architecture decisions |
| 18.3 | [ADR Template](./Architecture%20Decision%20Records/ADR%20Template/) | Reusable template for documenting decisions |
| 18.4 | [Architecture Alternatives](./Architecture%20Decision%20Records/Architecture%20Alternatives/) | Comparing possible architecture approaches |
| 18.5 | [Architecture Trade-offs](./Architecture%20Decision%20Records/Architecture%20Trade-offs/) | Documenting benefits, limitations, and consequences |
| 18.6 | [Networking Decisions](./Architecture%20Decision%20Records/Networking%20Decisions/) | Documenting network architecture decisions |
| 18.7 | [Compute Decisions](./Architecture%20Decision%20Records/Compute%20Decisions/) | Documenting compute service selection |
| 18.8 | [Database Decisions](./Architecture%20Decision%20Records/Database%20Decisions/) | Documenting database architecture decisions |
| 18.9 | [Storage Decisions](./Architecture%20Decision%20Records/Storage%20Decisions/) | Documenting storage architecture decisions |
| 18.10 | [Security Decisions](./Architecture%20Decision%20Records/Security%20Decisions/) | Documenting security architecture decisions |
| 18.11 | [HA and DR Decisions](./Architecture%20Decision%20Records/HA%20and%20DR%20Decisions/) | Documenting availability and disaster recovery decisions |
| 18.12 | [Cost Decisions](./Architecture%20Decision%20Records/Cost%20Decisions/) | Documenting cost-related architecture decisions |

---

## 19. Architecture Labs

This section provides hands-on labs focused on **architecture implementation and validation** rather than basic Azure administration. Each lab connects architecture concepts with real Azure services and documents the design decisions involved.

📂 **[Explore → Architecture Labs](./Architecture%20Labs/)**

| # | Lab | Description |
|---|-----|-------------|
| 19.1 | [Identity and Key Vault Architecture](./Architecture%20Labs/Identity%20and%20Key%20Vault%20Architecture/) | Implementing managed identity and secure secret access |
| 19.2 | [Landing Zone Governance](./Architecture%20Labs/Landing%20Zone%20Governance/) | Implementing management groups, policies, and governance |
| 19.3 | [Hub-and-Spoke Network](./Architecture%20Labs/Hub-and-Spoke%20Network/) | Implementing an enterprise network topology |
| 19.4 | [Hub-and-Spoke with Azure Firewall](./Architecture%20Labs/Hub-and-Spoke%20with%20Azure%20Firewall/) | Centralizing network traffic inspection |
| 19.5 | [Private Endpoint and Private DNS](./Architecture%20Labs/Private%20Endpoint%20and%20Private%20DNS/) | Implementing private access to Azure services |
| 19.6 | [Hybrid VPN Architecture](./Architecture%20Labs/Hybrid%20VPN%20Architecture/) | Implementing hybrid Azure connectivity |
| 19.7 | [Application Gateway and WAF](./Architecture%20Labs/Application%20Gateway%20and%20WAF/) | Protecting and routing web application traffic |
| 19.8 | [Multi-Region Application](./Architecture%20Labs/Multi-Region%20Application/) | Implementing a globally available application |
| 19.9 | [Highly Available Compute](./Architecture%20Labs/Highly%20Available%20Compute/) | Implementing resilient compute architecture |
| 19.10 | [API Management Architecture](./Architecture%20Labs/API%20Management%20Architecture/) | Implementing an enterprise API gateway |
| 19.11 | [Service Bus Architecture](./Architecture%20Labs/Service%20Bus%20Architecture/) | Implementing asynchronous messaging |
| 19.12 | [Cosmos DB Global Distribution](./Architecture%20Labs/Cosmos%20DB%20Global%20Distribution/) | Implementing globally distributed NoSQL |
| 19.13 | [Centralized Monitoring](./Architecture%20Labs/Centralized%20Monitoring/) | Implementing centralized Azure monitoring |
| 19.14 | [Azure Backup and Recovery](./Architecture%20Labs/Azure%20Backup%20and%20Recovery/) | Implementing backup and recovery architecture |
| 19.15 | [Azure Site Recovery](./Architecture%20Labs/Azure%20Site%20Recovery/) | Implementing disaster recovery |

---

## 20. Real-World Architecture Projects

This section combines multiple Azure services and architecture principles into complete real-world solutions. Each project starts with business requirements and ends with a documented architecture, service selection, trade-offs, security, reliability, cost, and operational considerations.

📂 **[Explore → Real-World Architecture Projects](./Real-World%20Architecture%20Projects/)**

| # | Project | Description |
|---|---------|-------------|
| 20.1 | [Highly Available Web Application](./Real-World%20Architecture%20Projects/Highly%20Available%20Web%20Application/) | Design and implement a highly available web application |
| 20.2 | [Global E-Commerce Platform](./Real-World%20Architecture%20Projects/Global%20E-Commerce%20Platform/) | Design a globally distributed e-commerce solution |
| 20.3 | [Enterprise Landing Zone](./Real-World%20Architecture%20Projects/Enterprise%20Landing%20Zone/) | Design an enterprise-scale Azure foundation |
| 20.4 | [Enterprise Hub-and-Spoke Network](./Real-World%20Architecture%20Projects/Enterprise%20Hub-and-Spoke%20Network/) | Design a secure centralized enterprise network |
| 20.5 | [Hybrid Enterprise Architecture](./Real-World%20Architecture%20Projects/Hybrid%20Enterprise%20Architecture/) | Integrate Azure workloads with on-premises infrastructure |
| 20.6 | [Microservices Platform](./Real-World%20Architecture%20Projects/Microservices%20Platform/) | Design a scalable microservices platform |
| 20.7 | [Serverless Application Platform](./Real-World%20Architecture%20Projects/Serverless%20Application%20Platform/) | Design an event-driven serverless application |
| 20.8 | [Multi-Region Application](./Real-World%20Architecture%20Projects/Multi-Region%20Application/) | Design an application with global availability |
| 20.9 | [Enterprise Data Platform](./Real-World%20Architecture%20Projects/Enterprise%20Data%20Platform/) | Design a complete enterprise data platform |
| 20.10 | [Disaster Recovery Solution](./Real-World%20Architecture%20Projects/Disaster%20Recovery%20Solution/) | Design a business-critical DR solution |
| 20.11 | [Legacy Application Modernization](./Real-World%20Architecture%20Projects/Legacy%20Application%20Modernization/) | Modernize an existing legacy application |
| 20.12 | [Enterprise API Platform](./Real-World%20Architecture%20Projects/Enterprise%20API%20Platform/) | Design a secure and scalable API platform |

---

## 21. Scenario-Based Architecture Design

This section focuses on the **scenario-based decision-making skills** required for AZ-305. Each scenario starts with business requirements, technical constraints, recovery objectives, and workload characteristics before designing and evaluating the final Azure architecture.

📂 **[Explore → Scenario-Based Architecture Design](./Scenario-Based%20Architecture%20Design/)**

| # | Scenario | Description |
|---|----------|-------------|
| 21.1 | [Identity Scenarios](./Scenario-Based%20Architecture%20Design/Identity%20Scenarios/) | Design identity and authorization solutions |
| 21.2 | [Governance Scenarios](./Scenario-Based%20Architecture%20Design/Governance%20Scenarios/) | Design governance and compliance solutions |
| 21.3 | [Networking Scenarios](./Scenario-Based%20Architecture%20Design/Networking%20Scenarios/) | Design network and connectivity solutions |
| 21.4 | [Compute Scenarios](./Scenario-Based%20Architecture%20Design/Compute%20Scenarios/) | Select and design compute architectures |
| 21.5 | [Application Scenarios](./Scenario-Based%20Architecture%20Design/Application%20Scenarios/) | Design application and API architectures |
| 21.6 | [Messaging Scenarios](./Scenario-Based%20Architecture%20Design/Messaging%20Scenarios/) | Select messaging and event-driven solutions |
| 21.7 | [Storage Scenarios](./Scenario-Based%20Architecture%20Design/Storage%20Scenarios/) | Design storage architectures based on requirements |
| 21.8 | [Database Scenarios](./Scenario-Based%20Architecture%20Design/Database%20Scenarios/) | Select and design database solutions |
| 21.9 | [Data Architecture Scenarios](./Scenario-Based%20Architecture%20Design/Data%20Architecture%20Scenarios/) | Design enterprise data solutions |
| 21.10 | [High Availability and DR Scenarios](./Scenario-Based%20Architecture%20Design/High%20Availability%20and%20DR%20Scenarios/) | Design solutions around RPO, RTO, and availability |
| 21.11 | [Migration Scenarios](./Scenario-Based%20Architecture%20Design/Migration%20Scenarios/) | Select migration and modernization strategies |
| 21.12 | [Enterprise Architecture Scenarios](./Scenario-Based%20Architecture%20Design/Enterprise%20Architecture%20Scenarios/) | Solve complex enterprise architecture requirements |
| 21.13 | [AZ-305 Case Studies](./Scenario-Based%20Architecture%20Design/AZ-305%20Case%20Studies/) | Full scenario-based architecture case studies |

---
