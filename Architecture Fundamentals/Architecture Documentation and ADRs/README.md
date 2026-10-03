# Architecture Documentation and ADRs

## Overview

Architecture documentation explains **how a solution is structured**, while Architecture Decision Records (ADRs) capture **why important architectural decisions were made**.

```text
Architecture
     ↓
Documentation
     +
Decision Records
     ↓
Shared Understanding
```

Good documentation helps architects, developers, operations teams, and future maintainers understand the solution.

---

## 1. Why Architecture Documentation Matters

Architecture documentation helps teams:

- Understand the solution
- Communicate architecture clearly
- Review design decisions
- Onboard new team members
- Troubleshoot systems
- Track architectural changes

```text
Architecture
    ↓
Document
    ↓
Review
    ↓
Implement
    ↓
Maintain
```

---

## 2. Types of Architecture Documentation

Common architecture documentation includes:

| Document | Purpose |
|---|---|
| Architecture Diagram | Shows major components and relationships |
| Data Flow Diagram | Shows how data moves through the system |
| Network Diagram | Shows connectivity and network boundaries |
| Deployment Diagram | Shows where components are deployed |
| Architecture Decision Record | Explains important architectural decisions |

---

## 3. Logical Architecture

A logical architecture shows the **major components and their relationships** without focusing on implementation details.

```text
Users
  ↓
Application
  ↓
Business Services
  ↓
Database
  ↓
Storage
```

It helps stakeholders understand the system at a high level.

---

## 4. Physical Architecture

A physical architecture shows how the solution is deployed.

```text
Azure Region
    │
    ├── Virtual Network
    │      ├── Subnet A
    │      └── Subnet B
    │
    ├── Compute
    ├── Database
    └── Storage
```

Logical architecture explains **what exists**.

Physical architecture explains **where and how it is deployed**.

---

## 5. Architecture Diagrams

A good architecture diagram should clearly show:

- Major components
- Connections
- Data flow
- Trust boundaries
- External dependencies
- Deployment boundaries

Example:

```text
Users
  ↓
Application Entry Point
  ↓
Application
  ├── Cache
  ├── Messaging
  └── Database
```

Avoid adding unnecessary implementation details to high-level diagrams.

---

## 6. Data Flow

Data-flow documentation shows how information moves through the solution.

```text
User
 ↓
Application
 ↓
Processing
 ↓
Database
 ↓
Response
```

For more complex systems:

```text
Application
    │
    ├── Database
    ├── Storage
    ├── Messaging
    └── External API
```

Data flow helps identify dependencies and important integration points.

---

## 7. Architecture Decision Records

An **Architecture Decision Record (ADR)** documents an important architectural decision and the reasoning behind it.

A simple ADR structure is:

```text
Title
Context
Decision
Alternatives
Consequences
Status
```

---

## 8. ADR Example

### Decision

Use a managed application platform instead of self-managed virtual machines.

### Context

The application requires automatic scaling and the operations team is small.

### Alternatives

- Virtual Machines
- Managed application platform
- Container platform

### Decision

Use the managed application platform.

### Consequences

- Lower infrastructure management
- Easier scaling
- Reduced infrastructure control
- Platform-specific dependency

This makes the reasoning behind the decision clear.

---

## 9. ADR Status

An ADR can have a lifecycle such as:

```text
Proposed
   ↓
Accepted
   ↓
Implemented
   ↓
Superseded
```

A decision should remain documented even after the architecture changes.

---

## 10. What Should Be Documented?

Document decisions that have significant architectural impact.

Examples:

- Database technology
- Application architecture style
- Network architecture
- Identity approach
- Multi-region strategy
- Integration approach
- Data storage strategy
- Major security architecture decisions

Not every small configuration change requires an ADR.

---

## 11. Architecture Documentation Principles

Good architecture documentation should be:

- Clear
- Concise
- Current
- Consistent
- Easy to understand
- Easy to update

Avoid documentation that is:

```text
Too Detailed
     ↓
Difficult to Maintain
     ↓
Becomes Outdated
```

The goal is to document enough information to support understanding and decision-making.

---

## 12. Keep Documentation Close to the Architecture

For modern engineering teams, architecture documentation can be stored alongside the project.

Example:

```text
project/
│
├── README.md
├── architecture/
│   ├── solution.md
│   ├── diagrams/
│   └── decisions/
│       ├── 001-database.md
│       └── 002-network.md
│
└── infrastructure/
```

Keeping architecture documentation with the project makes changes easier to track.

---

## 13. Architecture Review

Documentation supports architecture reviews.

A review can validate:

```text
Requirements
     ↓
Architecture
     ↓
Security
     ↓
Reliability
     ↓
Performance
     ↓
Cost
```

The architecture can then be updated based on review findings.

---

## 14. Architecture Evolution

Architecture documentation should evolve with the system.

```text
Architecture v1
      ↓
Requirement Change
      ↓
Architecture v2
      ↓
ADR Updated
      ↓
Documentation Updated
```

Old decisions should not simply disappear.

They should remain traceable so the team understands how the architecture evolved.

---

## 15. Key Takeaways

- Architecture documentation explains the **structure of a solution**.
- Architecture diagrams communicate components, relationships, and flows.
- Logical architecture focuses on the solution structure.
- Physical architecture focuses on deployment.
- Data-flow and network diagrams help explain interactions and dependencies.
- ADRs document important decisions and the reasoning behind them.
- ADRs should capture context, alternatives, decisions, and consequences.
- Not every small technical change requires an ADR.
- Documentation should remain clear, concise, and current.
- Architecture documentation should evolve as the solution changes.

---

## 🎯 Practical Exercise

Create documentation for a simple web application architecture.

Include:

```text
1. High-Level Architecture Diagram
2. Logical Architecture
3. Physical Architecture
4. Data Flow
5. One Architecture Decision Record
```

Example ADR topics:

```text
Why was the database architecture selected?
Why was the application architecture style selected?
Why was the network architecture designed this way?
```

The goal is to explain not only:

> **"What did we build?"**

but also:

> **"Why did we build it this way?"**
