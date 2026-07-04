# 🌐 FortiGate Interfaces

> **Document:** `02-Interfaces.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Interfaces-red?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-Low%20Level%20Design-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Interfaces |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Network Interfaces |

---

# 📖 Purpose

Interfaces are the foundation of every FortiGate deployment. Every packet entering or leaving the firewall always passes through an interface.

A properly designed interface architecture improves security, simplifies management, supports VLAN segmentation, enables routing, and provides a scalable network design.

This document explains every interface type available in FortiGate and how they are used in enterprise production environments.

---

# 🎯 Design Objectives

- Connect internal and external networks
- Separate network segments
- Enable VLAN communication
- Support VPN connectivity
- Provide redundancy
- Improve network performance
- Simplify administration
- Enhance security

---

# 🏗 Interface Architecture

```text
                    Internet
                        │
                        ▼
                 WAN1 / WAN2
                        │
            ┌─────────────────────┐
            │     FortiGate       │
            └─────────────────────┘
          │      │      │      │
          ▼      ▼      ▼      ▼

        LAN     DMZ    MGMT   VPN

          │
          ▼

     Core Layer-3 Switch

          │

   ┌──────┼───────────┐
   ▼      ▼           ▼

Users   Servers      Wi-Fi
```

---

# 🌐 Types of Interfaces

| Interface | Purpose |
|-----------|---------|
| Physical Interface | Connects directly to network devices |
| Logical Interface | Virtual interface for special functions |
| VLAN Interface | Network segmentation using VLAN IDs |
| Loopback Interface | Stable interface for routing and management |
| Aggregate Interface | Combines multiple links for redundancy and bandwidth |
| Software Switch | Groups multiple interfaces into one logical LAN |
| Tunnel Interface | Used by IPSec VPN and GRE tunnels |
| SSL VPN Interface | Virtual interface for remote users |
| Wireless Interface | Connects wireless networks (supported models) |

---

# 🔌 Physical Interfaces

Physical interfaces represent the actual Ethernet ports on the FortiGate appliance.

Examples:

```text
port1
port2
port3
port4
wan1
wan2
mgmt
ha
```

Typical enterprise usage:

| Interface | Connected Device |
|-----------|------------------|
| WAN1 | ISP Router |
| WAN2 | Secondary ISP |
| LAN | Core Switch |
| DMZ | DMZ Switch |
| MGMT | Management Network |
| HA | HA Heartbeat Link |

---

# 🏢 Logical Interfaces

Logical interfaces are software-defined interfaces created on top of physical interfaces.

Examples:

- VLAN Interface
- IPSec Tunnel
- SSL VPN
- Loopback
- Aggregate Interface

These interfaces provide flexibility without requiring additional physical ports.

---

# 🏷 VLAN Interfaces

VLAN interfaces allow multiple logical networks to share a single physical interface.

Example:

```text
port2

│

├── VLAN 10 → Users

├── VLAN 20 → Servers

├── VLAN 30 → Voice

├── VLAN 40 → Wi-Fi

└── VLAN 50 → Management
```

Benefits:

- Network Segmentation
- Reduced Cabling
- Improved Security
- Easier Expansion

---

# 🔄 Aggregate Interfaces

Aggregate interfaces combine multiple physical links into a single logical interface.

Example:

```text
port5

+

port6

↓

Aggregate Interface

↓

Core Switch
```

Benefits:

- Increased Bandwidth
- Link Redundancy
- Higher Availability

---

# 🔁 Loopback Interface

A loopback interface is a virtual interface that always remains active unless administratively disabled.

Common uses:

- Router ID
- VPN Endpoint
- Monitoring
- Management
- Routing Protocols

---

# 🔐 Tunnel Interfaces

Tunnel interfaces are automatically created for VPN connectivity.

Examples:

```text
IPSec Tunnel

SSL VPN Tunnel

GRE Tunnel
```

These interfaces carry encrypted traffic between sites or remote users.

---

# 🌍 Interface Roles

FortiGate allows assigning interface roles to simplify administration.

Typical roles include:

| Role | Purpose |
|------|---------|
| WAN | Internet Connectivity |
| LAN | Internal Network |
| DMZ | Public Services |
| Undefined | Custom Configuration |

---

# 🌐 IP Address Assignment

Interfaces can be configured with:

- Static IP Address
- DHCP Client
- PPPoE
- Secondary IP Addresses
- IPv6 Addressing

Example:

```text
WAN1

↓

203.0.113.10/29

↓

Default Gateway

↓

Internet
```

---

# 🛡 Security Best Practices

- Disable unused interfaces.
- Use dedicated management interfaces.
- Separate users and servers using VLANs.
- Restrict administrative access.
- Use interface descriptions.
- Enable only required services.
- Protect management interfaces with ACLs.
- Monitor interface utilization.

---

# ⚙ Enterprise Deployment Example

```text
WAN1
│
├── Internet

WAN2
│
├── Backup ISP

LAN
│
├── Core Switch

DMZ
│
├── Public Servers

MGMT
│
├── Network Administration

VPN
│
├── Branch Offices
```

---

# 📊 Design Considerations

During interface planning:

- Number of WAN links
- Number of LAN segments
- VLAN requirements
- Future expansion
- Redundancy
- High Availability
- Security zones
- Management network

---

# 📚 Related Documents

- 01-FortiGate-LLD.md
- 03-Security-Zones.md
- 04-Routing.md
- 05-Firewall-Policies.md
- 09-VPN.md
- 12-High-Availability.md

---

# 📌 Summary

Interfaces form the physical and logical foundation of the FortiGate firewall. Every network connection, VLAN, VPN, and management service depends on correctly designed interfaces. A well-planned interface architecture improves scalability, security, performance, and simplifies long-term administration in enterprise environments.

> **Note:** This document focuses on interface architecture and design. Actual interface configuration, CLI commands, GUI configuration, troubleshooting, and production deployment examples will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
03-Security-Zones.md
```

The next document explains FortiGate Security Zones, including zone-based firewall design, interface grouping, policy simplification, traffic control, segmentation strategies, and enterprise best practices for scalable network security.
