# 🏢 Site Information

> **Document:** 03-Site-Information.md

![Infrastructure](https://img.shields.io/badge/Infrastructure-Hybrid-blue?style=for-the-badge)
![Sites](https://img.shields.io/badge/Sites-Multi--Location-green?style=for-the-badge)
![Environment](https://img.shields.io/badge/Environment-Production-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Site Information |
| Environment | Production |
| Infrastructure Type | Hybrid Infrastructure |
| Version | 1.0 |

---

# 📖 Introduction

This document describes the physical locations that form the enterprise infrastructure.

The organization operates multiple office locations connected to a centralized production datacenter. Identity management, application hosting, and security services are centrally managed while users access resources securely from different branch offices.

---

# 🌍 Enterprise Site Overview

```text
                                        🌐 Internet
                                             │
                                      🛡 FortiGate Firewall
                                             │
══════════════════════════════════════════════════════════════════════════════════════

                         🏢 Yotta Datacenter (Primary Production)

══════════════════════════════════════════════════════════════════════════════════════

     🖥 Active Directory        🔐 CA        💾 Backup        📦 WSUS
     📁 File Server            📊 NMS       📧 Email         🗄 Database
     💼 Application Servers     🕒 NTP

══════════════════════════════════════════════════════════════════════════════════════

                               🏢 Mumbai Head Office
                                        │
────────────────────────────────────────┼───────────────────────────────────────────
                                        │
                          🔐 Site-to-Site IPSec VPN
                                        │
             ┌──────────────────────────┼──────────────────────────┐
             │                          │                          │
             ▼                          ▼                          ▼

      🏢 Pune Branch             🏢 Nashik Branch          🏢 Nagpur Branch

```

---

# 🏢 Site Details

## 🏢 Head Office

### Purpose

The Head Office is the primary business location where users access enterprise applications and IT services.

### Responsibilities

- Corporate Operations
- User Administration
- Business Applications
- Management Activities
- Secure Access to Datacenter Resources

---

## 🏢 Primary Datacenter

### Location

Yotta Datacenter

### Purpose

The datacenter hosts all critical enterprise infrastructure and business applications.

### Hosted Services

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

## 🏢 Disaster Recovery Site

### Status

Not Implemented *(Current Environment)*

> **Note:** If a Disaster Recovery (DR) site is deployed in the future, critical workloads and backup infrastructure should be replicated to ensure business continuity during a datacenter outage.

---

## 🏢 Branch Offices

The organization operates multiple branch offices connected securely to the primary datacenter.

| Branch | Connectivity | Purpose |
|---------|--------------|----------|
| Mumbai Head Office | LAN | Corporate Users |
| Pune | IPSec VPN | Branch Users |
| Nashik | IPSec VPN | Branch Users |
| Nagpur | IPSec VPN | Branch Users |

---

# 🌐 Connectivity Overview

| Source | Destination | Connection |
|---------|-------------|------------|
| Head Office | Datacenter | Secure Enterprise Network |
| Pune Branch | Datacenter | IPSec VPN |
| Nashik Branch | Datacenter | IPSec VPN |
| Nagpur Branch | Datacenter | IPSec VPN |
| Datacenter | Microsoft Cloud | Secure Internet Connectivity |

---

# 👥 User Distribution

| Location | Users | Authentication |
|----------|-------|----------------|
| Mumbai Head Office | Domain Users | Active Directory |
| Pune Branch | Domain Users | Active Directory |
| Nashik Branch | Domain Users | Active Directory |
| Nagpur Branch | Domain Users | Active Directory |

---

# 🔐 Centralized Services

The following enterprise services are centrally managed from the primary datacenter.

- Active Directory
- DNS
- Certificate Authority
- Windows Updates
- File Sharing
- Database Services
- Application Hosting
- Backup Infrastructure
- Network Monitoring
- Time Synchronization

---

# ☁️ Microsoft Cloud Integration

The datacenter is integrated with Microsoft Cloud services.

```text
🖥 Active Directory
        │
        ▼
🔄 Azure AD Connect
        │
        ▼
🔷 Microsoft Entra ID
        │
 ┌──────┼──────────────┐
 │      │              │
 ▼      ▼              ▼
📧 M365 💻 Intune   📱 Authenticator
```

---

# 🎯 Site Roles Summary

| Site | Primary Role |
|------|--------------|
| Mumbai Head Office | Corporate Operations |
| Yotta Datacenter | Production Infrastructure |
| Pune Branch | Branch Office |
| Nashik Branch | Branch Office |
| Nagpur Branch | Branch Office |
| Microsoft Cloud | Identity, Collaboration & Endpoint Management |

---

# 📌 Key Design Characteristics

- Hybrid Infrastructure
- Centralized Identity Management
- On-Premises Business Applications
- Microsoft Cloud Integration
- Secure Branch Connectivity
- Enterprise Security Architecture
- Centralized Infrastructure Management

---

# 🎯 Summary

The enterprise environment consists of a centralized production datacenter, a corporate head office, and multiple branch offices connected through secure VPN tunnels.

Core infrastructure services remain on-premises, while Microsoft Cloud services extend identity, collaboration, endpoint management, and multi-factor authentication capabilities.

---

📌 Next Document

```text
04-Network-Overview.md
```
---