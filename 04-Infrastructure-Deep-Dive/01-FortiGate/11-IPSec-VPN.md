# 🔐 FortiGate IPSec VPN

> **Document:** `11-IPSec-VPN.md`

![FortiGate](https://img.shields.io/badge/FortiGate-IPSec%20VPN-red?style=for-the-badge)
![VPN](https://img.shields.io/badge/VPN-Site%20to%20Site-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate IPSec VPN |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Site-to-Site VPN |

---

# 📖 Purpose

IPSec VPN is the standard technology used to securely connect multiple enterprise locations across the Internet. It creates an encrypted tunnel between two or more FortiGate firewalls, allowing private networks to communicate securely over public infrastructure.

In enterprise environments, IPSec VPN is commonly used to connect Head Offices, Datacenters, Disaster Recovery (DR) sites, Branch Offices, Cloud Networks, and Business Partners.

---

# 🎯 Design Objectives

- Secure Site-to-Site Connectivity
- Encrypt Enterprise Traffic
- Connect Branch Offices
- Support Hybrid Infrastructure
- Ensure Data Confidentiality
- Protect Data Integrity
- Support High Availability
- Enable Scalable Enterprise Networking

---

# 🏗 Enterprise IPSec VPN Architecture

```text
                    🌐 Internet
                         │
     ┌───────────────────┼───────────────────┐
     │                                       │
     ▼                                       ▼

🏢 Head Office                       🏢 Branch Office
192.168.10.0/24                     192.168.20.0/24

     │                                       │
     ▼                                       ▼

🛡 FortiGate A =================== 🛡 FortiGate B
          Encrypted IPSec Tunnel

     │                                       │
     └──────────── Secure Communication ─────┘
```

---

# 📌 What is IPSec VPN?

IPSec (Internet Protocol Security) is a Layer-3 security protocol that encrypts IP packets before they are transmitted across untrusted networks.

It provides:

- Authentication
- Encryption
- Data Integrity
- Secure Tunnel Establishment

---

# 🌍 Enterprise Use Cases

IPSec VPN is commonly deployed for:

- Branch Office Connectivity
- Head Office to Datacenter
- Datacenter to DR Site
- Azure Site-to-Site VPN
- AWS Site-to-Site VPN
- Partner Connectivity
- MPLS Replacement
- Hybrid Cloud Networking

---

# 🔄 IPSec Tunnel Lifecycle

Every IPSec tunnel follows a defined process.

```text
Peer Discovery

        │

IKE Phase 1

        │

Secure Management Tunnel

        │

IKE Phase 2

        │

IPSec Tunnel Created

        │

Encrypted Data Transfer

        │

Tunnel Termination
```

---

# 🔐 IKE (Internet Key Exchange)

IKE is responsible for establishing secure communication between VPN peers.

Its responsibilities include:

- Peer Authentication
- Encryption Negotiation
- Key Exchange
- Tunnel Creation
- Session Management

FortiGate supports:

- IKEv1
- IKEv2

---

# 🔹 Phase 1

Phase 1 establishes a secure management channel between VPN peers.

Typical parameters include:

| Parameter | Purpose |
|-----------|----------|
| Peer IP | Remote Firewall |
| Authentication | Pre-Shared Key / Certificate |
| Encryption | AES-128 / AES-256 |
| Hash Algorithm | SHA-256 / SHA-512 |
| DH Group | Key Exchange Security |
| Lifetime | Security Association Duration |

---

# 🔹 Phase 2

Phase 2 creates the encrypted tunnel used to transfer user traffic.

Typical parameters include:

| Parameter | Purpose |
|-----------|----------|
| Local Network | Source Subnet |
| Remote Network | Destination Subnet |
| Encryption | AES |
| Authentication | SHA |
| PFS | Perfect Forward Secrecy |
| Lifetime | IPSec SA Duration |

---

# 🔐 Encryption Algorithms

Enterprise IPSec VPN deployments commonly use:

- AES-128
- AES-256
- SHA-256
- SHA-384
- SHA-512

These algorithms ensure that enterprise traffic remains confidential while traversing public networks.

---

# 🌐 Routing Integration

Once the VPN tunnel is established, routing determines which traffic uses the encrypted tunnel.

```text
Branch User

        │

Routing Table

        │

VPN Interface

        │

Encrypted Tunnel

        │

Datacenter
```

Static routes or dynamic routing protocols can direct traffic into the IPSec tunnel.

---

# 🔄 Traffic Flow

```text
User

↓

LAN

↓

FortiGate

↓

Firewall Policy

↓

IPSec VPN

↓

Internet

↓

Remote FortiGate

↓

Destination Network
```

---

# 🛡 Security Components

An IPSec VPN deployment consists of:

- VPN Peers
- Phase 1 Configuration
- Phase 2 Configuration
- Encryption Algorithms
- Authentication
- Firewall Policies
- Static or Dynamic Routing
- Tunnel Monitoring

---

# ☁ Hybrid Enterprise Connectivity

```text
Head Office

↓

IPSec VPN

↓

Yotta Datacenter

↓

Azure VPN Gateway

↓

Microsoft Azure
```

This enables secure communication between on-premises infrastructure and cloud resources.

---

# 🔁 Redundancy and High Availability

Enterprise IPSec deployments often include:

- Dual ISP Links
- Backup VPN Tunnels
- SD-WAN Integration
- Tunnel Health Monitoring
- Automatic Failover

These features improve resilience and reduce downtime during network failures.

---

# ⚙ Design Considerations

Before implementing IPSec VPN, consider:

- Public IP Availability
- Peer Authentication Method
- Encryption Standards
- Local and Remote Subnets
- Routing Design
- MTU and MSS Values
- Tunnel Redundancy
- Monitoring Requirements

---

# ✅ Best Practices

- Use IKEv2 whenever supported.
- Use AES-256 and SHA-256 or stronger algorithms.
- Enable Perfect Forward Secrecy (PFS).
- Use strong Pre-Shared Keys or Certificates.
- Monitor VPN tunnel status.
- Configure redundant tunnels for critical sites.
- Document all VPN parameters.
- Review tunnel logs regularly.

---

# 📚 Related Documents

- 09-VPN.md
- 10-SSL-VPN.md
- 12-Authentication.md
- 13-Logging.md
- 14-Debug.md

---

# 📌 Summary

FortiGate IPSec VPN provides secure site-to-site connectivity by establishing encrypted tunnels between enterprise locations. Using IKE Phase 1 and Phase 2 negotiations, strong encryption, authentication, and routing integration, IPSec VPN enables secure communication between branch offices, datacenters, disaster recovery sites, and cloud environments.

A properly designed IPSec VPN architecture improves security, supports hybrid infrastructure, ensures business continuity, and provides reliable connectivity across geographically distributed enterprise networks.

> **Note:** This document covers the **Low-Level Design** of IPSec VPN. Detailed Phase 1 and Phase 2 configuration, IKE negotiation process, route-based vs policy-based VPN, Dead Peer Detection (DPD), tunnel monitoring, CLI configuration, packet flow, debugging, and troubleshooting will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
12-Authentication.md
```

The next document explains FortiGate authentication architecture, including local users, administrator authentication, Active Directory integration, LDAP, RADIUS, TACACS+, certificate-based authentication, Multi-Factor Authentication (MFA), user groups, and enterprise identity management best practices.
