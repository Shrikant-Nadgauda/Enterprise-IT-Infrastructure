# 🌐 FortiGate IP Pools

> **Document:** `08-IP-Pools.md`

![FortiGate](https://img.shields.io/badge/FortiGate-IP%20Pools-red?style=for-the-badge)
![NAT](https://img.shields.io/badge/NAT-Source%20Translation-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate IP Pools |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Source NAT |

---

# 📖 Purpose

IP Pools are used by FortiGate to define one or more public IP addresses that can be used for **Source NAT (SNAT)** when internal users or servers communicate with external networks.

Instead of using the firewall interface IP for NAT, IP Pools allow administrators to control which public IP address is assigned to outbound traffic. This improves scalability, supports multiple Internet-facing applications, enables ISP-specific routing, and simplifies public IP management in enterprise environments.

---

# 🎯 Design Objectives

- Control Source NAT
- Utilize Multiple Public IPs
- Separate User and Server Traffic
- Support ISP Requirements
- Improve Public IP Management
- Enable One-to-One NAT
- Support Load Distribution
- Simplify Enterprise NAT Design

---

# 🏗 Enterprise IP Pool Architecture

```text
                  Internal Network
                        │
      ┌─────────────────┼─────────────────┐
      ▼                 ▼                 ▼

 User VLAN         Server VLAN      DMZ Network

      │                 │                 │

      └──────────────┬────────────────────┘
                     │
                     ▼

              FortiGate Firewall

                     │

               Source NAT

                     │

        ┌────────────┼────────────┐
        ▼            ▼            ▼

203.0.113.10   203.0.113.11   203.0.113.12

                IP Pool
                     │
                     ▼
                 Internet
```

---

# 📌 What is an IP Pool?

An IP Pool is a collection of one or more public IP addresses that FortiGate uses during Source NAT.

Instead of translating all outbound traffic to the firewall interface IP, FortiGate can translate sessions using addresses from the configured IP Pool.

---

# 🔄 Traffic Processing

```text
Internal User

        │

Private IP

        │

Firewall Policy

        │

IP Pool Selected

        │

Source NAT

        │

Public IP Assigned

        │

Internet
```

---

# 🌍 Why Use IP Pools?

Without an IP Pool:

```text
All Users

↓

Firewall Interface IP

↓

Internet
```

With an IP Pool:

```text
Users

↓

IP Pool

↓

203.0.113.10

203.0.113.11

203.0.113.12

↓

Internet
```

This provides greater flexibility and efficient utilization of available public IP addresses.

---

# 🔹 Types of IP Pools

FortiGate supports multiple IP Pool modes.

| Type | Purpose |
|------|---------|
| Overload | Multiple users share one public IP using PAT |
| One-to-One | One private IP maps to one public IP |
| Fixed Port Range | Preserve source ports for specific applications |
| Dynamic Pool | Allocate addresses dynamically from a pool |

---

# 🔹 Overload IP Pool

Overload mode allows many internal devices to share a single public IP by using different source port numbers.

Example:

```text
192.168.10.10

192.168.10.20

192.168.10.30

        │

        ▼

203.0.113.10

        │

Internet
```

Suitable for:

- Employee Internet Access
- Web Browsing
- Microsoft 365
- General Outbound Traffic

---

# 🔹 One-to-One IP Pool

Each private IP is mapped to a dedicated public IP.

Example:

```text
192.168.10.50

↓

203.0.113.50
```

Suitable for:

- Banking Applications
- Whitelisted Applications
- Secure Partner Connectivity
- Static Public Identity

---

# 🏢 Enterprise Deployment Example

| Network | IP Pool | Purpose |
|---------|---------|----------|
| Employee LAN | User-IPPool | Internet Browsing |
| Server VLAN | Server-IPPool | Outbound Server Access |
| DMZ | DMZ-IPPool | Public Services |
| Backup Server | Dedicated Public IP | Replication |
| Application Server | Static Public IP | Third-Party Integration |

---

# 🔐 IP Pool Selection

An IP Pool is selected based on the matching firewall policy.

```text
Traffic

↓

Firewall Policy

↓

Source NAT Enabled

↓

Assigned IP Pool

↓

Internet
```

Different policies can use different IP Pools depending on business requirements.

---

# 📊 Design Considerations

Before creating an IP Pool, consider:

- Number of Public IPs
- ISP Allocation
- Application Requirements
- NAT Mode
- Security Policies
- Routing Design
- Future Growth
- Public IP Utilization

---

# ⚙ Enterprise Design Example

```text
Employee Network

↓

User-IPPool

↓

203.0.113.10

----------------------------

Application Server

↓

App-IPPool

↓

203.0.113.20

----------------------------

Database Backup

↓

Backup-IPPool

↓

203.0.113.30
```

This design provides clear separation between user traffic and server traffic while simplifying troubleshooting and public IP management.

---

# ✅ Best Practices

- Create separate IP Pools for different services.
- Use descriptive naming conventions.
- Allocate dedicated IPs for business-critical applications.
- Document all public IP assignments.
- Avoid unnecessary one-to-one mappings.
- Monitor IP Pool utilization.
- Review unused IP Pools regularly.
- Align IP Pools with firewall policies.

---

# 📚 Related Documents

- 05-Firewall-Policies.md
- 06-NAT.md
- 07-Virtual-IP.md
- 09-VPN.md
- 10-SSL-VPN.md

---

# 📌 Summary

IP Pools provide administrators with precise control over how outbound traffic is translated to public IP addresses. They enable efficient public IP utilization, support application-specific requirements, simplify ISP integration, and improve scalability for enterprise Internet connectivity.

A well-designed IP Pool strategy ensures predictable Source NAT behavior, easier troubleshooting, and better separation of user, server, and application traffic.

> **Note:** This document focuses on the **Low-Level Design** of IP Pools. IP Pool configuration, CLI commands, overload NAT, one-to-one NAT, fixed-port configuration, troubleshooting, and packet-level analysis will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
09-VPN.md
```

The next document explains FortiGate Virtual Private Network (VPN) architecture, including remote access VPN, site-to-site VPN, encrypted communication, VPN components, tunnel lifecycle, routing integration, authentication methods, and enterprise best practices for secure connectivity.
