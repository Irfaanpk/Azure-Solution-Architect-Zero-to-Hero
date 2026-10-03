# Security

## 1. Overview

Security is the ability of a workload to protect its data, systems, identities, and operations against unauthorized access, misuse, attacks, and other security threats.

The Azure Well-Architected Framework Security pillar focuses on protecting:

- Confidentiality
- Integrity
- Availability

Security should be considered throughout the workload lifecycle, from architecture and development to deployment, operations, monitoring, and incident response.

```text
Business Requirements
        ↓
Security Requirements
        ↓
Threat Analysis
        ↓
Security Architecture
        ↓
Implementation
        ↓
Monitoring & Detection
        ↓
Continuous Improvement
```

The objective is not to add security controls after an architecture has been designed. Security should influence architecture decisions from the beginning.

---

## 2. Security Design Principles

The Security pillar is based on five core design principles:

| Principle | Focus |
|---|---|
| Plan for security readiness | Establish security requirements, baselines, and responsibilities |
| Protect confidentiality | Prevent unauthorized access to sensitive information |
| Protect integrity | Prevent unauthorized modification of systems and data |
| Protect availability | Protect workloads against security-related disruptions |
| Sustain and evolve security posture | Continuously monitor, test, and improve security |

These principles provide the foundation for security-related architecture decisions.

---

## 3. Security Requirements

Security requirements should be identified before selecting Azure services or designing the architecture.

Important considerations include:

- Business criticality
- Data sensitivity
- Compliance requirements
- Regulatory requirements
- Identity requirements
- Network requirements
- Threat landscape
- Security responsibilities
- Operational capabilities

```text
Business Requirements
        ↓
Security Requirements
        ↓
Security Controls
        ↓
Architecture
```

Security requirements should be measurable where possible so that the architecture can be evaluated against them.

---

## 4. Security Baseline

A security baseline defines the minimum security expectations for the workload.

A baseline can include:

- Identity requirements
- Access-control requirements
- Network controls
- Encryption requirements
- Logging requirements
- Security monitoring
- Configuration standards
- Compliance requirements

```text
Security Baseline
       ↓
Implementation
       ↓
Assessment
       ↓
Gap Identification
       ↓
Improvement
```

The baseline should be regularly reviewed as threats, regulations, technology, and workload requirements change.

---

## 5. Secure Development Lifecycle

Security should be integrated throughout the software development lifecycle.

```text
Plan
 ↓
Design
 ↓
Develop
 ↓
Test
 ↓
Deploy
 ↓
Operate
 ↓
Improve
```

Security activities can include:

- Threat modeling
- Secure coding
- Dependency analysis
- Code scanning
- Infrastructure security checks
- Security testing
- Vulnerability management
- Security review

Security should not be treated as a final testing phase.

---

## 6. Threat Modeling

Threat modeling helps identify potential security threats before they become production issues.

A simplified process is:

```text
Identify Assets
      ↓
Identify Entry Points
      ↓
Identify Threats
      ↓
Analyze Risk
      ↓
Design Mitigations
      ↓
Validate Controls
```

Questions include:

- What are we protecting?
- Who could attack the system?
- How could an attacker access it?
- What could be compromised?
- What would the business impact be?
- Which controls reduce the risk?

Threat modeling should focus especially on critical user flows and sensitive assets.

---

## 7. Data Classification

Not all data requires the same level of protection.

Data can be classified according to its sensitivity and business impact.

Example:

| Classification | Example | Protection |
|---|---|---|
| Public | Public website content | Basic protection |
| Internal | Internal documentation | Access control |
| Confidential | Business information | Strong access control and encryption |
| Highly Sensitive | Financial or regulated data | Strict access, encryption, monitoring, and additional controls |

Classification should influence:

- Storage
- Access
- Encryption
- Retention
- Monitoring
- Backup
- Data transfer

```text
Data
 ↓
Classification
 ↓
Security Requirements
 ↓
Protection Controls
```

---

## 8. Identity and Access Management

Identity is a primary security boundary for modern cloud workloads.

A secure architecture should:

- Authenticate identities
- Authorize actions
- Apply least privilege
- Use role-based access
- Restrict privileged access
- Monitor access
- Review permissions
- Manage identity lifecycle

```text
Identity
   ↓
Authentication
   ↓
Authorization
   ↓
Least Privilege
   ↓
Auditing
```

Different identities may exist for:

- Human users
- Administrators
- Applications
- Workloads
- Automation
- Deployment systems

Identity-specific Azure implementation will be covered in the dedicated identity and security architecture sections later.

---

## 9. Least Privilege

Least privilege means providing only the permissions required to perform a specific task.

```text
Required Permission
        ↓
Minimum Access
        ↓
Limited Exposure
        ↓
Reduced Impact
```

Avoid assigning broad permissions when narrower permissions are sufficient.

Access should also be reviewed periodically because permissions can become excessive as workloads evolve.

---

## 10. Privileged Access

Administrative accounts represent a high-value target.

A secure architecture should consider:

- Separate administrative identities
- Strong authentication
- Conditional access
- Just-in-time access
- Privileged identity management
- Privileged access monitoring
- Auditing

```text
Normal User
     ↓
Standard Access

Administrator
     ↓
Privileged Access
     ↓
Additional Controls
     ↓
Monitoring & Audit
```

Privileged access should be minimized and carefully controlled.

---

## 11. Network Segmentation

Network segmentation limits communication between components and reduces the potential impact of a compromise.

```text
Internet
   ↓
Edge
   ↓
Application Boundary
   ↓
Application
   ↓
Data Boundary
   ↓
Database
```

Segmentation can be implemented using:

- Network boundaries
- Subnets
- Firewalls
- Network security controls
- Private connectivity
- Application-level authorization

Segmentation should be based on workload requirements and trust boundaries.

---

## 12. Defense in Depth

Defense in depth uses multiple security controls so that the failure of one control does not automatically expose the workload.

```text
                Users
                  ↓
           Identity Security
                  ↓
           Network Security
                  ↓
        Application Security
                  ↓
             Data Security
                  ↓
          Monitoring & Detection
```

A layered security strategy can reduce the impact of individual control failures.

---

## 13. Ingress and Egress Security

Network traffic should be controlled in both directions.

### Ingress

Traffic entering the workload.

```text
Internet
   ↓
Security Controls
   ↓
Application
```

### Egress

Traffic leaving the workload.

```text
Application
   ↓
Security Controls
   ↓
External Destination
```

Both inbound and outbound traffic should be evaluated according to the workload's trust boundaries and requirements.

---

## 14. Encryption

Encryption protects data from unauthorized disclosure and can also help protect data integrity.

Encryption should be considered for:

- Data at rest
- Data in transit
- Sensitive application data
- Backup data
- Secrets and credentials

```text
Sensitive Data
      ↓
Classification
      ↓
Encryption Requirement
      ↓
Key Management
      ↓
Monitoring
```

The encryption approach should align with the sensitivity and compliance requirements of the data.

---

## 15. Key Management

Encryption is only one part of data protection. Keys must also be securely managed.

Key-management considerations include:

- Key storage
- Access control
- Key rotation
- Key lifecycle
- Key recovery
- Monitoring
- Separation of responsibilities

The architecture should avoid unnecessary exposure of encryption keys to applications or users.

---

## 16. Resource Hardening

Hardening reduces the attack surface of workload components.

Examples include:

- Removing unnecessary services
- Disabling unused ports
- Removing unnecessary permissions
- Applying security updates
- Using secure configurations
- Restricting management access
- Reducing exposed interfaces

```text
Default Configuration
        ↓
Remove Unnecessary Exposure
        ↓
Restrict Access
        ↓
Secure Configuration
        ↓
Monitor
```

Hardening should be applied consistently across the workload.

---

## 17. Secrets Management

Application secrets should not be embedded directly into:

- Source code
- Configuration files
- Container images
- Scripts
- Public repositories

Examples of secrets include:

- Passwords
- API keys
- Connection strings
- Certificates
- Tokens

A secure approach is:

```text
Application
     ↓
Identity
     ↓
Secure Secret Store
     ↓
Secret
```

Secrets should have controlled access, auditing, and appropriate rotation processes.

---

## 18. Application Security

Application security should be incorporated into architecture and development.

Important areas include:

- Input validation
- Authentication
- Authorization
- Secure APIs
- Dependency security
- Secure configuration
- Error handling
- Security testing

```text
Application
   ├── Identity
   ├── Authorization
   ├── Input Validation
   ├── API Security
   └── Data Protection
```

Application security should be considered alongside infrastructure security.

---

## 19. Supply Chain Security

Modern applications often depend on:

- Open-source packages
- Third-party libraries
- Container images
- Build systems
- External services

These dependencies introduce supply-chain risks.

Security controls can include:

- Dependency scanning
- Package validation
- Image scanning
- Trusted repositories
- Build security
- Software composition analysis
- Artifact integrity

```text
Source Code
    ↓
Dependencies
    ↓
Build
    ↓
Artifact
    ↓
Deployment
```

Every stage can introduce security risks and should be considered in the security architecture.

---

## 20. Security Monitoring

Security monitoring provides visibility into suspicious activity and potential threats.

Monitor:

- Authentication events
- Authorization changes
- Resource changes
- Network activity
- Application activity
- Administrative actions
- Security alerts

```text
Workload
   ↓
Logs + Telemetry
   ↓
Aggregation
   ↓
Analysis
   ↓
Detection
   ↓
Alert
   ↓
Response
```

Monitoring should cover infrastructure, applications, identities, and operational activities.

---

## 21. Threat Detection

Security monitoring and threat detection work together.

```text
Activity
   ↓
Telemetry
   ↓
Detection Rules
   ↓
Suspicious Activity
   ↓
Alert
   ↓
Investigation
```

Detection mechanisms should be capable of identifying relevant threats and producing actionable signals for security operations.

---

## 22. Security Testing

Security controls should be tested rather than assumed to work.

Testing can include:

- Vulnerability assessment
- Penetration testing
- Dependency scanning
- Static analysis
- Dynamic analysis
- Configuration testing
- Identity testing
- Network security testing
- Threat detection testing

```text
Security Control
       ↓
Test
       ↓
Expected Result
       ↓
Observed Result
       ↓
Gap
       ↓
Improvement
```

Security testing should be continuous and prioritized according to workload risks.

---

## 23. Incident Response

A security architecture must include a response strategy for security incidents.

```text
Detection
   ↓
Triage
   ↓
Investigation
   ↓
Containment
   ↓
Eradication
   ↓
Recovery
   ↓
Lessons Learned
```

Incident response procedures should define:

- Who responds
- What actions are performed
- Which systems are affected
- How evidence is preserved
- How communication occurs
- How the workload is recovered
- How improvements are identified

Incident response procedures should also be tested periodically.

---

## 24. Security and Zero Trust

Zero Trust is an important security approach for modern cloud architectures.

The fundamental approach is:

```text
Never Automatically Trust
        ↓
Verify Explicitly
        ↓
Use Least Privilege
        ↓
Assume Breach
        ↓
Continuously Evaluate
```

Zero Trust should influence:

- Identity
- Network access
- Application access
- Data access
- Device trust
- Monitoring

It should be implemented as an architectural strategy rather than treated as a single Azure service.

---

## 25. Security Architecture Layers

A secure workload can be evaluated across multiple layers.

```text
                    Security
                       │
       ┌───────────────┼───────────────┐
       ↓               ↓               ↓
    Identity        Network         Application
       ↓               ↓               ↓
      Data         Infrastructure     Secrets
       ↓               ↓               ↓
              Monitoring & Detection
                       ↓
                Incident Response
```

Security controls should be applied according to the risks and requirements of each layer.

---

## 26. Security Trade-offs

Security decisions can affect other WAF pillars.

| Security Decision | Security Benefit | Possible Trade-off |
|---|---|---|
| Additional network controls | Better isolation | Increased complexity |
| Stronger encryption | Better data protection | Additional processing and management |
| Extensive monitoring | Better threat visibility | Additional cost |
| Strict access controls | Reduced unauthorized access | Increased operational effort |
| More security testing | Better security assurance | Additional development effort |

Security should not be considered independently from reliability, cost, operations, and performance.

---

## 27. Azure Capabilities for Security

Azure provides multiple capabilities that can support security architecture.

| Capability | Purpose |
|---|---|
| Microsoft Entra ID | Identity and access management |
| Azure RBAC | Resource authorization |
| Microsoft Defender for Cloud | Security posture management and workload protection |
| Azure Key Vault | Secrets, keys, and certificate management |
| Azure Firewall | Network traffic protection |
| Azure DDoS Protection | Protection against DDoS attacks |
| Microsoft Sentinel | Security information and event management |
| Azure Policy | Governance and security enforcement |
| Microsoft Defender for Containers | Container security |
| Microsoft Defender for Servers | Server security |
| Azure Monitor | Monitoring and telemetry |

The appropriate services should be selected based on workload requirements, threats, compliance needs, and operational capabilities.

---

## 28. Security Architecture Process

A practical security design process can be summarized as:

```text
1. Identify Business Requirements
              ↓
2. Identify Assets and Data
              ↓
3. Classify Data
              ↓
4. Identify Threats
              ↓
5. Define Security Requirements
              ↓
6. Design Identity and Access Controls
              ↓
7. Design Network and Segmentation Controls
              ↓
8. Protect Applications and Data
              ↓
9. Implement Monitoring and Detection
              ↓
10. Test Security Controls
              ↓
11. Prepare Incident Response
              ↓
12. Continuously Improve
```

This approach ensures that security is incorporated into the architecture rather than added after implementation.

---

## 29. Practical Lab

### Scenario

Design a secure three-tier web application.

### Requirements

- Public users must access the application.
- Application components should not be directly exposed to the internet.
- Database access must be restricted.
- Secrets must not be stored in application configuration.
- Administrative access must be controlled.
- Security events must be monitored.

### Architecture

```text
                         Internet
                            ↓
                     Security Boundary
                            ↓
                     Web / Entry Layer
                            ↓
                    Application Layer
                            ↓
                       Data Layer
                            ↓
                        Database

              Identity + Secrets + Monitoring
```

### Lab Objectives

1. Define security requirements.
2. Identify trust boundaries.
3. Design network segmentation.
4. Configure identity-based access.
5. Protect application secrets.
6. Restrict database access.
7. Enable security monitoring.
8. Test unauthorized access.
9. Review security logs.
10. Document the security architecture.

---

## 30. Architecture Scenario

### Requirement

A business application stores confidential customer information.

The organization requires:

- Restricted access
- Encryption
- Auditing
- Network isolation
- Threat detection
- Controlled administrative access

### Architecture Analysis

Consider:

```text
Customer
   ↓
Application Entry
   ↓
Application Layer
   ↓
Protected Data Layer
```

Evaluate:

- Who can access the application?
- Who can access the data?
- Which identities are used?
- Where are the trust boundaries?
- How is data protected?
- How are secrets managed?
- How is suspicious activity detected?
- How are administrative actions audited?
- What happens when a security incident occurs?

The goal is to design security controls based on the actual risk and business requirements.

---

## 31. Security Review Questions

Use these questions when reviewing an architecture:

### Identity

- Are all identities identified?
- Is least privilege applied?
- Are privileged accounts protected?
- Are access decisions auditable?

### Data

- Is sensitive data classified?
- Is encryption required?
- Are encryption keys protected?
- Are backups protected?

### Network

- Are trust boundaries clearly defined?
- Is unnecessary traffic blocked?
- Are ingress and egress flows controlled?
- Is the workload appropriately segmented?

### Application

- Is the application developed securely?
- Are dependencies monitored?
- Are secrets protected?
- Are security controls tested?

### Monitoring

- Are security events collected?
- Are threats detected?
- Are alerts actionable?
- Are logs protected from unauthorized modification?

### Incident Response

- Is there a defined response process?
- Are responsibilities clear?
- Is the recovery process tested?
- Are lessons learned incorporated into future improvements?

---

## 32. Key Takeaways

- Security should be designed from the beginning of the workload lifecycle.
- Security requirements should originate from business, technical, and compliance requirements.
- Protect confidentiality, integrity, and availability.
- Establish and continuously maintain a security baseline.
- Integrate security throughout the software development lifecycle.
- Classify data according to sensitivity and business impact.
- Apply least privilege to identities and access.
- Use segmentation and defense-in-depth to reduce attack impact.
- Protect data with appropriate encryption and key management.
- Harden workload components to reduce attack surface.
- Protect secrets using appropriate secure storage mechanisms.
- Monitor the workload for suspicious activity.
- Test security controls continuously.
- Maintain a documented and tested incident response process.
- Evaluate security decisions against reliability, cost, operations, and performance.
- Continuously improve the workload's security posture.

---

## 33. Study Checklist

Before completing this topic, you should be able to explain:

- [ ] What the Security pillar means in WAF
- [ ] The five Security design principles
- [ ] Security requirements and baselines
- [ ] Threat modeling
- [ ] Data classification
- [ ] Identity and access management
- [ ] Least privilege
- [ ] Privileged access
- [ ] Network segmentation
- [ ] Defense in depth
- [ ] Ingress and egress security
- [ ] Encryption and key management
- [ ] Resource hardening
- [ ] Secrets management
- [ ] Application security
- [ ] Supply-chain security
- [ ] Security monitoring
- [ ] Threat detection
- [ ] Security testing
- [ ] Incident response
- [ ] Zero Trust principles
- [ ] Security trade-offs
- [ ] Azure capabilities that support security
- [ ] How to perform a security-focused architecture review
