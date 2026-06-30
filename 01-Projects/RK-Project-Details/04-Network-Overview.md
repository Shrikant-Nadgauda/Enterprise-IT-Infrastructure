# 🌐 Network Overview

> **Document:** 04-Network-Overview.md

![Network](https://img.shields.io/badge/Network-Enterprise-blue?style=for-the-badge)
![Firewall](https://img.shields.io/badge/Security-FortiGate-red?style=for-the-badge)
![Topology](https://img.shields.io/badge/Topology-Hybrid-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Network Overview |
| Infrastructure | Hybrid Enterprise |
| Environment | Production |
| Version | 1.0 |

---

# 📖 Introduction

This document provides a high-level overview of the enterprise network architecture.

The environment consists of a centralized on-premises datacenter protected by a FortiGate Firewall. Multiple branch offices connect securely to the datacenter through IPSec VPN tunnels, while Microsoft Cloud services are integrated using Microsoft Entra ID synchronization.

The objective is to provide secure, highly available, and centralized access to enterprise resources.

---

# 🎯 Network Objectives

- Secure Internet Access
- Centralized Security
- Branch Connectivity
- Hybrid Cloud Integration
- Secure User Authentication
- High Availability
- Centralized Network Management

---

# 🌐 Enterprise Network Architecture

```text
                                             🌐 Internet
                                                  │
                                           Public IP Address
                                                  │
                                         🛡 FortiGate Firewall
                                                  │
══════════════════════════════════════════════════════════════════════════════════════

                                    🏢 Yotta Datacenter (Core Network)

══════════════════════════════════════════════════════════════════════════════════════

                                    🔀 Core Layer 3 Switch
                                                  │
             ┌───────────────────────┬────────────┼───────────────┬───────────────────────┐
             │                       │            │               │
             ▼                       ▼            ▼               ▼

      🖥 Server VLAN          👨 User VLAN    🖨 Printer VLAN   📹 Management VLAN
             │
             ▼

     🖥 Active Directory
     🔐 Certificate Authority
     📦 WSUS
     💾 Backup
     🕒 NTP
     📧 Email Protector
     📊 NMS
     📁 File Server
     💼 Application Server
     🗄 Database Server

             │
             ▼
      🔄 Azure AD Connect
             │
══════════════════════════════════════════════════════════════════════════════════════

                                         ☁ Microsoft Cloud

══════════════════════════════════════════════════════════════════════════════════════

                                   🔷 Microsoft Entra ID
                                              │
               ┌──────────────────────────────┼─────────────────────────────┐
               ▼                              ▼                             ▼

        📧 Microsoft 365              💻 Microsoft Intune         📱 Authenticator

══════════════════════════════════════════════════════════════════════════════════════

                                    🌍 Branch Connectivity

══════════════════════════════════════════════════════════════════════════════════════

🏢 Mumbai HO ─────┐
                  │
🏢 Pune ──────────┼──── 🔐 IPSec VPN ─────🛡 FortiGate Firewall
                  │
🏢 Nashik ────────┤
                  │
🏢 Nagpur ────────┘
```

---

# 🏗 Network Components

| Component | Purpose |
|-----------|---------|
| Internet | External Connectivity |
| ISP | Public Internet Provider |
| Public IP | Internet Facing Address |
| FortiGate Firewall | Perimeter Security |
| Core Layer 3 Switch | Internal Routing |
| VLANs | Network Segmentation |
| Servers | Enterprise Services |
| Azure AD Connect | Identity Synchronization |
| Microsoft Cloud | SaaS Services |
| IPSec VPN | Branch Connectivity |

---

# 🌍 Network Zones

| Zone | Description |
|------|-------------|
| Internet | Public Network |
| WAN | ISP Connection |
| DMZ *(Optional)* | Public Facing Services |
| Server Network | Infrastructure Servers |
| User Network | Employee Devices |
| Management Network | Administrative Access |
| Microsoft Cloud | SaaS Environment |

---

# 🔀 Traffic Flow

## User Authentication

```text
User
 │
 ▼
Active Directory
 │
 ▼
Domain Authentication
```

---

## Microsoft 365 Login

```text
User
 │
 ▼
Microsoft Entra ID
 │
 ▼
Microsoft 365
```

---

## Branch User Access

```text
Branch User
 │
 ▼
IPSec VPN
 │
 ▼
FortiGate Firewall
 │
 ▼
Datacenter
 │
 ▼
Application Server
```

---

## Endpoint Management

```text
Windows Laptop
 │
 ▼
Microsoft Intune
 │
 ▼
Policy Deployment
```

---

# 🔐 Network Security Controls

- FortiGate Next Generation Firewall
- Site-to-Site IPSec VPN
- Active Directory Authentication
- Microsoft Entra ID
- Multi-Factor Authentication
- Microsoft Intune
- Windows Defender
- BitLocker Encryption

---

# 🌐 Network Services

| Service | Location |
|----------|----------|
| DNS | Active Directory |
| DHCP | On-Premises |
| NTP | Datacenter |
| Certificate Services | Certificate Authority |
| User Authentication | Active Directory |
| Cloud Authentication | Microsoft Entra ID |
| Endpoint Management | Microsoft Intune |
| Email Services | Microsoft 365 |

---

# 📊 Network Communication Matrix

| Source | Destination | Protocol |
|---------|-------------|----------|
| User PC | Active Directory | LDAP / Kerberos |
| User PC | File Server | SMB |
| Branch Office | Datacenter | IPSec VPN |
| Active Directory | Entra ID | Azure AD Connect |
| User | Microsoft 365 | HTTPS |
| Intune | Windows Devices | HTTPS |
| Authenticator | Entra ID | MFA |

---

# 🎯 Key Design Principles

- Centralized Identity Management
- Layered Network Security
- Secure Remote Connectivity
- Hybrid Cloud Integration
- Segregated Network Architecture
- Centralized Monitoring
- High Availability
- Enterprise Scalability

---

# 📌 Summary

The enterprise network is built around a centralized FortiGate Firewall and Yotta Datacenter, providing secure connectivity for branch offices, enterprise servers, and Microsoft Cloud services.

Identity is managed through Active Directory and synchronized with Microsoft Entra ID, while Microsoft 365, Intune, and Authenticator extend cloud capabilities for collaboration, endpoint management, and secure authentication.

---

📌 Next Document

```text
05-Server-Inventory.md
```
---