# 🌐 FortiGate Network Address Translation (NAT)

> **Document:** `06-NAT.md`

![FortiGate](https://img.shields.io/badge/FortiGate-NAT-red?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-Address%20Translation-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Network Address Translation |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | NAT (Network Address Translation) |

---

# 📖 Purpose

Network Address Translation (NAT) is one of the core functions of the FortiGate firewall. It enables communication between private and public networks by translating IP addresses as packets traverse the firewall.

In an enterprise environment, NAT is used to provide Internet access for internal users, publish internal applications securely, conserve public IPv4 addresses, and isolate private networks from external exposure.

This document explains how NAT is designed and implemented within the enterprise network, including the different NAT types supported by FortiGate and the scenarios in which each is used.

---

# 🎯 Design Objectives

- Enable secure Internet access
- Hide private IP addresses
- Publish internal applications securely
- Optimize public IP utilization
- Support branch connectivity
- Maintain routing consistency
- Simplify address management
- Enhance network security

---

# 🏗 Enterprise NAT Architecture

```text
                     🌐 Internet
                          │
                  Public IP Addresses
                          │
                  ┌────────────────┐
                  │   FortiGate    │
                  └────────────────┘
                     │          │
             Source NAT     Destination NAT
                (SNAT)          (DNAT)
                     │          │
                     ▼          ▼

            Internal Users   Published Servers

                     │
              Private Networks
```

---

# 📌 What is NAT?

Network Address Translation is the process of modifying the source or destination IP address of a packet while it passes through the firewall.

The translation allows private networks to communicate with public networks without exposing internal IP addresses directly.

---

# 🔄 NAT Processing Overview

A typical packet follows this sequence:

```text
Incoming Packet
        │
        ▼
Route Lookup
        │
        ▼
Firewall Policy Match
        │
        ▼
NAT Decision
        │
        ▼
IP Translation
        │
        ▼
Forward Packet
```

---

# 🌍 Types of NAT

FortiGate supports multiple NAT methods depending on the deployment requirement.

| NAT Type | Purpose |
|----------|---------|
| Source NAT (SNAT) | Translate source IP address |
| Destination NAT (DNAT) | Translate destination IP address |
| Policy NAT | NAT configured within firewall policies |
| Central NAT | Centralized NAT management |
| Dynamic NAT | Use available public IP addresses dynamically |
| Static NAT | Fixed one-to-one IP translation |
| Port Address Translation (PAT) | Multiple devices share one public IP |

---

# 🔹 Source NAT (SNAT)

Source NAT changes the **source IP address** of outgoing traffic before it leaves the firewall.

Typical use cases:

- Internet browsing
- Software updates
- Cloud connectivity
- Public API access
- Branch Internet breakout

Example:

```text
192.168.10.25

        │

        ▼

FortiGate

        │

        ▼

150.242.201.79

        │

        ▼

Internet
```

---

# 🔹 Destination NAT (DNAT)

Destination NAT changes the **destination IP address** of incoming traffic.

This allows external users to access internal services without exposing private IP addresses.

Example:

```text
Internet User

        │

150.242.201.79

        │

FortiGate

        │

192.168.1.20

(Web Server)
```

---

# 🔹 Policy NAT

In Policy NAT, address translation is configured directly within the firewall policy.

Characteristics:

- Easy to manage
- Common in small and medium deployments
- NAT tied to individual firewall rules

---

# 🔹 Central NAT

Central NAT separates NAT configuration from firewall policies.

Advantages:

- Centralized management
- Simplified policy design
- Better scalability
- Easier troubleshooting

Typically used in medium and large enterprise environments.

---

# 🌐 IP Pools

IP Pools define the public IP addresses used for Source NAT.

Benefits:

- Multiple public IP addresses
- Dedicated public IP per application
- ISP-specific translations
- Better traffic distribution

Example:

```text
Private Network

↓

IP Pool

↓

203.0.113.10

203.0.113.11

203.0.113.12
```

---

# 🔁 Port Address Translation (PAT)

PAT allows multiple internal devices to share a single public IP address by translating TCP and UDP port numbers.

Benefits:

- Conserves IPv4 addresses
- Supports thousands of simultaneous connections
- Common Internet access method

---

# 📊 Enterprise NAT Flow

```text
Internal User

        │

192.168.10.15

        │

FortiGate

        │

Firewall Policy

        │

Source NAT

        │

Public IP

        │

Internet
```

---

# 🏢 Enterprise Deployment Example

| Network | NAT Method |
|---------|------------|
| Employee LAN | Source NAT |
| Server VLAN | Source NAT |
| Public Web Server | Destination NAT (VIP) |
| Microsoft 365 Access | Source NAT |
| Branch VPN | NAT Exemption (where required) |

---

# 🔐 Design Considerations

When designing NAT, consider:

- Public IP availability
- Application requirements
- Routing architecture
- VPN connectivity
- Server publishing
- ISP redundancy
- Scalability
- Security requirements

---

# ✅ Best Practices

- Use private IP addresses internally.
- Publish servers using VIP instead of exposing private IPs.
- Use IP Pools when multiple public IPs are available.
- Document all NAT mappings.
- Avoid unnecessary NAT rules.
- Separate Internet NAT from VPN traffic.
- Monitor NAT utilization and sessions.
- Review NAT policies regularly.

---

# 📚 Related Documents

- 04-Routing.md
- 05-Firewall-Policies.md
- 07-Virtual-IP.md
- 08-IP-Pools.md
- 09-VPN.md

---

# 📌 Summary

Network Address Translation enables secure communication between private and public networks while protecting internal addressing schemes. FortiGate supports multiple NAT mechanisms—including Source NAT, Destination NAT, Policy NAT, and Central NAT—to address different enterprise requirements.

A well-designed NAT strategy improves security, conserves public IP addresses, supports application publishing, and provides flexible connectivity for users, servers, and cloud services.

> **Note:** This document focuses on the **Low-Level Design** of NAT. Detailed packet processing, NAT lookup sequence, CLI configuration, debugging, packet captures, session analysis, and production troubleshooting will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
07-Virtual-IP.md
```

The next document explains FortiGate Virtual IP (VIP), including destination NAT, server publishing, port forwarding, one-to-one mapping, load balancing concepts, VIP processing, and enterprise best practices for securely exposing internal services to external users.
