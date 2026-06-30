# 🏛 Enterprise Architecture (High-Level Design)

> **Document:** 09-Architecture.md

![Architecture](https://img.shields.io/badge/Architecture-HLD-blue?style=for-the-badge)
![Infrastructure](https://img.shields.io/badge/Infrastructure-Hybrid-green?style=for-the-badge)
![Production](https://img.shields.io/badge/Environment-Production-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Enterprise Architecture |
| Architecture Type | High-Level Design (HLD) |
| Environment | Production |
| Version | 1.0 |

---

# 📖 Introduction

This document presents the complete High-Level Design (HLD) of the enterprise infrastructure.

It combines all major infrastructure components into a single architectural view, illustrating how users, branch offices, networking, security devices, servers, cloud services, and enterprise applications interact within the production environment.

This document acts as the primary architectural reference for infrastructure engineers, solution architects, auditors, and security reviewers.

---

# 🎯 Architecture Objectives

- Present the complete enterprise architecture
- Explain the relationship between all infrastructure components
- Illustrate hybrid cloud integration
- Show network segmentation and security layers
- Document centralized identity management
- Provide a reference architecture for future projects

---

# 🏗 Enterprise High-Level Architecture

```text
                                                  🌐 INTERNET
                                                       │
                                            ISP / Public IP Address
                                                       │
                                             🛡 FortiGate Firewall
                                                       │
══════════════════════════════════════════════════════════════════════════════════════════════════════════════

                                      🏢 YOTTA DATACENTER (PRIMARY SITE)

══════════════════════════════════════════════════════════════════════════════════════════════════════════════

                                         🔀 Core Layer-3 Switch
                                                       │
      ┌───────────────────────────────┬───────────────────────────────┬───────────────────────────────┐
      │                               │                               │
      ▼                               ▼                               ▼

 🖥 Infrastructure VLAN         💼 Application VLAN            👥 User VLAN

      │
      ▼

 ┌──────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │                                                                                                          │
 │  🖥 Active Directory            🔐 Certificate Authority             📦 WSUS Server                       │
 │                                                                                                          │
 │  💾 Backup Server              🕒 NTP Server                        📧 Email Protector                  │
 │                                                                                                          │
 │  📊 NMS Server                 📁 File Server                       💼 Application Servers              │
 │                                                                                                          │
 │                                  🗄 Database Servers                                               │
 └──────────────────────────────────────────────────────────────────────────────────────────────────────────┘

                                                       │
                                              🔄 Azure AD Connect
                                                       │
══════════════════════════════════════════════════════════════════════════════════════════════════════════════

                                             ☁ MICROSOFT CLOUD

══════════════════════════════════════════════════════════════════════════════════════════════════════════════

                                               🔷 Microsoft Entra ID
                                                        │
                    ┌───────────────────────────────────┼──────────────────────────────────┐
                    │                                   │                                  │
                    ▼                                   ▼                                  ▼

          📧 Microsoft 365                    💻 Microsoft Intune             📱 Microsoft Authenticator

                    │                                   │                                  │
      ┌─────────────┼──────────────┐          ┌─────────┼──────────┐                      │
      │             │              │          │         │          │                      │
📧 Outlook     💬 Teams      ☁ OneDrive   💻 Windows PCs   💼 Laptops             🔐 MFA / OTP

══════════════════════════════════════════════════════════════════════════════════════════════════════════════

                                          🌍 ENTERPRISE BRANCHES

══════════════════════════════════════════════════════════════════════════════════════════════════════════════

          🏢 Mumbai HO
                │
                ├──────────────🔐 IPSec VPN──────────────┐
                │                                        │
         🏢 Pune Branch                          🏢 Nashik Branch
                │                                        │
                └──────────────🔐 IPSec VPN──────────────┘
                                 │
                          🏢 Nagpur Branch

```

---

# 🏢 Infrastructure Layers

| Layer | Components |
|--------|------------|
| User Layer | Windows Laptops, Windows Desktops |
| Network Layer | Internet, ISP, FortiGate Firewall, Core L3 Switch |
| Server Layer | AD, CA, WSUS, Backup, File, NMS, Database, Application |
| Identity Layer | Active Directory, Azure AD Connect, Microsoft Entra ID |
| Cloud Layer | Microsoft 365, Intune, Authenticator |
| Security Layer | Firewall, IPSec VPN, MFA, Defender, BitLocker |

---

# 🔄 Identity Flow

```text
User
   │
   ▼
Active Directory
   │
   ▼
Azure AD Connect
   │
   ▼
Microsoft Entra ID
   │
   ├── Microsoft 365
   ├── Microsoft Intune
   └── Microsoft Authenticator
```

---

# 🌐 Network Flow

```text
User Device
      │
      ▼
Access Switch
      │
      ▼
Core Layer-3 Switch
      │
      ▼
FortiGate Firewall
      │
      ├── Internet
      ├── Branch VPN
      └── Datacenter Servers
```

---

# 🔐 Security Architecture

| Layer | Security Control |
|---------|------------------|
| Perimeter | FortiGate Firewall |
| Branch Connectivity | IPSec VPN |
| Identity | Active Directory |
| Cloud Identity | Microsoft Entra ID |
| MFA | Microsoft Authenticator |
| Endpoint | Microsoft Intune |
| Disk Encryption | BitLocker |
| Endpoint Protection | Microsoft Defender |

---

# ☁ Hybrid Cloud Integration

| On-Premises | Microsoft Cloud |
|--------------|----------------|
| Active Directory | Microsoft Entra ID |
| Users | Microsoft 365 |
| Windows Devices | Microsoft Intune |
| Domain Authentication | Microsoft Authenticator |
| Azure AD Connect | Identity Synchronization |

---

# 🎯 Design Principles

- Hybrid Infrastructure
- Centralized Identity Management
- Defense-in-Depth Security
- Secure Remote Connectivity
- Centralized Management
- Enterprise Scalability
- High Availability
- Standardized Infrastructure

---

# 📈 Business Benefits

- Centralized Administration
- Secure Authentication
- Secure Branch Connectivity
- Hybrid Cloud Integration
- Simplified Device Management
- Improved Collaboration
- Better Security Posture
- Easier Infrastructure Management

---

# 📌 Architecture Summary

The enterprise follows a **Hybrid Infrastructure Model**, where all critical business applications and infrastructure services are hosted within the **Yotta Datacenter**, while Microsoft Cloud services provide identity synchronization, collaboration, endpoint management, and multi-factor authentication.

The FortiGate Firewall secures all inbound and outbound traffic, Site-to-Site IPSec VPN tunnels connect every branch office, Active Directory remains the primary identity source, and Microsoft Entra ID extends authentication securely into the cloud.

This architecture provides a scalable, secure, and centrally managed enterprise environment suitable for modern business operations.

---

📌 Next Document

```text
10-Scope.md
```
