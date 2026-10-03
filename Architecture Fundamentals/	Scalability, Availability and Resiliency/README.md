# Scalability, Availability and Resiliency

## Overview

Scalability, availability, and resiliency are fundamental concepts in cloud architecture. They determine how well a solution can handle changing workloads, remain accessible, and recover from failures.

```text
Scalability
     ↓
Handle changing workload

Availability
     ↓
Keep services accessible

Resiliency
     ↓
Continue or recover from failures
```

---

## 1. Scalability

Scalability is the ability of a system to handle increasing or decreasing workload by adjusting resources.

There are two primary approaches:

### Vertical Scaling

Increasing the capacity of an existing resource.

```text
Small Resource
     ↓
Increase CPU / RAM
     ↓
Larger Resource
```

Example:

```text
4 vCPU / 16 GB RAM
        ↓
8 vCPU / 32 GB RAM
```

### Horizontal Scaling

Adding or removing multiple instances.

```text
Instance
   ↓
Instance + Instance
   ↓
Instance + Instance + Instance
```

Horizontal scaling is commonly used for distributed and highly available applications.

---

## 2. Elasticity

Elasticity is the ability to automatically adjust resources based on workload demand.

```text
Low Traffic
    ↓
Fewer Resources

High Traffic
    ↓
More Resources

Traffic Decreases
    ↓
Resources Scale Down
```

### Scalability vs Elasticity

| Concept | Meaning |
|---|---|
| Scalability | Ability to handle increased workload |
| Elasticity | Ability to dynamically adjust capacity based on demand |

---

## 3. Availability

Availability is the ability of a system to remain accessible and operational when users need it.

```text
Availability
      ↓
Service remains accessible
      ↓
Reduced Downtime
```

Availability is commonly expressed as a percentage.

| Availability | Approximate Annual Downtime |
|---|---:|
| 99% | 3.65 days |
| 99.9% | 8.76 hours |
| 99.99% | 52.6 minutes |
| 99.999% | 5.26 minutes |

Higher availability requirements generally require additional architecture and redundancy.

---

## 4. High Availability

High availability means designing systems to minimize service interruption.

A highly available architecture avoids relying on a single critical component.

```text
             ┌── Instance 1
Users → Load Balancer
             └── Instance 2
```

If one instance fails, another instance can continue serving requests.

---

## 5. Single Point of Failure

A **Single Point of Failure (SPOF)** is a component whose failure can cause the entire service or an important part of it to become unavailable.

```text
Users
  ↓
Single Server
  ↓
Database
```

If the single server fails:

```text
Users
  X
Server Failed
```

A resilient architecture identifies and reduces critical single points of failure.

---

## 6. Redundancy

Redundancy means having additional components that can provide service when another component fails.

```text
                ┌── Server A
Users → System ─┤
                └── Server B
```

If Server A fails:

```text
Server A ❌
Server B ✅
```

Redundancy is an important technique for improving availability.

---

## 7. Fault Tolerance

Fault tolerance is the ability of a system to continue operating despite the failure of one or more components.

```text
Component Failure
       ↓
Failure Detected
       ↓
Alternative Component
       ↓
Service Continues
```

The level of fault tolerance required depends on the workload and business requirements.

---

## 8. Resilience

Resilience is the ability of a system to **withstand failures, adapt to disruptions, and recover its normal operation**.

```text
Normal Operation
       ↓
Failure
       ↓
Detection
       ↓
Mitigation / Recovery
       ↓
Normal Operation
```

Resilience considers failures as an expected part of distributed systems.

---

## 9. Scalability vs Availability vs Resilience

| Concept | Main Question |
|---|---|
| Scalability | Can the system handle more workload? |
| Availability | Can users access the system when required? |
| Resilience | Can the system withstand and recover from failures? |

These concepts are related but solve different architectural problems.

---

## 10. Relationship Between the Concepts

A well-designed cloud architecture may require all three.

```text
                 Architecture
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
   Scalability    Availability   Resilience
        │             │             │
   Handle Load     Reduce         Handle
                  Downtime        Failures
```

For example:

```text
Multiple Instances
        ↓
Horizontal Scalability
        +
Redundancy
        ↓
High Availability
        +
Failure Recovery
        ↓
Resilient Architecture
```

---

## 11. Key Architecture Considerations

When designing a scalable and resilient solution, consider:

- Expected workload
- Traffic patterns
- Failure scenarios
- Redundancy requirements
- Scaling requirements
- Recovery requirements
- Dependencies
- Cost implications

Detailed Azure services and implementation strategies for these concepts will be covered in the later architecture sections.

---

## 12. Key Takeaway

A Solutions Architect should design systems that can:

```text
Handle changing demand
        ↓
Maintain availability
        ↓
Withstand failures
        ↓
Recover when necessary
```

The goal is not simply to add more resources, but to design an architecture that meets the workload's **scalability, availability, and resilience requirements**.
