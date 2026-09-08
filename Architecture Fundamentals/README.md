# Architecture Decision-Making

## Overview

Architecture decision-making is the process of evaluating different technical options and selecting the solution that best satisfies the **business and technical requirements**.

A Solutions Architect rarely has only one possible solution.

For the same requirement, multiple architectures may be technically possible.

The architect must determine:

- Which options are available
- Which requirements each option satisfies
- What constraints apply
- What risks exist
- What trade-offs are involved
- Which option provides the best overall outcome

```text
Requirements
      ↓
Understand the Problem
      ↓
Identify Possible Options
      ↓
Define Evaluation Criteria
      ↓
Compare Options
      ↓
Analyze Risks & Trade-offs
      ↓
Select Solution
      ↓
Document Decision
      ↓
Validate Decision
```

The goal is not to find the **most powerful** technology.

The goal is to find the **most appropriate solution for the given situation**.

---

# 1. What Is an Architecture Decision?

An architecture decision is a choice that has a significant impact on the structure, behavior, security, cost, reliability, or operation of a solution.

Examples:

- Which compute platform should be used?
- Which database technology should be selected?
- Should the application be single-region or multi-region?
- Should communication be synchronous or asynchronous?
- Should the application use containers or serverless?
- Should a database be publicly accessible or privately connected?
- Should workloads use managed services or self-managed infrastructure?

```text
Business Requirement
        ↓
Architecture Question
        ↓
Available Options
        ↓
Evaluation
        ↓
Architecture Decision
```

---

# 2. Start With the Problem

A common mistake is starting with a technology.

For example:

```text
"I know Azure Kubernetes Service,
so let's use AKS."
```

This is not architecture decision-making.

A better approach is:

```text
Business Problem
      ↓
Requirements
      ↓
Workload Characteristics
      ↓
Possible Solutions
      ↓
Evaluate Options
      ↓
Select Technology
```

The technology should be the **result of the decision process**, not the starting point.

---

# 3. Understand the Decision Context

Before evaluating services, understand the situation.

Ask:

- What problem are we solving?
- What is the business objective?
- Who are the users?
- What workload are we supporting?
- What are the important requirements?
- What constraints exist?
- What assumptions are being made?
- What dependencies exist?
- What is most important to the business?

```text
Decision Context
      │
      ├── Business Goals
      ├── Requirements
      ├── Constraints
      ├── Assumptions
      ├── Dependencies
      └── Priorities
```

Without understanding the context, the decision may be technically correct but inappropriate for the business.

---

# 4. Identify the Architecture Question

The architect should clearly define **what decision needs to be made**.

### Example

Instead of:

> "We need a database."

Define the actual architecture question:

> "Which database architecture best supports a globally distributed application with high availability and predictable read performance?"

This makes the decision much easier to evaluate.

```text
Vague Question
     ↓
"We need a database."

Clear Architecture Question
     ↓
"Which database architecture satisfies
our availability, scalability, consistency,
performance, and cost requirements?"
```

---

# 5. Identify Possible Options

Once the problem is understood, identify realistic alternatives.

For example, for an application workload:

```text
Application Compute
       │
       ├── Virtual Machines
       ├── App Service
       ├── Container Apps
       ├── AKS
       └── Azure Functions
```

The architect should avoid comparing every service available in Azure.

Instead, identify options that are **realistic candidates for the workload**.

---

# 6. Define Evaluation Criteria

Options need to be compared against common criteria.

Typical architecture evaluation criteria include:

- Functional requirements
- Performance
- Scalability
- Availability
- Reliability
- Security
- Compliance
- Cost
- Operational complexity
- Skills required
- Integration
- Maintainability
- Flexibility
- Future growth

```text
                    Evaluation Criteria
                           │
       ┌───────────────────┼───────────────────┐
       ▼                   ▼                   ▼
   Performance          Security             Cost
       │                   │                   │
       ├───────────────────┼───────────────────┤
       ▼                   ▼                   ▼
   Scalability         Availability       Operations
```

The criteria should come from the requirements.

---

# 7. Not Every Criterion Has Equal Importance

Some requirements are more important than others.

For example:

```text
Security        → Critical
Availability   → Critical
Performance    → High
Cost           → Medium
Flexibility    → Low
```

This means an option that is cheaper but fails the security requirement should not win.

```text
Critical Requirement
        ↓
Must Be Satisfied

Important Requirement
        ↓
Should Be Optimized

Optional Requirement
        ↓
Can Be Considered
```

Architecture decisions should reflect business priorities.

---

# 8. Eliminate Invalid Options

Before detailed comparison, remove options that cannot satisfy mandatory requirements.

Example:

Requirement:

> Application must support a specific runtime that is not supported by a particular managed platform.

That platform can be eliminated.

```text
Possible Options
      │
      ├── Option A → Meets mandatory requirements ✓
      ├── Option B → Meets mandatory requirements ✓
      ├── Option C → Fails mandatory requirement ✗
      └── Option D → Meets mandatory requirements ✓
                         │
                         ▼
                  Remove Option C
```

This reduces unnecessary analysis.

---

# 9. Compare Options

After eliminating unsuitable options, compare the remaining candidates.

Example:

| Criteria | Option A | Option B | Option C |
|---|---|---|---|
| Performance | High | High | Medium |
| Scalability | High | High | Medium |
| Availability | High | High | High |
| Security | High | High | Medium |
| Operations | Low effort | Medium effort | High effort |
| Cost | Medium | Low | High |
| Flexibility | Medium | High | High |

The architect then determines which option best matches the requirements.

---

# 10. Weighted Decision Matrix

A weighted decision matrix can be used when several criteria have different levels of importance.

Example:

| Criteria | Weight |
|---|---:|
| Security | 30% |
| Reliability | 25% |
| Performance | 20% |
| Cost | 15% |
| Operations | 10% |
| **Total** | **100%** |

Now score each option.

```text
Option A
Security      → 9
Reliability   → 9
Performance   → 8
Cost          → 6
Operations    → 8
```

The weighted score helps provide a structured comparison.

### Example Formula

```text
Weighted Score =
(Criterion Score × Criterion Weight)
+ ...
```

The matrix does not automatically make the decision.

It helps the architect make the reasoning **transparent and consistent**.

---

# 11. Architecture Decision Example

Suppose a company needs to host a web application.

### Requirements

- Highly available
- Automatically scalable
- Minimal infrastructure management
- Secure
- Moderate cost
- Development team has limited infrastructure expertise

Possible options:

```text
Option A → Virtual Machines
Option B → App Service
Option C → AKS
```

The architect evaluates them.

### Virtual Machines

Advantages:

- High control
- Flexible

Disadvantages:

- More infrastructure management
- Patching responsibility
- Scaling requires more management

### App Service

Advantages:

- Managed platform
- Easier operations
- Built-in scaling capabilities
- Good fit for web applications

Disadvantages:

- Less infrastructure-level control
- Platform constraints

### AKS

Advantages:

- Highly flexible container orchestration
- Strong control over container workloads

Disadvantages:

- Greater operational complexity
- Requires more Kubernetes expertise

The decision may favor a managed application platform if the requirements prioritize **low operational effort**.

The important point is not the service itself.

The important point is the **reasoning behind the selection**.

---

# 12. Functional Fit vs Architectural Fit

A service may technically support a workload but still be a poor architectural choice.

### Functional Fit

> "Can the service do what we need?"

### Architectural Fit

> "Is the service appropriate for the complete solution?"

For example:

```text
Service
  │
  ├── Functional Fit ✓
  │
  ├── Performance Fit ✓
  │
  ├── Security Fit ✓
  │
  ├── Operational Fit ✗
  │
  └── Cost Fit ✗
```

A service should be evaluated across the entire architecture.

---

# 13. Consider Dependencies

A decision can affect other components.

Example:

```text
Database Decision
       │
       ├── Network
       ├── Security
       ├── Identity
       ├── Backup
       ├── Monitoring
       ├── Application
       └── Disaster Recovery
```

Therefore, architects should ask:

> "What else changes if we make this decision?"

This prevents isolated decisions from causing problems elsewhere.

---

# 14. Analyze Risks

Every architecture option has risks.

Examples:

- Vendor limitations
- Service availability
- Operational complexity
- Skill requirements
- Performance limitations
- Security risks
- Cost uncertainty
- Dependency failures
- Migration complexity

A simple risk process is:

```text
Identify Risk
      ↓
Estimate Impact
      ↓
Estimate Likelihood
      ↓
Determine Mitigation
      ↓
Accept / Reduce / Avoid
```

### Example

```text
Decision:
Use a managed database.

Risk:
Application depends heavily on
a specific platform feature.

Mitigation:
Validate platform capabilities,
document dependency, and design
an appropriate migration strategy.
```

---

# 15. Consider the Cost of Complexity

More technology does not always mean better architecture.

For example:

```text
Simple Application
      │
      ▼
Highly Complex Microservices
Architecture
      │
      ▼
Unnecessary Operational Burden
```

The architect should consider:

- Number of components
- Number of dependencies
- Operational overhead
- Monitoring complexity
- Deployment complexity
- Troubleshooting complexity
- Required skills

A simpler architecture may be the better architecture when requirements do not justify additional complexity.

---

# 16. Managed Services vs Self-Managed Infrastructure

One common architecture decision is how much infrastructure should be managed by the organization.

### Self-Managed

```text
Organization
     │
     ├── OS
     ├── Patching
     ├── Scaling
     ├── Availability
     └── Infrastructure
```

### Managed Service

```text
Azure
     │
     ├── Platform Management
     ├── Infrastructure Management
     ├── Scaling Capabilities
     └── Service Operations

Organization
     │
     └── Application / Configuration
```

Managed services can reduce operational effort, but may introduce:

- Platform limitations
- Different pricing
- Reduced infrastructure control
- Service-specific dependencies

The correct choice depends on requirements.

---

# 17. Architecture Decisions Should Be Reversible When Possible

Some decisions are easy to change.

Others are difficult and expensive to reverse.

### Easier to Change

```text
Application Configuration
        ↓
Small Deployment Change
```

### Difficult to Change

```text
Database Architecture
        ↓
Large Data Migration
        ↓
Application Changes
        ↓
Testing
        ↓
Downtime / Migration Risk
```

Architects should give more attention to decisions that are:

- Expensive to change
- Difficult to reverse
- Broadly impactful
- Security-sensitive
- Data-related

---

# 18. One-Way Door vs Two-Way Door Decisions

Some architecture decisions are relatively easy to change.

These can be considered **two-way door decisions**.

```text
Option A ←→ Option B
```

Other decisions are difficult to reverse.

These are often considered **one-way door decisions**.

```text
Option A
   │
   ▼
Large Investment
   │
   ▼
Difficult Migration
   │
   ▼
Option B
```

Architects should spend more analysis effort on difficult-to-reverse decisions.

---

# 19. Consider Future Growth

An architecture decision should not only solve today's problem.

The architect should understand expected future changes.

Questions include:

- Will the number of users increase?
- Will data volume increase?
- Will new regions be added?
- Will new applications integrate with the system?
- Will compliance requirements change?
- Will the workload become more distributed?

```text
Today
  ↓
Current Requirements
  ↓
Architecture
  ↓
Future Growth
  ↓
Can Architecture Evolve?
```

This does not mean overengineering for every possible future scenario.

The goal is to provide **reasonable flexibility without unnecessary complexity**.

---

# 20. Consider Operational Capability

An architecture must match the organization's ability to operate it.

Example:

```text
Organization
    │
    ├── Small Operations Team
    ├── Limited Kubernetes Skills
    └── Limited Infrastructure Expertise
```

A highly complex platform may not be appropriate even if it provides excellent technical capabilities.

The architect should consider:

- Available skills
- Operational maturity
- Support model
- Monitoring capabilities
- Deployment maturity
- Incident response capabilities

Architecture must be **operable**, not just technically possible.

---

# 21. Security as a Decision Criterion

Security should be considered during architecture decisions rather than added later.

For each option, evaluate:

- Authentication
- Authorization
- Network isolation
- Encryption
- Secrets management
- Logging
- Auditing
- Compliance

```text
Architecture Option
       │
       ▼
Security Evaluation
       │
 ┌─────┼─────┐
 ▼     ▼     ▼
Identity Network Data
```

An option that fails a mandatory security requirement should normally be eliminated.

---

# 22. Validate the Decision

Before finalizing an architecture decision, validate it against the original requirements.

```text
Architecture Decision
        ↓
Requirements Check
        ↓
Security Check
        ↓
Performance Check
        ↓
Reliability Check
        ↓
Cost Check
        ↓
Operational Check
        ↓
Final Decision
```

Ask:

> "Does this decision actually solve the problem?"

If the answer is no, return to the alternatives.

---

# 23. Document Important Decisions

Important architecture decisions should be documented.

A simple decision record can contain:

```text
Decision
──────────────
What are we deciding?

Context
──────────────
Why is the decision required?

Options
──────────────
What alternatives were considered?

Decision
──────────────
Which option was selected?

Reason
──────────────
Why was it selected?

Consequences
──────────────
What are the benefits, limitations,
risks, and trade-offs?
```

This prevents teams from repeatedly asking:

> "Why did we choose this architecture?"

Detailed ADR structure is covered in **1.10 Architecture Documentation and ADRs**.

---

# 24. Architecture Decision Process

A reusable decision-making process is:

```text
                1. Understand
                     │
                     ▼
               Business Problem
                     │
                     ▼
                2. Analyze
                     │
                     ▼
          Requirements & Constraints
                     │
                     ▼
                3. Identify
                     │
                     ▼
             Possible Options
                     │
                     ▼
                4. Evaluate
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
    Security     Reliability      Cost
       │             │             │
       └─────────────┼─────────────┘
                     ▼
                5. Compare
                     │
                     ▼
               Trade-offs
                     │
                     ▼
                6. Decide
                     │
                     ▼
            Selected Architecture
                     │
                     ▼
                7. Validate
                     │
                     ▼
             Requirements Met?
                │          │
               Yes         No
                │           │
                ▼           └──────→ Re-evaluate
             8. Document
```

---

# 25. Example: Choosing Application Architecture

Suppose a company is building a new application.

The options are:

```text
                 Application
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
     Monolith     Modular       Microservices
                  Monolith
```

### Requirements

- Small development team
- Moderate workload
- Fast initial delivery
- Limited operational complexity
- Expected future growth

The architect should not automatically choose microservices.

A modular monolith may provide:

- Lower operational complexity
- Faster development
- Clear internal boundaries
- Easier deployment

while still allowing future evolution.

The decision depends on the actual requirements.

---

# 26. Example: Single Region vs Multi-Region

Suppose an application must remain available during a regional Azure outage.

Possible architectures:

```text
Option A
Single Region
    │
    ▼
Lower Complexity
Lower Cost
Higher Regional Risk
```

```text
Option B
Multi-Region
    │
    ▼
Higher Availability
Higher Complexity
Higher Cost
```

The architect needs to determine:

- Required RTO
- Required RPO
- Business impact of regional failure
- Data replication requirements
- Cost tolerance
- Operational capabilities

The correct answer depends on the requirements.

---

# 27. Example: Synchronous vs Asynchronous Communication

Suppose an order service needs to trigger several downstream operations.

### Synchronous

```text
Order Service
     │
     ├── Payment Service
     │
     ├── Inventory Service
     │
     └── Notification Service
```

The request waits for downstream responses.

### Asynchronous

```text
Order Service
      │
      ▼
    Queue
      │
 ┌────┼────┐
 ▼    ▼    ▼
Payment Inventory Notification
```

Asynchronous architecture may improve decoupling and resilience, but introduces additional components and eventual consistency considerations.

The architect must evaluate the requirements before choosing.

---

# 28. Avoid Architecture by Popularity

A technology should not be selected simply because:

- It is popular
- Other companies use it
- It is the newest service
- It is more advanced
- The architect has experience with it
- The development team prefers it

Instead:

```text
Requirements
     ↓
Architecture Fit
     ↓
Technical Fit
     ↓
Operational Fit
     ↓
Business Fit
     ↓
Decision
```

Technology popularity is not a substitute for architectural reasoning.

---

# 29. Architecture Decision Anti-Patterns

## ❌ Technology-First Decisions

```text
Technology
    ↓
Find a Problem for It
```

Instead:

```text
Problem
    ↓
Requirements
    ↓
Technology
```

---

## ❌ Single-Criteria Optimization

Example:

> "Choose the cheapest service."

The cheapest service may not satisfy:

- Security
- Availability
- Performance
- Scalability

---

## ❌ Overengineering

```text
Simple Requirement
       ↓
Complex Architecture
       ↓
Unnecessary Cost
```

---

## ❌ Ignoring Operations

A technically impressive architecture may fail because the organization cannot operate it.

---

## ❌ Ignoring Future Change

A design that completely blocks reasonable future growth can create expensive migration work later.

---

## ❌ No Decision Documentation

Without documentation:

```text
Decision
   ↓
Time Passes
   ↓
Team Changes
   ↓
"Why did we choose this?"
```

---

# 30. AZ-305 Decision-Making Approach

For an AZ-305 scenario, use this process:

```text
Step 1
Read the complete scenario
        ↓
Step 2
Identify the business objective
        ↓
Step 3
Identify mandatory requirements
        ↓
Step 4
Identify constraints
        ↓
Step 5
Identify important priorities
        ↓
Step 6
Determine the architecture category
        ↓
Step 7
Eliminate unsuitable options
        ↓
Step 8
Compare remaining options
        ↓
Step 9
Check security, reliability,
performance, operations, and cost
        ↓
Step 10
Select the option that best
satisfies the requirements
```

### Important AZ-305 Rule

Do not select an answer because:

> "This service is more powerful."

Select it because:

> **"This service best satisfies the stated requirements and constraints."**

---

# 31. Architecture Decision Checklist

Before finalizing an important decision, ask:

### Requirements

- Does it satisfy the business requirement?
- Does it satisfy the technical requirement?
- Does it satisfy mandatory requirements?

### Security

- Is it secure?
- Does it meet access requirements?
- Does it satisfy compliance requirements?

### Reliability

- What happens if the component fails?
- Is redundancy required?
- Can the system recover?

### Performance

- Can it handle the expected workload?
- Can it meet latency requirements?

### Scalability

- Can it handle future growth?
- Can it scale horizontally or vertically as required?

### Operations

- Can the team operate it?
- Can it be monitored?
- Can it be deployed and maintained effectively?

### Cost

- Is the cost appropriate?
- Are there hidden operational costs?

### Future

- Can the architecture evolve?
- Is the decision difficult to reverse?

```text
Requirements ✓
Security ✓
Reliability ✓
Performance ✓
Scalability ✓
Operations ✓
Cost ✓
Future Growth ✓
        │
        ▼
Architecture Decision
```

---

# 🧠 Key Takeaways

- Architecture decision-making is the process of choosing the most appropriate solution from multiple possible options.
- Start with the **problem and requirements**, not the technology.
- Clearly define the architecture question before evaluating services.
- Identify realistic alternatives.
- Evaluate options using criteria derived from requirements.
- Mandatory requirements should be satisfied before optimizing secondary concerns.
- Eliminate options that cannot meet critical requirements.
- Use structured comparisons when multiple options remain.
- Weighted decision matrices can help compare complex alternatives.
- Consider dependencies and the impact of decisions on the wider architecture.
- Evaluate risks, operational complexity, security, performance, scalability, and cost.
- Prefer appropriate simplicity over unnecessary complexity.
- Consider whether decisions are easy or difficult to reverse.
- Architecture should support reasonable future growth without overengineering.
- Important decisions should be documented and communicated.
- For AZ-305, always choose the option that best satisfies the **requirements, constraints, and priorities**.

---

## 🎯 Practical Exercise

Design a solution for a company that needs to host a business-critical web application.

### Requirements

- High availability
- Automatic scaling
- Secure access
- Minimal infrastructure management
- Predictable monthly cost
- Small operations team

### Architecture Decision

Evaluate three possible compute approaches:

```text
Option A → Virtual Machines
Option B → Managed Application Platform
Option C → Kubernetes Platform
```

Create a decision matrix using:

| Criteria | Weight |
|---|---:|
| Availability | 25% |
| Scalability | 20% |
| Security | 20% |
| Operations | 20% |
| Cost | 15% |

Then:

1. Score each option.
2. Calculate the weighted score.
3. Identify the strongest candidate.
4. Identify the biggest trade-off.
5. Identify one risk.
6. Explain why the selected option fits the requirements.
7. Explain why the other options were not selected.

The objective is **not** to find a universally best service.

The objective is to demonstrate the **architecture decision-making process**.

---

## 🔗 What's Next?

Now that we understand how architects **evaluate options and make architecture decisions**, the next topic focuses on how we determine whether an architecture is successful by examining its quality attributes.

➡️ **Next: [1.5 Architecture Quality Attributes](../Architecture-Quality-Attributes/)**
