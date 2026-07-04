# 🛣 FortiGate Routing

> **Document:** `04-Routing.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Routing-red?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-Routing-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Routing |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Routing |

---

# 📖 Purpose

Routing is one of the core functions of the FortiGate firewall. After a packet enters an interface and passes the initial validation process, the firewall must determine where the packet should be forwarded.

The routing engine selects the most appropriate path based on the routing table, destination network, administrative distance, priority, and routing policies. A well-designed routing architecture ensures reliable connectivity between internal networks, branch offices, datacenters, cloud services, and the Internet.

---

# 🎯 Design Objectives

- Provide Network Connectivity
- Enable Internet Access
- Connect Branch Offices
- Support Multiple WAN Links
- Optimize Traffic Paths
- Improve Availability
- Support Hybrid Cloud Connectivity
- Simplify Network Management

---

# 🏗 Enterprise Routing Architecture

```text
                        🌐 Internet
                             │
                      ISP Gateway
                             │
                     Default Route
                             │
                    ┌────────────────┐
                    │   FortiGate    │
                    └────────────────┘
              │            │             │
              ▼            ▼             ▼

         LAN Routes   VPN Routes    Static Routes

              │            │             │
              ▼            ▼             ▼

      Internal LAN   Branch Offices   Datacenter

                             │
                             ▼

                    Microsoft Cloud
```

---

# 📌 Routing Fundamentals

Routing determines the path a packet takes from its source to its destination.

The routing process includes:

- Receiving the packet
- Reading the destination IP
- Searching the routing table
- Selecting the best route
- Forwarding the packet to the next hop

---

# 🌐 Routing Table

The routing table contains all known network paths.

Typical route sources include:

| Route Type | Description |
|------------|-------------|
| Connected | Directly connected networks |
| Static | Manually configured routes |
| Dynamic | Learned through routing protocols |
| Default | Route to unknown destinations |
| Blackhole | Discard unwanted traffic |

---

# 🚪 Default Route

The default route is used when no specific route exists for a destination.

Example:

```text
0.0.0.0/0

↓

ISP Gateway

↓

Internet
```

Every enterprise firewall typically has at least one default route for Internet-bound traffic.

---

# 🧭 Static Routing

Static routes are manually configured and provide deterministic routing behavior.

Common use cases:

- Internal Networks
- Branch Offices
- Datacenters
- VPN Tunnels
- Management Networks
- Backup Links

Advantages:

- Simple Configuration
- Predictable Routing
- Low Resource Usage

---

# 🔄 Dynamic Routing

Dynamic routing automatically exchanges routing information between network devices.

Supported routing protocols include:

- OSPF
- BGP
- RIP
- IS-IS (platform dependent)

Benefits:

- Automatic Route Learning
- Faster Network Convergence
- Reduced Administrative Effort
- Improved Scalability

---

# 📊 Route Lookup Process

```text
Incoming Packet

        │

        ▼

Destination IP

        │

        ▼

Routing Table Lookup

        │

        ▼

Best Matching Route

        │

        ▼

Next-Hop Selection

        │

        ▼

Packet Forwarded
```

---

# ⚖ Administrative Distance

When multiple routes exist to the same destination, FortiGate selects the route with the lowest Administrative Distance (AD).

Priority Order:

1. Connected Route
2. Static Route
3. Dynamic Route
4. Default Route

---

# 🚦 Policy-Based Routing (PBR)

Policy-Based Routing allows traffic to be forwarded based on policies rather than only the routing table.

Routing decisions may consider:

- Source Address
- Destination Address
- Application
- Service
- Incoming Interface
- User Identity

Common uses:

- ISP Load Balancing
- Dedicated Application Routing
- Cloud Traffic Optimization

---

# ⚡ Equal Cost Multi-Path (ECMP)

ECMP allows multiple routes with equal cost to be used simultaneously.

Benefits:

- Load Sharing
- Increased Bandwidth
- Link Redundancy
- Higher Availability

---

# 🌍 SD-WAN Overview

FortiGate SD-WAN intelligently selects the best WAN connection based on link health.

Typical metrics include:

- Latency
- Packet Loss
- Jitter
- Bandwidth
- Link Availability

Benefits:

- Automatic Failover
- Application-Aware Routing
- Improved User Experience
- WAN Optimization

---

# 🔐 Routing Best Practices

- Use Static Routes where possible.
- Implement Dynamic Routing for large environments.
- Maintain accurate routing documentation.
- Configure redundant default routes.
- Monitor route changes.
- Use route summarization where appropriate.
- Avoid asymmetric routing.
- Test failover scenarios regularly.

---

# 🏢 Enterprise Deployment Example

```text
WAN1
│
├── Primary ISP

WAN2
│
├── Secondary ISP

LAN
│
├── User VLANs

VPN
│
├── Mumbai Branch

VPN
│
├── Pune Branch

VPN
│
├── Nashik Branch

VPN
│
├── Nagpur Branch

Cloud
│
└── Microsoft Services
```

---

# 📈 Design Considerations

Before implementing routing, consider:

- Network Topology
- IP Addressing Scheme
- Branch Connectivity
- Internet Redundancy
- VPN Architecture
- Cloud Integration
- High Availability
- Future Expansion

---

# 📚 Related Documents

- 01-FortiGate-LLD.md
- 02-Interfaces.md
- 03-Security-Zones.md
- 05-Firewall-Policies.md
- 06-NAT.md
- 09-VPN.md
- 11-IPSec-VPN.md

---

# 📌 Summary

Routing is responsible for forwarding traffic between networks and ensuring that packets reach their intended destination efficiently. A well-designed routing architecture improves performance, supports redundancy, enables secure branch connectivity, and integrates seamlessly with Internet and Microsoft cloud services.

Enterprise deployments typically combine static routes, dynamic routing protocols, policy-based routing, ECMP, and SD-WAN to build a resilient, scalable, and highly available network infrastructure.

> **Note:** This document focuses on routing architecture and design. Static route configuration, OSPF, BGP, SD-WAN configuration, CLI commands, routing diagnostics, packet flow analysis, and troubleshooting procedures will be covered in the **Infrastructure Deep Dive** section.

---
📌 Next Document

```text
05-Firewall-Policies.md
```

The next document explains FortiGate Firewall Policies, including policy evaluation order, source and destination objects, services, security profiles, policy matching, logging, implicit deny rules, and enterprise best practices for designing secure and scalable access control.
