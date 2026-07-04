# 🔐 FortiGate Virtual Private Network (VPN)

> **Document:** `09-VPN.md`

![FortiGate](https://img.shields.io/badge/FortiGate-VPN-red?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Encrypted%20Communication-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate VPN Architecture |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Secure Connectivity |

---

# 📖 Purpose

Virtual Private Network (VPN) technology enables secure communication between remote users, branch offices, datacenters, and cloud environments over untrusted networks such as the Internet.

FortiGate VPN solutions use encryption, authentication, and integrity validation to ensure that sensitive business traffic remains protected while traversing public networks.

VPN technology forms the foundation of modern enterprise connectivity, especially for organizations operating multiple branches, remote workers, cloud platforms, and hybrid infrastructures.

---

# 🎯 Design Objectives

- Secure Data Transmission
- Protect Business Traffic
- Connect Branch Offices
- Enable Remote User Access
- Extend Enterprise Networks
- Support Hybrid Infrastructure
- Ensure Data Confidentiality
- Maintain Business Continuity

---

# 🏗 Enterprise VPN Architecture

```text
                    🌐 Internet
                          │

         ┌────────────────┼────────────────┐
         │                │                │
         ▼                ▼                ▼

   🏢 Branch A      🏢 Branch B      👨‍💻 Remote Users

         │                │                │

         └─────────── VPN Tunnels ─────────┘

                          │

                    🛡 FortiGate

                          │

                  Core Network

                          │

      ┌───────────┬───────────┬───────────┐
      ▼           ▼           ▼

 Active Dir.   File Server   Applications
```

---

# 📌 What is a VPN?

A VPN creates an encrypted tunnel between two endpoints.

Instead of sending data in clear text across the Internet, VPN technology encrypts traffic before transmission and decrypts it at the destination.

This ensures:

- Confidentiality
- Integrity
- Authentication
- Secure Communication

---

# 🔐 Why VPN is Required

Without VPN:

```text
User

↓

Internet

↓

Traffic Visible
```

With VPN:

```text
User

↓

Encrypted Tunnel

↓

FortiGate

↓

Enterprise Network
```

Only authorized devices can access the protected resources.

---

# 🌍 Types of VPN

FortiGate supports multiple VPN technologies.

| VPN Type | Purpose |
|-----------|----------|
| Site-to-Site VPN | Connect Branch Offices |
| Remote Access VPN | Connect Remote Users |
| IPSec VPN | Network-to-Network Connectivity |
| SSL VPN | User-Based Secure Access |

---

# 🏢 Site-to-Site VPN

Site-to-Site VPN connects two or more office locations securely.

Example:

```text
Mumbai Office

       │

IPSec VPN

       │

Internet

       │

IPSec VPN

       │

Yotta Datacenter
```

Benefits:

- Secure Branch Connectivity
- Private Communication
- Reduced MPLS Dependency
- Cost Effective

---

# 👨‍💻 Remote Access VPN

Remote Access VPN allows individual users to connect securely to enterprise resources.

Example:

```text
Employee Laptop

        │

 SSL VPN

        │

 Internet

        │

 FortiGate

        │

 Internal Network
```

Common use cases:

- Work From Home
- Remote Administration
- Vendor Access
- Field Operations

---

# 🔑 VPN Security Components

Every VPN deployment relies on the following components:

| Component | Purpose |
|------------|----------|
| Encryption | Protect Data |
| Authentication | Verify Identity |
| Integrity Check | Prevent Tampering |
| Tunnel | Secure Communication Path |
| Key Exchange | Establish Encryption Keys |

---

# 🔄 VPN Tunnel Lifecycle

A VPN tunnel follows a defined lifecycle.

```text
Tunnel Request

        │

Authentication

        │

Key Exchange

        │

Tunnel Establishment

        │

Encrypted Traffic

        │

Tunnel Termination
```

---

# 🌐 VPN and Routing

VPN tunnels become part of the routing architecture.

```text
Branch Network

↓

VPN Tunnel

↓

FortiGate

↓

Routing Table

↓

Datacenter Network
```

Routing determines which traffic should enter the VPN tunnel.

---

# 🔒 Encryption Overview

VPN security relies heavily on encryption.

Common algorithms include:

- AES-128
- AES-256
- SHA-256
- SHA-512

Encryption ensures intercepted traffic cannot be read by unauthorized parties.

---

# 🛡 Authentication Methods

FortiGate supports multiple authentication methods.

| Method | Description |
|----------|-------------|
| Local User Database | Firewall Users |
| Active Directory | Domain Authentication |
| RADIUS | Central Authentication |
| LDAP | Directory Services |
| Certificate-Based | PKI Authentication |
| MFA | Multi-Factor Authentication |

---

# ☁ Hybrid Infrastructure Connectivity

VPN plays a critical role in hybrid environments.

```text
On-Prem Datacenter

        │

 VPN Tunnel

        │

 FortiGate

        │

 Internet

        │

 Microsoft Cloud
```

This enables secure communication between on-premises and cloud resources.

---

# 📊 Enterprise Deployment Example

```text
Head Office

↓

IPSec VPN

↓

Yotta Datacenter

↓

FortiGate Hub

↓

Application Servers

↓

Database Servers

↓

Microsoft Cloud Services
```

---

# ⚙ Design Considerations

Before implementing VPN, consider:

- Number of Sites
- User Count
- Authentication Method
- Bandwidth Requirements
- Encryption Standards
- High Availability
- Cloud Integration
- Regulatory Compliance

---

# ✅ Best Practices

- Use strong encryption algorithms.
- Implement MFA for remote users.
- Restrict VPN access based on business requirements.
- Monitor VPN activity continuously.
- Use certificate-based authentication where possible.
- Document all VPN tunnels.
- Review inactive VPN accounts regularly.
- Test failover scenarios periodically.

---

# 🚨 Common Enterprise VPN Use Cases

| Use Case | VPN Type |
|-----------|----------|
| Branch Connectivity | IPSec VPN |
| Remote Employees | SSL VPN |
| Vendor Access | SSL VPN |
| Datacenter Interconnect | IPSec VPN |
| Cloud Connectivity | IPSec VPN |

---

# 📚 Related Documents

- 04-Routing.md
- 05-Firewall-Policies.md
- 06-NAT.md
- 10-SSL-VPN.md
- 11-IPSec-VPN.md
- 14-Authentication.md

---

# 📌 Summary

VPN technology enables secure communication across untrusted networks by creating encrypted tunnels between users, offices, datacenters, and cloud environments. FortiGate supports both Site-to-Site and Remote Access VPN architectures, providing secure, scalable, and flexible connectivity for modern enterprise infrastructures.

A properly designed VPN architecture strengthens security, supports business continuity, enables hybrid cloud adoption, and allows organizations to securely connect users and locations regardless of geographic distance.

> **Note:** This document provides the Low-Level Design overview of VPN architecture. Detailed SSL VPN design, IPSec VPN design, Phase 1 & Phase 2 negotiations, encryption algorithms, tunnel establishment process, troubleshooting, packet flow analysis, and configuration examples are covered in the upcoming dedicated VPN documents.

---

📌 Next Document

```text
10-SSL-VPN.md
```

The next document explains FortiGate SSL VPN architecture, including remote user connectivity, authentication workflows, portal design, MFA integration, traffic flow, security controls, and enterprise best practices for secure remote access.
