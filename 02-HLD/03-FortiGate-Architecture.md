# 🛡 FortiGate Firewall Architecture

> **Document:** `03-FortiGate-Architecture.md`

![FortiGate](https://img.shields.io/badge/Fortinet-FortiGate-red?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-NGFW-blue?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Documentation-HLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Firewall Architecture |
| Document Type | High-Level Design (HLD) |
| Security Device | FortiGate Next Generation Firewall |
| Environment | Production |

---

# 📖 Introduction

The **FortiGate Firewall** is the central security gateway of the enterprise network.

Every packet entering or leaving the organization passes through the firewall before reaching its destination. It protects internal infrastructure from unauthorized access while allowing legitimate business traffic.

Rather than acting as only a firewall, FortiGate performs multiple security functions including routing, VPN, NAT, traffic inspection, logging, and access control.

This document explains the architectural role of FortiGate within the enterprise infrastructure.

---

# 🎯 Business Objectives

- Protect Enterprise Network
- Secure Internet Access
- Secure Branch Connectivity
- Control User Traffic
- Publish Internal Applications Securely
- Monitor Network Activity
- Provide Centralized Security

---

# 🏢 FortiGate Position in Enterprise

```text
                 🌐 Internet
                      │
                Public IP Address
                      │
             🛡 FortiGate Firewall
        ┌─────────────┼──────────────┐
        │             │              │
        ▼             ▼              ▼

   Internal LAN     VPN Users     Branch VPN

        │
        ▼

   Layer-3 Core Switch

        │

Servers • Users • Microsoft Cloud
```

---

# 🎯 Primary Responsibilities

| Function | Description |
|----------|-------------|
| Firewall | Allow / Deny Network Traffic |
| Routing | Route Internal & External Traffic |
| NAT | Public & Private Address Translation |
| VPN | Secure Site-to-Site Connectivity |
| Security Inspection | Inspect Network Traffic |
| Logging | Record Security Events |
| Access Control | Enforce Security Policies |

---

# 🌐 Network Interfaces

A typical enterprise FortiGate deployment contains multiple logical or physical interfaces.

| Interface | Purpose |
|-----------|----------|
| WAN | Internet Connectivity |
| LAN | Internal Users |
| Server Network | Datacenter Servers |
| Management | Firewall Administration |
| VPN | IPSec Tunnel Interfaces |
| DMZ *(Optional)* | Public Facing Servers |

---

# 🔥 Firewall Policies

Firewall Policies determine how traffic flows through the enterprise.

Typical policy flow:

```text
Source
     │
     ▼
Destination
     │
     ▼
Service
     │
     ▼
Action
     │
     ▼
Allow / Deny
```

Each packet is evaluated against the configured security policies before being forwarded.

---

# 🌍 Network Address Translation (NAT)

FortiGate performs NAT to enable communication between private and public networks.

Common NAT Types:

- Source NAT (SNAT)
- Destination NAT (DNAT)
- Virtual IP (VIP)
- IP Pool

---

# 🔐 VPN Architecture

FortiGate provides secure encrypted communication between enterprise locations.

Supported VPN Technologies:

- Site-to-Site IPSec VPN
- Remote Access SSL VPN *(If Enabled)*

This enables users at branch offices to securely access centralized business resources.

---

# 🛡 Security Services

FortiGate can provide multiple integrated security services.

| Service | Purpose |
|----------|----------|
| Firewall Policy | Traffic Filtering |
| IPS | Intrusion Prevention |
| Web Filtering | URL Control |
| Application Control | Application Visibility |
| Antivirus | Malware Protection |
| SSL Inspection | Encrypted Traffic Inspection |
| DoS Protection | Network Attack Prevention |

> **Note:** The availability of these services depends on the licensed features enabled in the production environment.

---

# 📊 Logging & Monitoring

FortiGate continuously records network activity.

Typical log categories include:

- Traffic Logs
- Event Logs
- VPN Logs
- System Logs
- Administrator Logs
- Security Logs

These logs support troubleshooting, auditing, and incident response.

---

# 🌐 Traffic Flow

## Internet Access

```text
User
 │
 ▼
Core Switch
 │
 ▼
FortiGate
 │
 ▼
Internet
```

---

## Branch Communication

```text
Branch Office
      │
      ▼
IPSec VPN
      │
      ▼
FortiGate
      │
      ▼
Datacenter
```

---

## Publishing Internal Applications

```text
Internet
     │
     ▼
Public IP
     │
     ▼
VIP
     │
     ▼
Application Server
```

---

# 🔒 Security Layers

| Layer | Protection |
|--------|------------|
| Network | Firewall Policies |
| Internet | NAT |
| Branch Connectivity | IPSec VPN |
| Identity | Active Directory |
| Cloud Identity | Microsoft Entra ID |
| Endpoint | Microsoft Intune |
| Authentication | MFA |

---

# 📈 Business Benefits

- Centralized Security
- Secure Internet Access
- Protected Internal Network
- Secure Branch Connectivity
- Application Publishing
- Centralized Logging
- Improved Visibility
- Regulatory Compliance

---

# 📚 Related Documents

- 02-Network-Architecture.md
- 18-Branch-Connectivity.md
- 19-Security-Architecture.md

---

# 📌 Summary

The FortiGate Firewall serves as the enterprise security gateway, protecting the organization's infrastructure from external threats while enabling secure communication between users, branch offices, servers, and Microsoft Cloud services.

It combines firewall policies, routing, NAT, VPN, traffic inspection, and logging into a single security platform, making it one of the most critical components of the enterprise architecture.

> **Note:** This document explains the **architectural role** of FortiGate. Configuration details, firewall objects, policies, NAT, VPN, troubleshooting, and CLI commands will be covered in the **Low-Level Design (LLD)** and **Learning** sections.

---

📌 Next Document

```text
04-Active-Directory-Architecture.md
```
