# 🌍 Branch Connectivity

> **Document:** 07-Branch-Connectivity.md

![VPN](https://img.shields.io/badge/VPN-IPSec-blue?style=for-the-badge)
![Network](https://img.shields.io/badge/Network-Multi--Site-green?style=for-the-badge)
![Connectivity](https://img.shields.io/badge/Connectivity-Secure-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Branch Connectivity |
| Connectivity Type | Site-to-Site IPSec VPN |
| Environment | Production |
| Version | 1.0 |

---

# 📖 Introduction

This document describes how all enterprise locations are securely connected to the primary datacenter.

The organization follows a centralized network architecture where all branch offices communicate with the production datacenter through FortiGate Site-to-Site IPSec VPN tunnels. Users at every location access business applications, file services, authentication services, and Microsoft Cloud resources through this secure infrastructure.

---

# 🎯 Objectives

- Secure Inter-Site Communication
- Centralized Infrastructure Access
- Secure Branch Connectivity
- Encrypted WAN Communication
- High Availability
- Simplified Network Management

---

# 🌍 Enterprise Connectivity

```text
                                            🌐 Internet
                                                 │
                                                 │
═══════════════════════════════════════════════════════════════════════════════════════════════

                         🏢 Mumbai Head Office (Corporate Users)
                                         │
                                         │
                                   🔐 IPSec VPN
                                         │
                                         │
═══════════════════════════════════════════════════════════════════════════════════════════════

                           🏢 Yotta Datacenter (Primary Site)

═══════════════════════════════════════════════════════════════════════════════════════════════

                                  🛡 FortiGate Firewall
                                          │
                                   🔀 Core L3 Switch
                                          │
        ┌─────────────────────────────────┼─────────────────────────────────┐
        │                                 │                                 │
        ▼                                 ▼                                 ▼

 🖥 Active Directory              📁 File Server                 💼 Application Server

 🔐 Certificate Authority         🗄 Database Server             📊 NMS

 📦 WSUS                          💾 Backup                      🕒 NTP

                                          │
                                          ▼

                                  ☁ Microsoft Cloud

═══════════════════════════════════════════════════════════════════════════════════════════════

                          🔐 IPSec VPN Connections

             ┌──────────────────────┬──────────────────────┐
             │                      │                      │
             ▼                      ▼                      ▼

      🏢 Pune Branch        🏢 Nashik Branch       🏢 Nagpur Branch

```

---

# 🏢 Connected Locations

| Site | Connectivity | Primary Purpose |
|------|--------------|-----------------|
| Mumbai Head Office | LAN / VPN | Corporate Operations |
| Yotta Datacenter | Core Infrastructure | Production Services |
| Pune Branch | IPSec VPN | Branch Users |
| Nashik Branch | IPSec VPN | Branch Users |
| Nagpur Branch | IPSec VPN | Branch Users |

---

# 🔐 VPN Overview

The enterprise uses FortiGate Site-to-Site IPSec VPN tunnels to establish secure communication between all office locations.

### Benefits

- Encrypted Communication
- Secure Data Transfer
- Private Network Extension
- Centralized Access
- Secure Authentication
- Reliable Connectivity

---

# 🌐 Traffic Flow

## User Authentication

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
Active Directory
      │
      ▼
User Login Successful
```

---

## File Access

```text
Branch User
      │
      ▼
IPSec VPN
      │
      ▼
File Server
      │
      ▼
Shared Folder Access
```

---

## Business Application Access

```text
Branch User
      │
      ▼
IPSec VPN
      │
      ▼
Application Server
      │
      ▼
Database Server
```

---

## Microsoft 365 Access

```text
Branch User
      │
      ▼
Internet
      │
      ▼
Microsoft Entra ID
      │
      ▼
Microsoft 365
```

---

# 🔀 Routing Overview

| Source | Destination | Path |
|----------|------------|------|
| Mumbai HO | Datacenter | LAN |
| Pune | Datacenter | IPSec VPN |
| Nashik | Datacenter | IPSec VPN |
| Nagpur | Datacenter | IPSec VPN |
| Datacenter | Microsoft Cloud | Internet |
| Branch Users | Microsoft Cloud | Internet |

---

# 🔒 Security Controls

- FortiGate Next Generation Firewall
- Site-to-Site IPSec VPN
- Active Directory Authentication
- Microsoft Entra ID
- Multi-Factor Authentication
- Network Segmentation
- Encrypted WAN Traffic

---

# 📊 Connectivity Matrix

| Source | Destination | Service |
|---------|-------------|----------|
| Branch User | Active Directory | Authentication |
| Branch User | File Server | SMB |
| Branch User | Application Server | Business Application |
| Application Server | Database Server | Database Connectivity |
| Active Directory | Entra ID | Azure AD Connect |
| User | Microsoft 365 | HTTPS |
| User | Microsoft Teams | HTTPS |
| User | OneDrive | HTTPS |

---

# 🎯 Benefits

- Centralized Infrastructure
- Secure Branch Connectivity
- Encrypted Communication
- Simplified Administration
- Better Security
- Scalable Enterprise Network
- High Availability

---

# 📌 Summary

All branch offices securely connect to the primary Yotta Datacenter using FortiGate Site-to-Site IPSec VPN tunnels. The datacenter hosts all critical business services, while Microsoft Cloud services provide identity, collaboration, endpoint management, and multi-factor authentication.

This architecture ensures secure communication, centralized management, and consistent user access across all enterprise locations.

---

📌 Next Document

```text
08-Technology-Stack.md
```