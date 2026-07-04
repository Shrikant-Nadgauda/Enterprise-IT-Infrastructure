# 🛡 FortiGate Firewall Policies

> **Document:** `05-Firewall-Policies.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Firewall%20Policies-red?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Access%20Control-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Firewall Policies |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Access Control |

---

# 📖 Purpose

Firewall Policies define how traffic is allowed, denied, inspected, and logged as it traverses the FortiGate firewall.

Every packet entering the firewall is evaluated against the configured policy list. The first matching policy determines whether the traffic is permitted or blocked and which security services are applied before forwarding the packet.

A properly designed firewall policy framework is essential for maintaining enterprise security, regulatory compliance, and controlled network communication.

---

# 🎯 Design Objectives

- Control Network Access
- Enforce Security Policies
- Protect Internal Resources
- Restrict Unauthorized Traffic
- Enable Secure Business Applications
- Apply Threat Protection
- Log Security Events
- Simplify Policy Management

---

# 🏗 Enterprise Policy Architecture

```text
                 Incoming Traffic
                        │
                        ▼
               Incoming Interface
                        │
                        ▼
               Route Lookup Completed
                        │
                        ▼
            Firewall Policy Evaluation
                        │
            ┌───────────┴───────────┐
            │                       │
          Match                  No Match
            │                       │
            ▼                       ▼
     Apply Security           Implicit Deny
        Profiles                   │
            │                      ▼
            ▼                  Drop Packet
     NAT / VIP Processing
            │
            ▼
     Forward to Destination
```

---

# 📌 What is a Firewall Policy?

A Firewall Policy is a rule that defines how traffic should be handled between two network zones or interfaces.

Each policy specifies:

- Source
- Destination
- Service
- Action
- Schedule
- Security Inspection
- Logging

Only traffic matching all configured criteria is processed by the policy.

---

# 🧩 Components of a Firewall Policy

| Component | Purpose |
|-----------|---------|
| Incoming Interface | Where traffic enters |
| Outgoing Interface | Where traffic exits |
| Source Address | Source IP or Address Object |
| Destination Address | Destination IP or Address Object |
| Service | Allowed Protocols and Ports |
| Schedule | Time-based Access |
| Action | Allow or Deny |
| NAT | Source Address Translation |
| Security Profiles | IPS, AV, Web Filter, Application Control |
| Logging | Record Session Information |

---

# 🔄 Policy Evaluation Process

FortiGate processes firewall policies from **top to bottom**.

```text
Policy 1
    │
    ▼
Policy 2
    │
    ▼
Policy 3
    │
    ▼
Policy 4
    │
    ▼
Implicit Deny
```

The **first matching policy** is applied, and no further policies are evaluated.

---

# 🔍 Policy Matching Criteria

For a policy to match, the following attributes are evaluated:

- Incoming Interface
- Outgoing Interface
- Source Address
- Destination Address
- Service / Port
- Schedule
- User (if applicable)

If all conditions match, the policy is executed.

---

# 🔐 Security Profiles

Security Profiles provide Layer-7 inspection and advanced threat protection.

Common profiles include:

- Antivirus (AV)
- Intrusion Prevention System (IPS)
- Web Filtering
- DNS Filtering
- Application Control
- SSL Inspection
- Anti-Spam
- Data Leak Prevention (DLP)

These profiles are attached directly to firewall policies.

---

# 📄 Logging

Logging records traffic activity for monitoring, troubleshooting, auditing, and compliance.

Typical log events include:

- Allowed Sessions
- Denied Sessions
- Security Events
- VPN Connections
- Authentication Attempts
- IPS Detections
- Malware Detection

Logs can be forwarded to:

- FortiAnalyzer
- Syslog Server
- SIEM Platform
- Local Storage

---

# ⛔ Implicit Deny

At the end of the firewall policy table, FortiGate automatically applies an **Implicit Deny** rule.

```text
No Matching Policy

        │

        ▼

Implicit Deny

        │

        ▼

Traffic Blocked
```

This default behavior ensures that any traffic not explicitly permitted is automatically denied.

---

# 🌍 Typical Enterprise Policy Flow

```text
Users

↓

LAN Zone

↓

Firewall Policy

↓

Security Profiles

↓

NAT

↓

Internet
```

Another example:

```text
Branch Office

↓

IPSec VPN

↓

Firewall Policy

↓

Server VLAN

↓

Application Server
```

---

# 🛡 Firewall Policy Best Practices

- Follow the Principle of Least Privilege.
- Place frequently matched policies near the top.
- Use Address Objects instead of IP addresses.
- Use Service Objects instead of Any.
- Enable logging for critical policies.
- Review unused policies regularly.
- Remove duplicate rules.
- Document every policy.

---

# 🏢 Enterprise Deployment Example

| Source | Destination | Service | Action |
|---------|-------------|----------|--------|
| Users | Internet | HTTP/HTTPS | Allow |
| Users | File Server | SMB | Allow |
| Branch Office | Application Server | HTTPS | Allow |
| Guest Network | Internal LAN | Any | Deny |
| Internet | Published Web Server | HTTPS | Allow |

---

# 📈 Design Considerations

Before creating firewall policies, consider:

- Business Requirements
- User Access Needs
- Server Communication
- Internet Access
- VPN Connectivity
- Compliance Standards
- Security Inspection
- Future Scalability

---

# 📚 Related Documents

- 01-FortiGate-LLD.md
- 02-Interfaces.md
- 03-Security-Zones.md
- 04-Routing.md
- 06-NAT.md
- 07-Virtual-IP.md
- 09-VPN.md

---

# 📌 Summary

Firewall Policies are the core of FortiGate security. They determine which traffic is allowed, denied, inspected, translated, and logged. A well-designed policy structure improves security, simplifies administration, supports compliance, and ensures reliable communication across enterprise networks.

Enterprise environments rely on carefully planned firewall policies combined with security profiles, logging, and object-based configurations to enforce consistent and scalable access control.

> **Note:** This document focuses on the architectural design of firewall policies. Policy creation, object configuration, CLI commands, GUI implementation, policy troubleshooting, session analysis, and real-world configuration examples will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
06-NAT.md
```

The next document explains FortiGate Network Address Translation (NAT), including Source NAT (SNAT), Destination NAT (DNAT), Central NAT, IP Pools, NAT processing order, traffic translation, and enterprise best practices for secure and efficient address translation.
