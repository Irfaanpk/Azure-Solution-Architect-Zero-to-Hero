# Business Requirements → Technical Requirements

## 📖 Overview

A Solutions Architect does not begin architecture design by selecting Azure services.

The architecture process begins with understanding the **business requirements** and converting them into clear **technical requirements**.

This is one of the most important skills for an Azure Solutions Architect because real-world architecture decisions are driven by requirements.

```text
Business Problem
        ↓
Business Goals
        ↓
Business Requirements
        ↓
Technical Requirements
        ↓
Architecture Requirements
        ↓
Azure Service Selection
        ↓
Architecture Design
```

The key principle is:

> **Requirements drive architecture. Architecture drives technology selection.**

---

## 🎯 Why Requirement Analysis Is Important

A technically excellent Azure solution can still be the wrong solution if it does not satisfy the business requirements.

For example, imagine a company asks for:

> "A highly available application that can support global users."

If the architect only focuses on Azure services, they might immediately choose multiple services without understanding the actual requirements.

Instead, the architect should determine:

- How many users?
- Where are the users located?
- What availability level is required?
- What does "highly available" actually mean?
- What is the acceptable downtime?
- What is the acceptable data loss?
- How much traffic is expected?
- How quickly can the system recover?
- What is the budget?
- Are there compliance requirements?

Only after answering these questions should architecture decisions be made.

```text
Wrong Approach

Azure Services
      ↓
Architecture
      ↓
Try to fit the requirements


Better Approach

Business Requirements
      ↓
Technical Requirements
      ↓
Architecture
      ↓
Azure Services
```

---

# 🏢 Business Requirements

**Business requirements** describe what the organization wants to achieve.

They are usually expressed in business language rather than technical language.

Examples:

- Increase application availability
- Reduce operational costs
- Support global customers
- Improve application performance
- Protect customer information
- Meet regulatory requirements
- Support business growth
- Modernize legacy applications
- Reduce time to market
- Improve disaster recovery

### Example

A business requirement might be:

> "Customers should be able to access the application from anywhere in the world."

This is a business requirement.

The architect must translate it into technical requirements.

```text
Business Requirement
        ↓
Global User Access
        ↓
Global Traffic Management
        ↓
Regional Application Deployment
        ↓
Global Application Architecture
```

---

# 🔧 Technical Requirements

**Technical requirements** describe what the technology solution must provide to satisfy the business requirements.

Examples:

- Global traffic routing
- Multi-region deployment
- Autoscaling
- Encryption
- Identity-based access
- Network isolation
- Database replication
- Backup
- Monitoring
- Logging
- Failover
- Disaster recovery

For example:

```text
Business Requirement:
Application must support global customers.

Technical Requirements:
- Global traffic routing
- Regional application instances
- Regional failover
- Data replication
- Global monitoring
```

The technical requirements become the foundation of the architecture.

---

# 🔄 Business Requirement → Technical Requirement

The conversion process can be represented as:

```text
Business Requirement
        ↓
What does the business need?
        ↓
Why is it needed?
        ↓
What technical capability is required?
        ↓
What architecture can provide that capability?
        ↓
Which Azure services can implement it?
```

### Example

```text
Business:
Application must remain available.

        ↓

Technical:
Application must tolerate component failures.

        ↓

Architecture:
Use redundant application instances.

        ↓

Azure:
Use appropriate load balancing and
high-availability capabilities.
```

---

# 🧩 Functional Requirements

Functional requirements describe **what the system should do**.

They define the behavior and functionality of the application.

Examples:

- Users can register
- Users can log in
- Customers can place orders
- Customers can cancel orders
- Administrators can manage products
- Users can upload documents
- Applications can send notifications
- Reports can be generated
- Payments can be processed

### Example

```text
User
 ↓
Login
 ↓
Authentication
 ↓
Application
 ↓
View Account
```

Functional requirements answer:

> **"What should the system do?"**

---

# 🛡️ Non-Functional Requirements

Non-functional requirements describe **how the system should operate**.

They define the quality, performance, security, availability, and operational characteristics of the solution.

Common non-functional requirements include:

- Availability
- Reliability
- Performance
- Scalability
- Security
- Compliance
- Recoverability
- Maintainability
- Observability
- Cost efficiency

Non-functional requirements are extremely important for architecture decisions.

```text
Functional Requirement
        ↓
What should the system do?

Non-Functional Requirement
        ↓
How well should the system do it?
```

---

# 📊 Functional vs Non-Functional Requirements

| Area | Functional Requirement | Non-Functional Requirement |
|---|---|---|
| Meaning | What the system does | How the system operates |
| Focus | Features and behavior | Quality and constraints |
| Example | User can place an order | Order processing must complete within required latency |
| Example | User can log in | Authentication must meet security requirements |
| Example | User can upload files | Upload service must support required file size and availability |
| Example | Application processes payments | Payment processing must be reliable and secure |

Both types are required for complete architecture design.

---

# 🎯 Requirement Categories

A Solutions Architect should analyze requirements across multiple categories.

```text
                    Requirements
                          │
       ┌──────────────────┼──────────────────┐
       ↓                  ↓                  ↓
   Functional       Non-Functional       Constraints
       │                  │                  │
       ↓                  ↓                  ↓
 Features            Availability         Budget
 Behavior            Reliability          Timeline
 Workflows           Performance          Existing Systems
                     Scalability           Compliance
                     Security             Skills
                     Cost                 Dependencies
```

---

# 🟢 Availability Requirements

Availability requirements describe how much downtime the business can tolerate.

Instead of simply saying:

> "The application should be highly available."

The architect should ask:

- What availability percentage is required?
- Is downtime acceptable?
- How much downtime is acceptable?
- Which components are business-critical?
- What happens during a failure?
- Is multi-zone deployment required?
- Is multi-region deployment required?

### Example

```text
Requirement:
Critical application must have very high availability.

Technical Requirements:
- Redundant compute
- Failure detection
- Automatic failover
- Zone redundancy
- Reliable data layer
```

Availability requirements influence architecture directly.

---

# ⏱️ Performance Requirements

Performance requirements describe how quickly the solution should respond.

Important performance metrics include:

- Response time
- Latency
- Throughput
- Requests per second
- Processing time
- Database response time
- Network latency

### Example

Business requirement:

> "Customers should receive search results quickly."

Technical requirements might include:

```text
Low Application Latency
        +
Fast Database Queries
        +
Caching
        +
Efficient Network Routing
```

---

# 📈 Scalability Requirements

Scalability requirements describe how the system should handle growth.

Questions include:

- How many users are expected?
- How many requests per second?
- How much data will be generated?
- What is the expected growth?
- Are traffic spikes expected?
- Is scaling predictable or unpredictable?

### Example

```text
Normal Traffic
     ↓
2 Instances

Peak Traffic
     ↓
20 Instances
```

This may lead to requirements such as:

- Horizontal scaling
- Autoscaling
- Load distribution
- Scalable database
- Scalable storage

---

# 🔐 Security Requirements

Security requirements describe how the solution should protect:

- Users
- Applications
- Data
- Networks
- Secrets
- Infrastructure

Examples:

- Users must authenticate
- Administrative access must use strong authentication
- Sensitive data must be encrypted
- Applications should use managed identities
- Secrets must not be stored in source code
- Resources should use least-privilege access
- Network access should be restricted
- Sensitive services should use private connectivity

Example:

```text
Business Requirement:
Protect customer information.

Technical Requirements:
- Strong authentication
- Authorization
- Encryption
- Network isolation
- Secrets management
- Monitoring
- Auditing
```

---

# 📋 Compliance Requirements

Some organizations must comply with legal, regulatory, or industry requirements.

Examples may include:

- Data residency
- Data retention
- Audit requirements
- Encryption requirements
- Access control requirements
- Regulatory reporting
- Industry-specific security requirements

The architect must understand how compliance affects the design.

```text
Compliance Requirement
        ↓
Technical Control
        ↓
Architecture
        ↓
Azure Governance + Security
```

---

# 💾 Data Requirements

Data requirements describe how information should be stored, processed, protected, and accessed.

The architect should determine:

- Type of data
- Data size
- Data growth
- Access patterns
- Read/write ratio
- Data retention
- Data residency
- Backup requirements
- Recovery requirements
- Consistency requirements
- Performance requirements

### Example

```text
Data Requirement
      ↓
Relational Data?
      ↓
NoSQL Data?
      ↓
Object Data?
      ↓
Analytics Data?
      ↓
Select Appropriate Data Architecture
```

---

# 🌍 Geographic Requirements

Some applications have users or data distributed across different geographical locations.

Questions include:

- Where are users located?
- Where must data be stored?
- Is global access required?
- Is regional failover required?
- Are there data residency restrictions?
- What network latency is acceptable?

Example:

```text
Global Users
      ↓
Multiple Regions
      ↓
Regional Application Instances
      ↓
Regional Data Strategy
```

---

# 💰 Cost Requirements

Cost is also a business requirement.

Examples:

- Monthly budget
- Maximum infrastructure cost
- Cost reduction target
- Cost per transaction
- Cost per user
- Cost of disaster recovery

### Example

```text
Business Requirement:
Reduce infrastructure cost by 20%.

Technical Considerations:
- Right-size resources
- Autoscale workloads
- Use managed services where appropriate
- Remove unused resources
- Optimize storage tiers
- Review database tiers
```

Cost requirements must be balanced with other requirements.

---

# 🚨 Disaster Recovery Requirements

Disaster recovery requirements describe how the solution should behave after major failures.

Important concepts include:

- RPO
- RTO
- Backup
- Replication
- Failover
- Failback
- Recovery region

### RPO

**Recovery Point Objective** defines the maximum acceptable amount of data loss.

Example:

```text
RPO = 15 minutes
```

The business can tolerate losing approximately 15 minutes of data.

### RTO

**Recovery Time Objective** defines the maximum acceptable recovery time.

Example:

```text
RTO = 1 hour
```

The application should be restored within approximately one hour.

---

# 🔄 Requirement Prioritization

Requirements can conflict with each other.

For example:

```text
Higher Availability
        ↓
More Redundancy
        ↓
Higher Cost
```

Therefore, requirements must be prioritized.

A simple classification can be:

| Priority | Meaning |
|---|---|
| Critical | Must be satisfied |
| High | Very important |
| Medium | Important but flexible |
| Low | Nice to have |

### Example

```text
Critical:
Security

Critical:
Compliance

High:
Availability

High:
Performance

High:
Scalability

Medium:
Convenience

Low:
Optional Features
```

When requirements conflict, higher-priority requirements normally take precedence.

---

# ⚖️ Requirements and Trade-offs

Architecture is often about balancing competing requirements.

Example:

```text
High Availability
       +
Low Cost
       ↓
Trade-off Required
```

Another example:

```text
Maximum Performance
       +
Minimum Cost
       ↓
Trade-off Required
```

Another example:

```text
Maximum Control
       +
Minimum Operations
       ↓
Trade-off Required
```

The architect should identify these conflicts early.

---

# 🧱 Constraints vs Requirements

Requirements describe **what the solution needs**.

Constraints describe **what limits the solution**.

### Example

```text
Requirement:
Application must be highly available.

Constraint:
Budget is limited.

Architecture Challenge:
Design the highest practical availability
within the available budget.
```

### Common Constraints

- Budget
- Timeline
- Existing infrastructure
- Existing applications
- Existing databases
- Team skills
- Compliance
- Licensing
- Vendor contracts
- Data residency
- Legacy technology

---

# 🧠 Requirements Discovery Questions

A Solutions Architect should ask questions before designing the solution.

## Business Questions

- What business problem are we solving?
- What is the expected business outcome?
- Who are the users?
- How critical is the application?
- What happens if the application is unavailable?
- What is the expected business growth?

## Technical Questions

- What workload will the system handle?
- How many users are expected?
- What traffic is expected?
- What data is involved?
- What performance is required?
- What availability is required?
- What security controls are required?

## Operational Questions

- Who will manage the solution?
- How will it be monitored?
- How will incidents be handled?
- How will deployments happen?
- How will backups be managed?

## Disaster Recovery Questions

- What is the RPO?
- What is the RTO?
- What failures must the solution tolerate?
- Is regional recovery required?
- How frequently should backups run?

## Cost Questions

- What is the budget?
- Is cost optimization a major priority?
- What resources can scale?
- What resources can be reserved?
- What operational costs exist?

---

# 📝 Example: E-Commerce Application

## Business Requirements

A company wants to build an online shopping platform.

The business requires:

- Global customer access
- High availability
- Support for traffic spikes
- Secure customer information
- Reliable order processing
- Fast application response
- Disaster recovery
- Controlled infrastructure costs

---

## Convert Requirements to Technical Requirements

| Business Requirement | Technical Requirement |
|---|---|
| Global customers | Global traffic routing |
| High availability | Redundant application architecture |
| Traffic spikes | Horizontal scaling and autoscaling |
| Secure customer data | Identity, authorization, encryption |
| Reliable orders | Durable data storage and reliable messaging |
| Fast response | Performance optimization and caching where appropriate |
| Disaster recovery | Backup, replication, RPO/RTO strategy |
| Cost control | Right-sizing and autoscaling |

---

## Technical Architecture

```text
                         Global Users
                              ↓
                    Global Traffic Layer
                              ↓
              ┌───────────────┴───────────────┐
              ↓                               ↓
          Region A                         Region B
              ↓                               ↓
       Application Layer                Application Layer
              ↓                               ↓
          Messaging                       Messaging
              ↓                               ↓
           Database                        Database
              └───────────────┬───────────────┘
                              ↓
                           Storage

Supporting Architecture:

Identity
Security
Monitoring
Governance
Backup
Disaster Recovery
Cost Management
```

The architecture is derived from the requirements.

---

# 🔍 Requirement Traceability

A useful technique is to connect every major requirement to an architecture decision.

```text
Requirement
     ↓
Architecture Decision
     ↓
Azure Service / Technology
     ↓
Implementation
     ↓
Validation
```

### Example

```text
Requirement:
Global availability

        ↓

Architecture Decision:
Deploy application across multiple regions

        ↓

Technology:
Global traffic routing + regional application instances

        ↓

Implementation:
Configure regional endpoints and health-based routing

        ↓

Validation:
Test regional failure and failover
```

This approach helps ensure that architecture decisions have a clear reason.

---

# 📊 Requirement Traceability Matrix

A requirement traceability matrix can be used to map business requirements to technical architecture.

| ID | Business Requirement | Technical Requirement | Architecture Decision | Validation |
|---|---|---|---|---|
| R1 | Global access | Global traffic routing | Multi-region entry architecture | Global access test |
| R2 | High availability | Redundancy | Multiple application instances | Failure test |
| R3 | Traffic spikes | Autoscaling | Horizontal scaling | Load test |
| R4 | Data protection | Encryption + authorization | Secure data architecture | Security review |
| R5 | Fast recovery | Defined RPO/RTO | DR architecture | Recovery test |
| R6 | Cost control | Resource optimization | Right-sizing + autoscaling | Cost review |

This creates a clear relationship between **business needs and technical decisions**.

---

# 🧩 Example: Legacy Application Migration

Suppose a company has a legacy application running on-premises.

### Business Requirements

- Move the application to Azure
- Minimize downtime
- Keep the existing application mostly unchanged
- Improve disaster recovery
- Reduce physical infrastructure management

### Constraints

- Application cannot be significantly modified
- Legacy database dependency
- Limited migration window
- Existing team has limited cloud experience

### Technical Requirements

```text
Minimal Application Changes
        ↓
Migration With Low Refactoring
```

```text
Limited Downtime
        ↓
Migration Planning + Replication
```

```text
Improved DR
        ↓
Azure Recovery Architecture
```

The requirements and constraints influence the migration strategy.

---

# 🚫 Common Mistakes in Requirement Analysis

## 1. Starting With Azure Services

Bad:

```text
We should use AKS.
```

Better:

```text
What are the application requirements?
        ↓
What workload is expected?
        ↓
Do we need Kubernetes?
        ↓
Evaluate possible services.
```

---

## 2. Ignoring Non-Functional Requirements

An application may work functionally but still fail because:

- It is too slow
- It is not available enough
- It cannot scale
- It is insecure
- It cannot recover
- It costs too much

---

## 3. Using Vague Requirements

Bad:

> "The application should be fast."

Better:

> "The application should meet the defined response-time requirement under expected production load."

Bad:

> "The application should be highly available."

Better:

> "The application must meet the required availability target and tolerate defined infrastructure failures."

---

## 4. Ignoring Constraints

A technically ideal architecture may not be possible because of:

- Budget
- Time
- Existing applications
- Team skills
- Compliance

---

## 5. Ignoring Requirement Conflicts

Requirements can conflict.

Example:

```text
Maximum Availability
        +
Minimum Cost
        ↓
Architecture Trade-off
```

The architect must identify the conflict and discuss priorities.

---

## 6. Assuming Every Requirement Is Permanent

Requirements can change.

A good architecture should be able to evolve.

```text
Current Requirements
        ↓
Architecture
        ↓
Future Growth
        ↓
Architecture Evolution
```

---

# 🧠 Architect Thinking Pattern

When someone gives you a requirement, think:

```text
What?
 ↓
Why?
 ↓
Who?
 ↓
How many?
 ↓
How fast?
 ↓
How available?
 ↓
How secure?
 ↓
How scalable?
 ↓
How recoverable?
 ↓
How much does it cost?
 ↓
What are the constraints?
 ↓
What alternatives exist?
 ↓
What trade-offs exist?
```

This mindset helps prevent premature technology decisions.

---

# 🔗 Business Requirements → Architecture Decision

The complete process can be represented as:

```text
Business Goal
      ↓
Business Requirement
      ↓
Functional Requirement
      ↓
Non-Functional Requirement
      ↓
Constraints
      ↓
Priorities
      ↓
Technical Requirement
      ↓
Architecture Pattern
      ↓
Azure Service Options
      ↓
Alternative Evaluation
      ↓
Trade-off Analysis
      ↓
Final Architecture
      ↓
Implementation
      ↓
Validation
```

---

# 🎯 AZ-305 Perspective

For AZ-305, many scenario-based questions provide business and technical requirements and ask you to choose the **best architecture**.

The important process is:

```text
Read the Scenario
       ↓
Identify Business Goal
       ↓
Identify Functional Requirements
       ↓
Identify Non-Functional Requirements
       ↓
Identify Constraints
       ↓
Identify Priority Requirements
       ↓
Eliminate Incorrect Options
       ↓
Compare Remaining Solutions
       ↓
Select Best-Fit Architecture
```

Pay special attention to words such as:

- Must
- Required
- Minimum
- Maximum
- Only
- Cannot
- Should
- Prefer
- Cost-effective
- Highly available
- Minimal management
- Global
- Private
- Low latency
- Recoverable

These words often indicate important requirements or constraints.

---

# 🧪 Practical Exercise

## Scenario

A company wants to build a customer-facing application.

### Business Requirements

- Customers should access the application globally
- Application should remain available during infrastructure failures
- Traffic can increase during promotional events
- Customer information must be protected
- The company has a limited operations team
- The application should support future growth
- The company has a defined disaster recovery requirement
- Infrastructure costs must remain controlled

### Your Task

Identify:

1. Business requirements
2. Functional requirements
3. Non-functional requirements
4. Constraints
5. Availability requirements
6. Performance requirements
7. Scalability requirements
8. Security requirements
9. Data requirements
10. Disaster recovery requirements
11. Cost requirements
12. Technical requirements
13. Possible architecture patterns
14. Possible Azure services
15. Alternative solutions
16. Architecture trade-offs

Then create:

```text
Business Requirements
        ↓
Technical Requirements
        ↓
Architecture
        ↓
Azure Service Selection
        ↓
Trade-offs
        ↓
Final Recommendation
```

---

# 💡 Architect Thinking Exercise

Consider this requirement:

> "The application must be highly available, support global users, and have low operational overhead."

Do not immediately choose a service.

Break it down:

```text
Highly Available
        ↓
Redundancy + Failover

Global Users
        ↓
Global Traffic Management + Regional Architecture

Low Operational Overhead
        ↓
Managed Services
```

Now combine them:

```text
Business Requirements
        ↓
Technical Requirements
        ↓
Global + Highly Available
        +
Managed Platform
        ↓
Evaluate Azure Architecture Options
```

This is how an architect should approach the problem.

---

# 🔑 Key Takeaways

1. **Business requirements describe what the business wants to achieve.**
2. **Technical requirements describe what the technology must provide.**
3. **Functional requirements describe what the system does.**
4. **Non-functional requirements describe how the system should operate.**
5. **Constraints limit available architecture choices.**
6. **Requirements should be prioritized.**
7. **Availability, reliability, performance, scalability, security, cost, and DR are major architecture considerations.**
8. **Requirements should be measurable whenever possible.**
9. **Architecture decisions should be traceable back to requirements.**
10. **Do not select Azure services before understanding the requirements.**
11. **Evaluate alternatives before making major architecture decisions.**
12. **Understand trade-offs between competing requirements.**
13. **Consider both current and future requirements.**
14. **Document important requirements and architecture decisions.**
15. **The best architecture is the one that satisfies the important requirements within the constraints.**

---

# 📚 Summary

A Solutions Architect converts business needs into technical architecture.

The complete process is:

```text
Business Problem
       ↓
Business Goals
       ↓
Business Requirements
       ↓
Functional Requirements
       ↓
Non-Functional Requirements
       ↓
Constraints
       ↓
Priorities
       ↓
Technical Requirements
       ↓
Architecture Design
       ↓
Azure Service Selection
       ↓
Alternative Evaluation
       ↓
Trade-off Analysis
       ↓
Security
       ↓
Reliability
       ↓
Performance
       ↓
Scalability
       ↓
Disaster Recovery
       ↓
Cost
       ↓
Operations
       ↓
Implementation
       ↓
Validation
```

The most important principle is:

> **Do not start with the Azure service. Start with the requirement.**

> **Requirements drive architecture, and architecture drives technology selection.**

---

## 📚 What's Next?

In the next topic, we will learn about **architecture decision-making and trade-offs**, including how to compare multiple Azure solutions, evaluate alternatives, understand constraints, and select the best-fit architecture.

📂 **[Next → Architecture Decision Making](../Architecture%20Decision%20Making/)**

---
