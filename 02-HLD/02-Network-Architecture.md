# 🌐 Network Architecture

> **Document:** `02-Network-Architecture.md`

![Network](https://img.shields.io/badge/Architecture-Network-blue?style=for-the-badge)
![Infrastructure](https://img.shields.io/badge/Enterprise-Hybrid-green?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-FortiGate-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Network Architecture |
| Document Type | High-Level Design (HLD) |
| Environment | Production |
| Version | 1.0 |

---

# 📖 Introduction

The Enterprise Network is the backbone of the entire IT infrastructure.

Every user, server, branch office, cloud service, and business application communicates through the enterprise network.

A properly designed network provides:

- Secure Connectivity
- High Availability
- Scalability
- Performance
- Centralized Management

This document explains the enterprise network from an architectural perspective.

---

# 🎯 Network Objectives

- Secure Internet Access
- Connect all Branch Offices
- Protect Internal Servers
- Provide High Availability
- Separate Network Traffic using VLANs
- Enable Hybrid Cloud Connectivity
- Simplify Network Management

---

# 🏗 Network Components

| Layer | Components |
|--------|------------|
| Internet | ISP, Public IP |
| Security | FortiGate Firewall |
| Core Network | Layer-3 Switch |
| Access Layer | Layer-2 Switches |
| Infrastructure | Servers |
| Users | Laptops & Desktops |
| Cloud | Microsoft Cloud |

---

# 🌐 Enterprise Network Layers

```text
Users
   │
   ▼
Access Layer
   │
   ▼
Distribution / Core Layer
   │
   ▼
Security Layer
   │
   ▼
Datacenter
   │
   ▼
Microsoft Cloud
```

---

# 🌍 Network Zones

| Zone | Purpose |
|------|---------|
| Internet | Public Connectivity |
| WAN | ISP Connection |
| LAN | Internal Users |
| Server Network | Infrastructure Servers |
| Management Network | Administrative Access |
| VPN Network | Branch Connectivity |
| Cloud Network | Microsoft Services |

---

# 🔀 Network Devices

| Device | Purpose |
|---------|----------|
| ISP Router | Internet Connectivity |
| FortiGate Firewall | Network Security |
| Layer-3 Switch | Inter-VLAN Routing |
| Layer-2 Switch | User Connectivity |
| Wireless Access Point | Wi-Fi Access |
| Servers | Business Services |

---

# 🌐 VLAN Segmentation

The enterprise network is logically divided into multiple VLANs.

Example:

| VLAN | Purpose |
|------|---------|
| User VLAN | Employee Devices |
| Server VLAN | Production Servers |
| Management VLAN | Network Administration |
| Printer VLAN | Network Printers |
| Guest VLAN | Guest Internet Access |

> **Note:** Actual VLAN IDs and IP subnets are documented in the Low-Level Design (LLD).

---

# 🔄 Routing Architecture

The Core Layer-3 Switch performs:

- Inter-VLAN Routing
- Internal Traffic Forwarding
- Default Gateway Services
- Communication Between Network Segments

The FortiGate Firewall performs:

- Internet Routing
- VPN Routing
- Security Inspection
- NAT

---

# 🔐 Security Architecture

Network security is implemented using multiple layers.

| Layer | Security Control |
|---------|------------------|
| Internet Edge | FortiGate Firewall |
| Internal Network | VLAN Segmentation |
| Remote Access | IPSec VPN |
| Identity | Active Directory |
| Cloud Identity | Microsoft Entra ID |
| Endpoint | Microsoft Intune |
| Authentication | Microsoft Authenticator |

---

# 🌍 Branch Connectivity

Remote offices securely connect to the primary datacenter using FortiGate Site-to-Site IPSec VPN tunnels.

Each branch can securely access:

- Active Directory
- File Server
- Application Server
- Database Server
- Microsoft Cloud Services

---

# ☁ Hybrid Connectivity

The enterprise follows a Hybrid Network Architecture.

```text
On-Premises Network
          │
          ▼
Azure AD Connect
          │
          ▼
Microsoft Entra ID
          │
          ▼
Microsoft Cloud Services
```

---

# 📈 Traffic Flow

### Internal User

```text
User PC
    │
    ▼
Access Switch
    │
    ▼
Layer-3 Switch
    │
    ▼
Server
```

---

### Internet Access

```text
User PC
    │
    ▼
Access Switch
    │
    ▼
Layer-3 Switch
    │
    ▼
FortiGate Firewall
    │
    ▼
Internet
```

---

### Branch Access

```text
Branch User
     │
     ▼
FortiGate VPN
     │
     ▼
Datacenter
     │
     ▼
Business Application
```

---

### Microsoft Cloud Access

```text
User
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

# 📊 Communication Matrix

| Source | Destination | Purpose |
|----------|------------|----------|
| User | Active Directory | Authentication |
| User | File Server | File Access |
| User | Application Server | Business Application |
| Application Server | Database Server | Data Access |
| Active Directory | Entra ID | Identity Sync |
| User | Microsoft 365 | Collaboration |
| Branch Office | Datacenter | Secure VPN Communication |

---

# 🎯 Network Design Principles

- Layered Network Architecture
- Centralized Security
- VLAN Segmentation
- Secure Remote Connectivity
- Hybrid Cloud Integration
- High Availability
- Scalability
- Simplified Troubleshooting

---

# 📈 Business Benefits

- Secure Enterprise Communication
- Centralized Infrastructure
- Faster Network Management
- Better Security
- Reduced Broadcast Domains
- Simplified Expansion
- Reliable Branch Connectivity

---

# 📚 Related Documents

- 03-FortiGate-Architecture.md
- 04-Active-Directory-Architecture.md
- 18-Branch-Connectivity.md
- 19-Security-Architecture.md

---

# 📌 Summary

The Enterprise Network Architecture provides the communication framework for the entire organization. By combining FortiGate security, Layer-3 routing, VLAN segmentation, IPSec VPN connectivity, and Hybrid Microsoft Cloud integration, the network delivers secure, scalable, and highly available connectivity for users, servers, branch offices, and cloud services.

---

📌 Next Document

```text
03-FortiGate-Architecture.md
``` 