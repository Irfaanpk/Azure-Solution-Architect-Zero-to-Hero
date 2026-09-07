# Business and Technical Requirements

## 📌 Overview

A Solutions Architect should never begin designing an Azure solution by immediately selecting services.

The first step is to understand **what the business needs** and translate those needs into clear technical requirements.

```text
Business Goal
     ↓
Business Requirements
     ↓
Technical Requirements
     ↓
Constraints & Assumptions
     ↓
Priorities
     ↓
Architecture
```

Requirements are the foundation of architecture.

If the requirements are misunderstood, even a technically excellent architecture can become the wrong solution.

---

# 1. What Are Requirements?

A requirement describes **something the solution must achieve, provide, or satisfy**.

For example:

> "The application must support customers from multiple countries."

This is a business-level requirement.

The architect then determines what technical capabilities are needed to satisfy it.

```text
Business Requirement
        │
        ▼
Global Customer Access
        │
        ▼
Technical Requirements
        ├── Global traffic routing
        ├── Regional deployment
        ├── Data residency considerations
        ├── High availability
        └── Network connectivity
```

The important point is:

> **Requirements describe what the solution needs to achieve; architecture determines how to achieve it.**

---

# 2. Business Requirements

Business requirements describe the **business outcome** the organization wants.

Examples:

- Increase application availability
- Reduce operational costs
- Support more customers
- Expand into new regions
- Modernize legacy applications
- Protect customer information
- Reduce deployment time
- Meet regulatory requirements
- Improve application performance

### Example

```text
Business Goal:
Expand e-commerce application globally.

Business Requirements:
├── Support international customers
├── Provide good user experience
├── Maintain high availability
├── Protect customer data
└── Control operating costs
```

These requirements do not yet specify Azure services.

---

# 3. Technical Requirements

Technical requirements describe the **technical capabilities** needed to satisfy the business requirements.

For example:

### Business Requirement

> "The application must remain available if a data center fails."

### Technical Requirements

Possible technical requirements include:

- Redundancy
- Fault isolation
- Multiple availability zones
- Regional disaster recovery
- Health monitoring
- Automated failover

```text
Business Requirement
        ↓
High Availability
        ↓
Technical Requirements
        ├── Redundancy
        ├── Failure Detection
        ├── Failover
        └── Recovery
```

Technical requirements provide a bridge between business needs and architecture.

---

# 4. Functional Requirements

Functional requirements describe **what the system must do**.

Examples:

- Users must be able to register
- Users must be able to log in
- Customers must be able to place orders
- Administrators must be able to manage products
- The application must send order notifications
- The system must process payments

```text
E-Commerce Application
        │
        ├── User Registration
        ├── Authentication
        ├── Product Management
        ├── Shopping Cart
        ├── Order Processing
        ├── Payment Processing
        └── Notifications
```

Functional requirements describe system behavior.

---

# 5. Non-Functional Requirements

Non-functional requirements describe **how well the system must operate**.

Examples:

- Availability
- Performance
- Scalability
- Security
- Reliability
- Maintainability
- Observability
- Recoverability
- Compliance

For example:

> "The application must respond to requests within 2 seconds."

This is a performance requirement.

> "The application must be available 99.95% of the time."

This is an availability requirement.

```text
Functional
   ↓
What must the system do?

Non-Functional
   ↓
How well must the system do it?
```

Non-functional requirements often have a major influence on architecture.

---

# 6. Functional vs Non-Functional Requirements

| Type | Question | Example |
|---|---|---|
| Functional | What should the system do? | Process customer orders |
| Non-functional | How well should it operate? | Process requests within 2 seconds |
| Functional | What capability is required? | Users can upload files |
| Non-functional | What quality is required? | Uploaded files must be encrypted |
| Functional | What action should happen? | Send order confirmation |
| Non-functional | What operational requirement exists? | Notification service must be highly available |

Both types are required for architecture.

---

# 7. Availability Requirements

Availability defines how much time a system should remain operational.

For example:

> "The application must be available 99.99% of the time."

The architect must understand:

- Required availability level
- Acceptable downtime
- Failure scenarios
- Required redundancy
- Recovery requirements

```text
Availability Requirement
          ↓
Identify Failure Scenarios
          ↓
Remove / Reduce Single Points of Failure
          ↓
Add Redundancy
          ↓
Design Failover
```

Higher availability usually requires additional architecture complexity and cost.

---

# 8. Reliability Requirements

Reliability describes the ability of a system to **perform correctly and consistently over time**.

Reliability considerations include:

- Component failures
- Dependency failures
- Network failures
- Data failures
- Application failures
- Recovery mechanisms

Example:

```text
Application
    │
    ├── Database
    ├── Storage
    ├── Messaging
    └── External API
```

The architect should ask:

> "What happens if any of these dependencies fail?"

This question helps convert reliability requirements into architecture decisions.

---

# 9. Performance Requirements

Performance requirements define how quickly and efficiently the system should operate.

Examples:

- API response time below 500 ms
- Process 10,000 requests per second
- Complete batch processing within 30 minutes
- Database query response below a defined threshold

```text
Performance Requirement
          ↓
     Workload Analysis
          ↓
 ┌────────┼────────┐
 ▼        ▼        ▼
Compute  Database  Network
          │
          ▼
      Optimization
```

Performance requirements can influence:

- Compute selection
- Database design
- Caching
- Network architecture
- Application architecture
- Data access patterns

---

# 10. Scalability Requirements

Scalability defines how the system should handle increasing workload.

Example:

> "The application currently serves 100,000 users but must support 1 million users within three years."

The architect must consider:

- Expected traffic
- User growth
- Data growth
- Compute scaling
- Database scaling
- Storage growth
- Network capacity

```text
Current
100K Users
    │
    ▼
Architecture
    │
    ▼
Future
1M Users
```

A scalable architecture should be able to grow without requiring a complete redesign.

---

# 11. Security Requirements

Security requirements define how the solution should protect:

- Identities
- Applications
- Data
- Networks
- Secrets
- Infrastructure

Examples:

- Multi-factor authentication
- Encryption
- Network isolation
- Least-privilege access
- Centralized auditing
- Secret protection
- Secure application access

```text
Security Requirements
        │
 ┌──────┼──────┐
 ▼      ▼      ▼
Identity Network Data
 │       │      │
 ▼       ▼      ▼
Access  Security Encryption
```

Security requirements can affect almost every architecture decision.

---

# 12. Compliance Requirements

Organizations may have legal, regulatory, or industry requirements.

Examples include requirements around:

- Data residency
- Data retention
- Encryption
- Auditing
- Access control
- Logging
- Data protection

For example:

> "Customer data must remain within a specific geographic boundary."

This requirement can affect:

```text
Data Residency
      ↓
Region Selection
      ↓
Service Availability
      ↓
Data Storage
      ↓
Backup Location
      ↓
Disaster Recovery Design
```

Compliance requirements should be identified early because they can significantly constrain architecture choices.

---

# 13. Data Requirements

Architects must understand how data should be handled.

Important questions include:

- What type of data is stored?
- How much data exists?
- How quickly will data grow?
- How frequently is data accessed?
- How long must data be retained?
- Who can access it?
- Does the data need global replication?
- What consistency is required?
- What backup requirements exist?

```text
Data Requirements
      │
 ┌────┼───────────────┐
 ▼    ▼               ▼
Type  Volume        Access
 │     │               │
 ▼     ▼               ▼
Data  Growth       Performance
```

Data requirements strongly influence storage and database architecture.

---

# 14. Geographic Requirements

Some solutions need to operate in specific geographic locations.

Examples:

- Users are distributed globally
- Data must remain in a particular country
- Application must support multiple regions
- Disaster recovery must use a different region

Questions include:

- Where are users located?
- Where should workloads run?
- Where should data be stored?
- Where should backups be stored?
- What regions are supported by required Azure services?

```text
Global Users
     │
 ┌───┼───────────┐
 ▼   ▼           ▼
US  Europe      Asia
 │    │           │
 └────┼───────────┘
      ▼
Global Architecture
```

Geographic requirements can affect networking, data, availability, compliance, and cost.

---

# 15. Disaster Recovery Requirements

Disaster recovery requirements define what should happen when a major failure occurs.

Two important concepts are:

### RPO — Recovery Point Objective

RPO defines the **maximum acceptable amount of data loss measured in time**.

Example:

> RPO = 15 minutes

This means the organization is willing to potentially lose up to 15 minutes of data.

```text
Last Recovery Point
       │
       ├────────────── 15 minutes ──────────────┤
       │                                        │
     Backup                                  Failure
```

### RTO — Recovery Time Objective

RTO defines the **maximum acceptable time to restore service**.

Example:

> RTO = 1 hour

The solution should be capable of restoring the required service within one hour.

```text
Failure
  │
  ├────────────── 1 hour ──────────────┤
  │                                    │
Failure                             Service
Occurs                              Restored
```

RPO and RTO are requirements.

The architecture determines how those objectives can be achieved.

---

# 16. Cost Requirements

Cost is also a requirement.

A business may specify:

> "The solution must operate within a defined monthly budget."

The architect must consider:

- Compute cost
- Storage cost
- Database cost
- Network cost
- Monitoring cost
- Backup cost
- Disaster recovery cost
- Operational effort

```text
Architecture
     │
     ├── Performance
     ├── Availability
     ├── Security
     └── Cost
```

The cheapest architecture is not always the correct architecture.

The solution must satisfy the required business outcomes while remaining financially appropriate.

---

# 17. Operational Requirements

Operational requirements describe how the solution should be managed after deployment.

Examples:

- Centralized monitoring
- Automated deployment
- Logging
- Alerting
- Backup
- Patch management
- Incident response
- Operational visibility

For example:

> "The operations team should be able to monitor the entire application from a centralized platform."

This creates architectural requirements around:

- Logging
- Metrics
- Tracing
- Alerts
- Monitoring
- Diagnostic data

---

# 18. Constraints

A **constraint** is a limitation that restricts the available solution options.

Examples:

- Fixed budget
- Existing technology
- Regulatory requirements
- Existing contracts
- Limited engineering skills
- Required Azure region
- Existing network architecture
- Migration deadline
- Legacy application limitations

```text
Requirements
     +
Constraints
     ↓
Available Architecture Options
```

### Example

Requirement:

> "Application must run in Azure."

Constraint:

> "The application cannot be completely rewritten."

This may make a full cloud-native redesign inappropriate.

A migration or modernization strategy may be more suitable.

---

# 19. Assumptions

An assumption is something the architecture team **believes to be true** while designing the solution.

Examples:

- Expected traffic is 10,000 requests per second
- Users will authenticate through Entra ID
- The application supports horizontal scaling
- Network connectivity between environments is available

Example:

```text
Assumption:
Traffic will remain below 10K requests/sec.

        ↓

Architecture designed around
10K requests/sec.

        ↓

If assumption changes
        ↓

Architecture may need revision.
```

Important assumptions should be documented and validated.

---

# 20. Dependencies

A dependency is something the solution relies on.

Dependencies can include:

- External APIs
- Existing databases
- Identity providers
- Network connections
- Third-party services
- Internal applications
- Shared infrastructure

Example:

```text
Application
     │
     ├── Identity Service
     ├── Payment API
     ├── Database
     └── External Notification Service
```

If an important dependency fails, the application may also fail.

Architects therefore need to understand critical dependencies.

---

# 21. Requirements Prioritization

Not all requirements have equal importance.

For example:

```text
Must Have
├── Security
├── Data Protection
└── Required Availability

Should Have
├── Advanced Monitoring
└── Additional Automation

Could Have
├── Optional Features
└── Future Enhancements
```

A common approach is to classify requirements as:

- **Must have**
- **Should have**
- **Could have**
- **Won't have for now**

Prioritization becomes important when requirements conflict.

---

# 22. Requirement Conflicts

Requirements can sometimes conflict.

Example:

```text
Business wants:
High Availability
       +
Very Low Cost
```

The architect must determine whether both requirements can realistically be achieved.

Another example:

```text
Maximum Security
       vs
Maximum User Convenience
```

Another:

```text
Strong Consistency
       vs
Global Performance
```

The architect must identify the conflict and work with stakeholders to establish priorities.

Detailed trade-off analysis is covered in **1.9 Architecture Trade-offs**.

---

# 23. Requirement Traceability

Requirement traceability means being able to connect a requirement to the architectural decision that satisfies it.

Example:

```text
Business Requirement
"Application must be highly available"
             │
             ▼
Technical Requirement
"Remove single points of failure"
             │
             ▼
Architecture Decision
"Deploy across availability zones"
             │
             ▼
Implementation
Configure redundant application instances
```

This makes architecture decisions easier to justify and review.

---

# 24. Requirements to Architecture Mapping

A useful architecture approach is:

```text
Requirement
     ↓
Technical Capability
     ↓
Architecture Component
     ↓
Azure Service
     ↓
Implementation
```

### Example

```text
Requirement:
Application must scale automatically.
          ↓
Technical Capability:
Automatic horizontal scaling.
          ↓
Architecture:
Stateless application instances.
          ↓
Azure Service:
Appropriate scalable compute platform.
          ↓
Implementation:
Configure autoscaling rules.
```

Notice that the Azure service is selected **after understanding the requirement**.

---

# 25. Requirement Discovery Questions

Before designing a solution, an architect should ask questions.

### Business

- What problem are we solving?
- What business outcome is expected?
- Who are the users?
- What happens if the solution fails?

### Workload

- How many users?
- How much traffic?
- What is the expected growth?
- What are peak workloads?

### Availability

- What availability is required?
- What downtime is acceptable?
- What failures must the system survive?

### Performance

- What response time is expected?
- What throughput is required?
- Are there peak usage periods?

### Data

- What data is stored?
- How much data exists?
- How quickly does it grow?
- How long must it be retained?

### Security

- Who can access the system?
- What data is sensitive?
- What authentication is required?
- What compliance requirements exist?

### Operations

- Who will operate the system?
- What monitoring is required?
- What deployment process is expected?

### Cost

- What is the budget?
- Is the workload predictable?
- Are there cost constraints?

---

# 26. Example: E-Commerce Requirements

Consider an e-commerce platform.

### Business Requirements

```text
├── Support global customers
├── Process customer orders
├── Protect customer information
├── Maintain high availability
├── Handle seasonal traffic spikes
└── Control operational cost
```

### Technical Requirements

```text
├── Global traffic management
├── Secure authentication
├── Highly available application
├── Automatic scaling
├── Reliable order processing
├── Secure database
├── Backup and recovery
├── Centralized monitoring
└── Cost controls
```

### Constraints

```text
├── Limited operations team
├── Existing payment provider
├── Existing customer database
└── Fixed migration timeline
```

### Assumptions

```text
├── Traffic will increase significantly during sales
├── Application can be horizontally scaled
└── Payment provider supports cloud connectivity
```

Now the architect has enough information to begin evaluating architecture options.

---

# 27. Example: Legacy Application Migration

Suppose a company has a legacy application running on physical servers.

### Business Requirements

- Move the application to Azure
- Reduce data center dependency
- Maintain application functionality
- Improve disaster recovery

### Constraints

- Application cannot be rewritten immediately
- Migration must happen within six months
- Existing database must initially remain compatible

### Technical Requirements

```text
Legacy Application
       ↓
Azure Migration
       ↓
├── Compatible Compute
├── Network Connectivity
├── Database Migration
├── Backup
├── Monitoring
└── Disaster Recovery
```

These requirements help the architect determine the appropriate migration approach.

---

# 28. Requirements Are Not the Architecture

A common mistake is to confuse requirements with solutions.

### Requirement

> "The application must support 1 million users."

### Not a requirement:

> "Use Azure Kubernetes Service."

The second statement is already a technology decision.

The correct process is:

```text
Requirement
     ↓
Analyze Workload
     ↓
Identify Technical Capabilities
     ↓
Evaluate Architecture Options
     ↓
Select Appropriate Technology
```

The architect should avoid prematurely locking the solution to a particular technology.

---

# 29. Common Mistakes

## ❌ Starting With Azure Services

```text
"I know this service,
so let's use it."
```

### Better:

```text
Requirement
    ↓
Evaluate Options
    ↓
Choose Service
```

---

## ❌ Ignoring Non-Functional Requirements

An application may provide all required features but still fail because:

- It is too slow
- It is unreliable
- It is insecure
- It cannot scale
- It is too expensive

---

## ❌ Ignoring Constraints

A technically excellent solution may still be impossible because of:

- Budget
- Skills
- Timeline
- Existing systems
- Compliance
- Regional limitations

---

## ❌ Treating Every Requirement as Equal

Some requirements are mandatory.

Others can be deferred.

The architect must understand priorities.

---

## ❌ Making Assumptions Without Validation

Unvalidated assumptions can become architecture risks.

```text
Wrong Assumption
       ↓
Wrong Architecture
       ↓
Production Problem
```

---

# 🧠 Requirements Analysis Framework

A useful framework is:

```text
                REQUIREMENTS
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
    Business      Functional   Non-Functional
       │             │             │
       │             │      ┌──────┼─────────┐
       │             │      ▼      ▼         ▼
       │             │   Security Performance
       │             │      │      │         │
       │             │      ▼      ▼         ▼
       │             │ Availability Scalability
       │             │
       └─────────────┼──────────────┘
                     ▼
              Constraints
                     │
                     ▼
               Assumptions
                     │
                     ▼
               Dependencies
                     │
                     ▼
                Priorities
                     │
                     ▼
                Architecture
```

---

# 🎯 Practical Exercise

Imagine a company wants to build a **global online learning platform**.

The platform must:

- Support students worldwide
- Handle 500,000 users
- Store video content
- Protect user information
- Remain available during failures
- Support traffic spikes during exams
- Keep operational costs controlled

Before selecting any Azure service, create the following:

### 1. Business Requirements

Identify what the business wants to achieve.

### 2. Functional Requirements

Identify what the platform must do.

### 3. Non-Functional Requirements

Identify:

- Availability
- Performance
- Scalability
- Security
- Reliability
- Recoverability

### 4. Constraints

Identify possible limitations.

### 5. Assumptions

Write down assumptions about:

- Users
- Traffic
- Data
- Application behavior

### 6. Dependencies

Identify external systems and services.

### 7. Priorities

Classify requirements as:

```text
Must Have
Should Have
Could Have
```

### 8. Requirement Traceability

For each important requirement, identify the technical capability that will eventually satisfy it.

Do **not** select the final Azure services yet.

---

# 📌 Key Takeaways

- Requirements are the foundation of solution architecture.
- Start with the **business problem**, not the Azure service.
- Business requirements describe desired business outcomes.
- Technical requirements describe the capabilities needed to achieve those outcomes.
- Functional requirements describe **what the system must do**.
- Non-functional requirements describe **how well the system must operate**.
- Availability, reliability, performance, scalability, security, compliance, and cost are important architectural requirements.
- RPO and RTO are business continuity requirements that influence architecture.
- Constraints limit the available architecture options.
- Assumptions must be validated.
- Dependencies must be identified.
- Requirements should be prioritized when they conflict.
- Requirement traceability connects business needs to technical decisions.
- A requirement should not prematurely dictate a specific Azure service.
- Good architecture starts with **understanding requirements before selecting technology**.

---

## 🔗 What's Next?

Now that we know how to identify and structure **business and technical requirements**, the next step is learning how a Solutions Architect uses those requirements to evaluate options and make architecture decisions.

➡️ **Next: [1.4 Architecture Decision-Making](../Architecture-Decision-Making/)**
