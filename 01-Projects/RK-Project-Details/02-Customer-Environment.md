# 🏢 Customer Environment

> **Document:** 02-Customer-Environment.md

![Customer](https://img.shields.io/badge/Customer-Enterprise-blue?style=for-the-badge)
![Infrastructure](https://img.shields.io/badge/Infrastructure-Hybrid-green?style=for-the-badge)
![Environment](https://img.shields.io/badge/Environment-Production-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Customer Environment |
| Environment | Production |
| Infrastructure Type | Hybrid Infrastructure |
| Version | 1.0 |

---

# 📖 Introduction

This document provides an overview of the customer's production environment.

The organization operates a hybrid enterprise infrastructure where core business services are hosted within an on-premises datacenter while identity, collaboration, and endpoint management services are integrated with Microsoft Cloud.

The infrastructure is designed to provide high availability, centralized identity management, secure branch connectivity, and enterprise-grade security.

---

# 🎯 Business Objectives

The primary objectives of the customer environment are:

- Centralized Identity Management
- Secure Network Connectivity
- High Availability of Business Services
- Centralized User Management
- Secure Remote Authentication
- Standardized Endpoint Management
- Enterprise Security Compliance

---

# 🏢 Site Information

The organization consists of the following locations:

| Site | Purpose |
|------|---------|
| Head Office (Mumbai) | Corporate Office |
| Datacenter (Yotta) | Primary Production Infrastructure |
| Branch Office | Pune |
| Branch Office | Nashik |
| Branch Office | Nagpur |

---

# 🌐 Infrastructure Model

The customer operates a Hybrid Infrastructure consisting of:

## On-Premises Infrastructure

- Enterprise Network
- FortiGate Firewall
- Active Directory
- Certificate Authority
- WSUS
- Backup Server
- NTP Server
- Email Protector
- Network Monitoring Server
- File Server
- Application Servers
- Database Servers

---

## Microsoft Cloud Services

- Microsoft Entra ID
- Microsoft 365
- Microsoft Intune
- Microsoft Authenticator

---

# 👥 User Environment

Users access enterprise resources from:

- Windows Desktop
- Windows Laptop
- Corporate Mobile Devices

Users authenticate using Active Directory credentials while Microsoft Entra ID provides cloud identity synchronization.

Multi-Factor Authentication (MFA) is implemented using Microsoft Authenticator.

---

# 🌍 Branch Connectivity

All branch offices are securely connected to the primary datacenter using FortiGate Site-to-Site VPN tunnels.

Business applications are accessed through the datacenter while Microsoft Cloud services are accessed securely over the Internet.

---

# 🔐 Identity Management

Identity management follows a hybrid model.

```text
Active Directory
       │
Azure AD Connect
       │
       ▼
Microsoft Entra ID
```

Active Directory remains the primary identity source, while Azure AD Connect synchronizes users and groups with Microsoft Entra ID for Microsoft Cloud services.

---

# ☁️ Cloud Services Usage

| Service | Purpose |
|----------|---------|
| Microsoft Entra ID | Cloud Identity Management |
| Microsoft 365 | Email & Collaboration |
| Microsoft Intune | Windows Laptop/Desktop Management |
| Microsoft Authenticator | Multi-Factor Authentication |

---

# 🖥 On-Premises Services

| Service | Purpose |
|----------|---------|
| Active Directory | Identity Management |
| Certificate Authority | PKI & Certificate Services |
| WSUS | Windows Updates |
| Backup Server | Backup & Recovery |
| NTP Server | Time Synchronization |
| Email Protector | Email Security |
| NMS | Infrastructure Monitoring |
| File Server | File Sharing |
| Application Server | Business Applications |
| Database Server | Database Services |

---

# 📈 High-Level Environment

```text
Users
   │
   ▼
Branch Offices
   │
   ▼
Internet
   │
   ▼
FortiGate Firewall
   │
   ▼
Yotta Datacenter
   │
   ├── Active Directory
   ├── Certificate Authority
   ├── WSUS
   ├── Backup
   ├── NTP
   ├── Email Protector
   ├── NMS
   ├── File Server
   ├── Application Server
   └── Database Server
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

# 🎯 Summary

The customer environment consists of a secure hybrid infrastructure where business-critical workloads remain on-premises while Microsoft Cloud services provide identity, collaboration, endpoint management, and multi-factor authentication.

This architecture enables centralized administration, secure access, and seamless integration between on-premises infrastructure and Microsoft Cloud.

---

📌 Next Document

Continue with:

```text
03-Site-Information.md
```
