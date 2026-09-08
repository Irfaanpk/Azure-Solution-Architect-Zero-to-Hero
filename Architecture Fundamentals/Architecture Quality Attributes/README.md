# Architecture Quality Attributes

## Overview

Architecture quality attributes describe **how well a solution should operate**, rather than what features the application provides.

Functional requirements answer:

> **"What should the system do?"**

Quality attributes answer:

> **"How well should the system do it?"**

For example:

```text
Functional Requirement
        ↓
"Users can place an order."

Quality Requirements
        ↓
├── Order processing must be reliable
├── Response should be fast
├── Service should be highly available
├── Customer data must be secure
├── System should scale during peak traffic
└── System should be recoverable after failure
```

Quality attributes have a major influence on architecture.

A solution that provides all required features but is unreliable, insecure, too slow, or impossible to operate may still be considered a poor architecture.

---

# 1. What Are Architecture Quality Attributes?

A quality attribute is a characteristic that describes the **quality or operational behavior** of a system.

Common quality attributes include:

- Reliability
- Availability
- Resiliency
- Performance
- Scalability
- Security
- Maintainability
- Observability
- Recoverability
- Manageability
- Portability
- Usability

```text
                 Architecture Quality
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
    Reliability      Performance       Security
        │                │                │
        ▼                ▼                ▼
   Availability      Scalability     Maintainability
        │                │                │
        └────────────────┼────────────────┘
                         ▼
                    Architecture
```

Not every system needs the same quality level.

The required quality attributes depend on the **business and technical requirements**.

---

# 2. Why Quality Attributes Matter

Architecture decisions directly affect quality attributes.

For example:

```text
Requirement:
Application must remain available during
a single infrastructure failure.
```

This may lead to:

```text
Redundancy
    ↓
Multiple Instances
    ↓
Failure Isolation
    ↓
Health Monitoring
    ↓
Automatic Failover
```

Another example:

```text
Requirement:
Application must respond quickly.
        ↓
Performance Architecture
        ↓
├── Appropriate Compute
├── Caching
├── Database Optimization
├── Network Optimization
└── Efficient Application Design
```

Therefore:

> **Quality requirements drive architecture decisions.**

---

# 3. Functional vs Quality Requirements

| Type | Focus | Example |
|---|---|---|
| Functional | What the system does | Process an order |
| Quality | How well it operates | Process the order within 1 second |
| Functional | What capability exists | Users can upload files |
| Quality | Required behavior | Files must be securely stored |
| Functional | Business operation | Generate reports |
| Quality | Operational requirement | Reports must complete within 10 minutes |

A complete architecture considers both.

---

# 4. Reliability

**Reliability** is the ability of a system to perform its intended function consistently and correctly over time.

A reliable system should be able to handle expected failures without producing incorrect results.

### Example

An order processing system should not:

- Lose orders
- Process the same order incorrectly
- Corrupt transaction data
- Produce inconsistent results

```text
Customer
    ↓
Order Service
    ↓
Order Processing
    ↓
Database

Failure occurs
      ↓
System handles failure
      ↓
Order remains consistent
```

Reliability is about **correct and dependable operation**.

---

# 5. Availability

**Availability** describes how often a system is operational and accessible when users need it.

Availability is commonly expressed as a percentage.

Examples:

```text
99%
99.9%
99.95%
99.99%
99.999%
```

Higher availability generally requires more redundancy and more sophisticated architecture.

```text
Single Instance
      ↓
Single Point of Failure
      ↓
Lower Availability
```

Compared with:

```text
Multiple Instances
      ↓
Redundancy
      ↓
Failure Detection
      ↓
Failover
      ↓
Higher Availability
```

---

# 6. Availability and Downtime

Availability percentages can be translated into approximate allowable downtime.

For example:

| Availability | Approx. Annual Downtime |
|---|---:|
| 99% | 87.6 hours |
| 99.9% | 8.76 hours |
| 99.95% | 4.38 hours |
| 99.99% | 52.6 minutes |
| 99.999% | 5.26 minutes |

This demonstrates why a requirement such as:

> "The application must be highly available."

is not specific enough.

The architect should understand the actual business requirement.

---

# 7. Reliability vs Availability

These concepts are related but not identical.

### Availability

> Is the system accessible?

### Reliability

> Does the system consistently perform the correct operation?

Example:

```text
System A
Available
   ✓
But frequently returns incorrect results
   ✗
```

It may be available but unreliable.

Another system might:

```text
System B
Reliable when operating
   ✓
But frequently unavailable
   ✗
```

A good architecture considers both.

---

# 8. Resiliency

**Resiliency** is the ability of a system to continue operating or recover effectively when failures occur.

Failures can include:

- Application crashes
- VM failures
- Network failures
- Database failures
- Dependency failures
- Zone failures
- Regional failures

```text
Normal Operation
       ↓
Failure
       ↓
Detect
       ↓
Absorb / Isolate
       ↓
Recover
       ↓
Continue Operation
```

A resilient architecture assumes that failures **will happen**.

The goal is not to prevent every failure.

The goal is to design the system so failures have an acceptable impact.

---

# 9. Fault Tolerance

Fault tolerance is the ability of a system to continue operating despite the failure of one or more components.

Example:

```text
              Load Balancer
                   │
          ┌────────┼────────┐
          ▼        ▼        ▼
        App 1    App 2    App 3
          ✓        ✓        ✓
```

If App 1 fails:

```text
        App 1
          ✗
          
        App 2    App 3
          ✓        ✓
           \      /
            \    /
          Continue
```

The application can continue serving users.

Fault tolerance often requires redundancy and failure isolation.

---

# 10. Single Point of Failure

A **Single Point of Failure (SPOF)** is a component whose failure can cause the entire solution or a critical part of it to fail.

Example:

```text
Application
     │
     ▼
Single Database
     │
     X
  Failure
     │
     ▼
Application Failure
```

The architect should identify critical SPOFs.

A redundant architecture might look like:

```text
                 Application
                      │
               ┌──────┴──────┐
               ▼             ▼
           Database A    Database B
               │             │
               └──────┬──────┘
                      ▼
                High Availability
```

Not every SPOF must automatically be eliminated.

The architect should evaluate:

- Business impact
- Required availability
- Cost
- Complexity
- Recovery requirements

---

# 11. Performance

Performance describes how efficiently and quickly a system responds to workload.

Important performance measurements include:

- Response time
- Latency
- Throughput
- Transactions per second
- Requests per second
- Processing time

```text
User Request
     │
     ▼
Application
     │
     ▼
Database
     │
     ▼
Response

Total Response Time
= Network
+ Processing
+ Database
+ Other Dependencies
```

Performance requirements should be measurable whenever possible.

Instead of:

> "The application should be fast."

Prefer:

> "API requests should normally complete within 500 ms."

---

# 12. Latency

Latency is the time required for an operation or request to travel through a system and receive a response.

For distributed systems, latency can come from:

- Network distance
- Service-to-service communication
- Database queries
- External APIs
- Processing
- Storage access

```text
User
 │
 ▼
Region A
 │
 ▼
Application
 │
 ▼
Database
 │
 ▼
Response
```

If users are geographically far from the application, latency may increase.

Architecture may therefore consider:

- Regional deployment
- Global routing
- Caching
- Data locality
- Network optimization

---

# 13. Throughput

Throughput describes how much work a system can process during a given period.

Examples:

- 10,000 requests/second
- 5,000 transactions/minute
- 1 TB of data/hour

```text
Workload
  │
  ▼
System
  │
  ├── Request 1
  ├── Request 2
  ├── Request 3
  ├── ...
  └── Request 10,000
```

The architecture must be capable of handling the expected throughput.

---

# 14. Scalability

Scalability is the ability of a system to handle increasing workload.

Example:

```text
100 Users
    ↓
1,000 Users
    ↓
10,000 Users
    ↓
100,000 Users
    ↓
1,000,000 Users
```

A scalable architecture should be able to accommodate growth without requiring an unreasonable redesign.

---

# 15. Vertical Scaling

Vertical scaling means increasing the capacity of an individual resource.

```text
Before:

    Server
   4 CPU
   16 GB RAM


After:

    Server
   16 CPU
   64 GB RAM
```

Advantages:

- Simple
- Often easy to implement

Limitations:

- Resource limits
- Larger failure impact
- Can become expensive
- May require downtime depending on the platform

---

# 16. Horizontal Scaling

Horizontal scaling means adding more instances.

```text
Before:

      Application
           │
        Server 1


After:

      Application
           │
    ┌──────┼──────┐
    ▼      ▼      ▼
 Server 1 Server 2 Server 3
```

Advantages:

- Increased capacity
- Better redundancy
- Better fault tolerance
- Can support distributed workloads

Horizontal scaling is especially useful for cloud-native architectures.

---

# 17. Elasticity

Elasticity is the ability to dynamically adjust resources according to workload.

```text
Low Traffic
    ↓
2 Instances

High Traffic
    ↓
10 Instances

Traffic Decreases
    ↓
3 Instances
```

Elasticity can help:

- Handle traffic spikes
- Reduce unused capacity
- Improve cost efficiency

Scalability and elasticity are related, but elasticity emphasizes **dynamic adjustment based on workload**.

---

# 18. Security

Security is a core architecture quality attribute.

Security includes protection of:

- Identities
- Applications
- Networks
- Data
- Secrets
- Infrastructure

Important security principles include:

```text
Least Privilege
Defense in Depth
Zero Trust
Encryption
Strong Authentication
Secure Authorization
Network Isolation
Monitoring & Auditing
```

Security should be considered across the entire architecture.

```text
Users
  ↓
Identity
  ↓
Network
  ↓
Application
  ↓
Data
  ↓
Monitoring
```

Security is not a separate component added at the end.

---

# 19. Maintainability

Maintainability is the ease with which a system can be:

- Modified
- Updated
- Fixed
- Extended
- Refactored

A maintainable architecture generally has:

- Clear component boundaries
- Low unnecessary coupling
- Good documentation
- Automated deployment
- Standardized configuration
- Appropriate monitoring

```text
Poor Architecture
      ↓
Tightly Coupled Components
      ↓
Small Change
      ↓
Many Components Affected
```

Compared with:

```text
Well-Structured Architecture
      ↓
Clear Boundaries
      ↓
Localized Change
      ↓
Easier Maintenance
```

---

# 20. Observability

Observability is the ability to understand the internal state and behavior of a system from its external outputs.

Important observability signals include:

- Metrics
- Logs
- Traces

```text
                   Application
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
        Metrics        Logs         Traces
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                  Observability
```

Observability helps teams answer questions such as:

- Is the application healthy?
- Why is the application slow?
- Which component failed?
- Which dependency caused the problem?
- Which users are affected?

---

# 21. Recoverability

Recoverability describes how effectively a system can return to normal operation after a failure.

Examples:

- Restore from backup
- Recover a database
- Fail over to another region
- Restore application state
- Rebuild infrastructure

```text
Failure
   ↓
Detection
   ↓
Recovery Process
   ↓
Restore / Failover
   ↓
Service Available
```

Recoverability is closely related to business continuity and disaster recovery.

---

# 22. Manageability

Manageability describes how easily a system can be administered and operated.

Important considerations include:

- Centralized management
- Automation
- Monitoring
- Configuration management
- Deployment automation
- Standardization

A solution that requires manual intervention for every operational task may become difficult to manage at scale.

```text
Manual Operations
       ↓
High Operational Effort
       ↓
Higher Risk

Automation
       ↓
Consistent Operations
       ↓
Lower Operational Effort
```

---

# 23. Portability

Portability is the ability to move a workload between environments with limited changes.

Possible environments include:

- Azure
- On-premises
- Other cloud providers
- Hybrid environments

Portability may be important when:

- Vendor flexibility is required
- Hybrid deployment is expected
- Regulatory requirements exist
- Migration between environments is anticipated

However, portability often introduces additional complexity.

This is an architectural trade-off rather than an automatic requirement.

---

# 24. Usability

Usability describes how easily users can interact with the system.

Examples:

- Simple user experience
- Clear workflows
- Fast response
- Accessibility
- Consistent interfaces

For a Solutions Architect, usability may influence:

- Application architecture
- Performance
- Global deployment
- API design
- Caching
- Availability

User experience is therefore also affected by architectural decisions.

---

# 25. Quality Attributes Are Connected

Quality attributes should not be considered independently.

For example:

```text
Higher Availability
       │
       ▼
More Redundancy
       │
       ▼
Higher Cost
       │
       ▼
More Operational Complexity
```

Another example:

```text
Higher Security
       │
       ▼
Additional Controls
       │
       ▼
Potentially More Complexity
       │
       ▼
Potential User Experience Impact
```

Architecture is about balancing these qualities.

---

# 26. Quality Attributes and Architecture Decisions

A single architecture decision can affect multiple quality attributes.

Example:

> Choose a managed application platform.

Potential effects:

```text
Managed Platform
      │
      ├── Operations ↓
      ├── Maintenance ↓
      ├── Deployment Simplicity ↑
      ├── Infrastructure Control ↓
      └── Platform Dependency ↑
```

Another example:

> Add caching.

Potential effects:

```text
Caching
   │
   ├── Performance ↑
   ├── Database Load ↓
   ├── Scalability ↑
   ├── Complexity ↑
   └── Consistency Considerations ↑
```

Therefore, every significant decision should be evaluated across multiple quality attributes.

---

# 27. Quality Attribute Scenarios

Quality requirements should ideally be measurable.

Instead of:

> "The system should be reliable."

Define a scenario:

```text
Event:
Application instance fails

Expected Behavior:
Traffic is redirected to healthy instances

Target:
Service remains available

Measurement:
No significant user-visible interruption
```

Another example:

```text
Event:
Traffic increases significantly

Expected Behavior:
Application automatically scales

Target:
Maintain required response time

Measurement:
Response time remains below defined threshold
```

This makes quality requirements testable.

---

# 28. Quality Attribute Example

Consider an online banking application.

### Reliability

Transactions should not be lost or corrupted.

### Availability

Customers should be able to access the service when required.

### Performance

Account balances should load quickly.

### Scalability

The platform should handle increased traffic during peak periods.

### Security

Customer identity and financial data must be protected.

### Recoverability

The system should recover from major failures within the required time.

### Observability

Operations teams should be able to detect and investigate failures.

```text
                 Banking Application
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
    Reliability       Security        Availability
        │                │                │
        ├────────────────┼────────────────┤
        ▼                ▼                ▼
    Performance      Observability    Recoverability
                         │
                         ▼
                     Scalability
```

---

# 29. Quality Attributes and the Azure Well-Architected Framework

The Azure Well-Architected Framework organizes architecture guidance around five major pillars:

```text
       Azure Well-Architected Framework

                ┌───────────────┐
                │  Reliability  │
                └───────────────┘
                       │
     ┌─────────────────┼─────────────────┐
     ▼                 ▼                 ▼
 Security       Cost Optimization   Operational
                                     Excellence
                       │
                       ▼
             Performance Efficiency
```

The five pillars are:

1. **Reliability**
2. **Security**
3. **Cost Optimization**
4. **Operational Excellence**
5. **Performance Efficiency**

These pillars provide a structured way to evaluate Azure architectures.

Detailed Well-Architected Framework concepts will be covered separately in:

➡️ **02. Azure Well-Architected Framework**

The purpose of this topic is to understand the **general concept of architecture quality attributes** before applying the WAF in depth.

---

# 30. Quality Attributes in AZ-305

AZ-305 scenarios often provide requirements that indirectly describe quality attributes.

For example:

### Scenario

> "The application must continue operating if an Azure availability zone becomes unavailable."

This indicates:

```text
Requirement
    ↓
Zone Failure Tolerance
    ↓
Availability / Resiliency
```

### Scenario

> "The company has a small operations team and wants minimal infrastructure management."

This indicates:

```text
Requirement
    ↓
Low Operational Effort
    ↓
Operational Excellence / Manageability
```

### Scenario

> "The application must support sudden traffic spikes."

This indicates:

```text
Requirement
    ↓
Dynamic Capacity
    ↓
Scalability / Elasticity
```

### Scenario

> "Customer data must be protected from unauthorized access."

This indicates:

```text
Requirement
    ↓
Data Protection
    ↓
Security
```

Learning to recognize these signals is extremely useful for AZ-305 scenario questions.

---

# 31. Quality Attribute Decision Process

When a requirement specifies a quality attribute, use this process:

```text
Quality Requirement
        ↓
Define Measurement
        ↓
Identify Failure / Workload
        ↓
Determine Technical Capabilities
        ↓
Evaluate Architecture Options
        ↓
Select Appropriate Design
        ↓
Validate Requirement
```

Example:

```text
Requirement:
99.99% Availability
        ↓
Identify Failure Scenarios
        ↓
Redundancy
        ↓
Failover
        ↓
Monitoring
        ↓
Recovery
        ↓
Validate Availability Target
```

---

# 32. Quality Attributes vs Trade-offs

Improving one quality attribute can affect another.

Examples:

```text
More Redundancy
      ↓
Availability ↑
Cost ↑
Complexity ↑
```

```text
More Caching
      ↓
Performance ↑
Scalability ↑
Consistency Complexity ↑
```

```text
More Security Controls
      ↓
Security ↑
Operational Complexity ↑
Potential Usability Impact ↑
```

```text
Managed Services
      ↓
Operational Effort ↓
Infrastructure Control ↓
Platform Dependency ↑
```

These relationships are important when evaluating architecture options.

Detailed trade-off analysis will be covered in:

➡️ **1.9 Architecture Trade-offs**

---

# 33. Quality Attribute Checklist

When evaluating an architecture, ask:

### Reliability

- What happens when components fail?
- Can the system continue operating correctly?

### Availability

- How much downtime is acceptable?
- Are critical components redundant?

### Resiliency

- Can the system absorb failures?
- Can it recover automatically?

### Performance

- What response time is required?
- What throughput is required?

### Scalability

- How will the system handle growth?
- Can components scale independently?

### Security

- How are identities, applications, networks, and data protected?

### Maintainability

- How easy is the system to modify and troubleshoot?

### Observability

- Can the team understand system health and failures?

### Recoverability

- How quickly can the system recover?

### Manageability

- Can the operations team effectively operate the solution?

```text
Reliability
Availability
Resiliency
Performance
Scalability
Security
Maintainability
Observability
Recoverability
Manageability
        │
        ▼
Overall Architecture Quality
```

---

# 🎯 Practical Exercise

Design a high-level architecture for a **food delivery platform**.

The business provides these requirements:

- Users can place food orders.
- The platform must support 500,000 users.
- Traffic can increase significantly during weekends.
- Orders must not be lost.
- Customers expect fast responses.
- Customer data must be protected.
- The application should remain available during infrastructure failures.
- The operations team is small.
- The company wants to control costs.

Identify the quality attributes involved.

### Step 1 — Identify Quality Attributes

```text
Functional
├── Place Orders
└── Process Payments

Quality Attributes
├── Reliability
├── Availability
├── Performance
├── Scalability
├── Security
├── Observability
├── Recoverability
└── Cost
```

### Step 2 — Define Measurable Requirements

For example:

```text
Performance
→ Define acceptable response time

Availability
→ Define acceptable availability target

Scalability
→ Define expected peak workload

Recovery
→ Define RPO / RTO

Security
→ Define required protection controls
```

### Step 3 — Identify Architecture Impact

Determine which components may need:

- Redundancy
- Autoscaling
- Caching
- Messaging
- Monitoring
- Backup
- Disaster recovery
- Secure access

Do not focus on selecting the exact Azure services yet.

The goal is to understand **how quality requirements influence architecture**.

---

# 🧠 Key Takeaways

- Quality attributes describe **how well a system should operate**.
- Functional requirements describe what the system does.
- Quality requirements describe how well it performs those functions.
- Reliability, availability, resiliency, performance, scalability, security, maintainability, observability, recoverability, and manageability are important architecture qualities.
- Availability and reliability are related but different.
- Resilient architectures assume failures will occur and design for acceptable recovery.
- Scalability allows systems to handle increasing workloads.
- Vertical scaling increases the capacity of an existing resource.
- Horizontal scaling adds additional instances.
- Elasticity allows capacity to dynamically adjust to workload.
- Security should be considered throughout the architecture.
- Observability helps teams understand system behavior through metrics, logs, and traces.
- Quality attributes should be measurable whenever possible.
- Improving one quality attribute can affect cost, complexity, or other attributes.
- Architecture decisions should be evaluated against the quality attributes required by the business.
- The Azure Well-Architected Framework provides five major pillars for evaluating Azure architectures.
- AZ-305 scenarios often express quality attributes indirectly through business and technical requirements.

---

## 🔗 What's Next?

Now that we understand **what makes an architecture good and how quality attributes influence architecture**, the next topic focuses on the principles architects use when designing reliable, secure, scalable, and maintainable solutions.

➡️ **Next: [1.6 Architecture Design Principles](../Architecture-Design-Principles/)**
