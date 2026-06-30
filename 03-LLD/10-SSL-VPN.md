# 🔒 FortiGate SSL VPN

> **Document:** `10-SSL-VPN.md`

![FortiGate](https://img.shields.io/badge/FortiGate-SSL%20VPN-red?style=for-the-badge)
![Remote Access](https://img.shields.io/badge/Remote%20Access-Secure-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate SSL VPN |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Remote Access VPN |

---

# 📖 Purpose

SSL VPN provides secure remote access for users connecting to the enterprise network over the Internet using SSL/TLS encryption.

Unlike IPSec VPN, SSL VPN is designed primarily for individual users such as employees, administrators, support engineers, and third-party vendors who need secure access to internal applications and resources from any location.

FortiGate SSL VPN supports browser-based access as well as full network access through the FortiClient VPN application.

---

# 🎯 Design Objectives

- Secure Remote User Access
- Encrypted Communication
- User Authentication
- Support Work From Home
- Controlled Access to Internal Resources
- Multi-Factor Authentication (MFA)
- Centralized VPN Management
- Secure Hybrid Workforce

---

# 🏗 Enterprise SSL VPN Architecture

```text
                    👨‍💻 Remote User
                           │
                    Laptop / Mobile
                           │
                     HTTPS (SSL/TLS)
                           │
                      🌐 Internet
                           │
                           ▼
                  🛡 FortiGate Firewall
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼

     Authentication   SSL VPN Portal   Firewall Policy
          │                │                │
          └────────────────┼────────────────┘
                           │
                           ▼
                  Internal Enterprise Network
                           │
      ┌─────────────┬─────────────┬─────────────┐
      ▼             ▼             ▼

 Active Directory  File Server  Application Server
```

---

# 📌 What is SSL VPN?

SSL VPN is a remote access solution that creates an encrypted tunnel between a remote user and the enterprise network using SSL/TLS protocols.

Users authenticate through FortiGate and are granted access only to the resources permitted by VPN policies and user permissions.

---

# 🌍 Why SSL VPN?

Modern organizations have employees working from:

- Home
- Customer Sites
- Branch Offices
- Airports
- Hotels
- Mobile Devices

SSL VPN enables these users to securely connect without exposing the internal network directly to the Internet.

---

# 🔄 SSL VPN Connection Flow

```text
Remote User

        │

Internet

        │

FortiGate SSL VPN Portal

        │

User Authentication

        │

VPN Tunnel Established

        │

Firewall Policy

        │

Enterprise Resources
```

---

# 🔐 SSL VPN Components

| Component | Purpose |
|-----------|---------|
| SSL VPN Portal | User Login Interface |
| SSL/TLS Encryption | Secure Communication |
| Authentication Server | Verify User Identity |
| VPN Policies | Control Resource Access |
| FortiClient | Full Tunnel VPN Client |
| Web Portal | Browser-Based Access |

---

# 👤 Authentication Methods

FortiGate supports multiple authentication methods for SSL VPN.

- Local Users
- Active Directory
- LDAP
- RADIUS
- TACACS+
- Microsoft Entra ID
- Certificate Authentication
- Multi-Factor Authentication (MFA)

---

# 🖥 SSL VPN Access Modes

## Web Mode

Users access internal applications directly through a web browser.

Suitable for:

- Internal Websites
- RDP Bookmarks
- SSH Access
- File Shares
- Web Applications

---

## Tunnel Mode

Tunnel Mode provides full network connectivity using the FortiClient VPN application.

Users receive an IP address from the SSL VPN pool and can access internal resources as permitted.

Suitable for:

- Domain Resources
- File Servers
- Application Servers
- Remote Administration
- Internal Business Applications

---

# 🌐 Enterprise Traffic Flow

```text
Remote User

        │

HTTPS (TCP 443)

        │

FortiGate SSL VPN

        │

Authentication

        │

VPN Tunnel

        │

Firewall Policy

        │

Internal Network
```

---

# 🔒 Security Controls

SSL VPN security is enhanced through:

- Strong User Authentication
- SSL/TLS Encryption
- Multi-Factor Authentication
- User Groups
- VPN Portals
- Firewall Policies
- Session Timeout
- Login Restrictions

---

# 👥 User Group Design

Enterprise deployments typically create different VPN access groups.

| User Group | Access Level |
|------------|--------------|
| IT Administrators | Full Infrastructure Access |
| Employees | Business Applications |
| HR Team | HR Systems |
| Finance Team | Finance Applications |
| Vendors | Restricted Access |
| Support Engineers | Assigned Servers Only |

---

# 🛡 Firewall Integration

SSL VPN users do not automatically gain access to the network.

Traffic must pass through:

```text
SSL VPN Login

↓

VPN Tunnel

↓

Firewall Policy

↓

Security Inspection

↓

Destination Server
```

Firewall policies determine which internal resources users are permitted to access.

---

# ☁ Hybrid Enterprise Integration

SSL VPN integrates seamlessly with hybrid environments.

```text
Remote User

↓

SSL VPN

↓

FortiGate

↓

On-Prem Servers

↓

Azure AD Connect

↓

Microsoft Entra ID

↓

Microsoft 365
```

Users can securely access both on-premises and cloud-integrated resources.

---

# ⚙ Design Considerations

Before deploying SSL VPN, consider:

- Expected Number of Users
- Authentication Method
- MFA Requirements
- IP Address Pool
- User Groups
- Portal Design
- Split Tunnel vs Full Tunnel
- Logging and Monitoring
- High Availability

---

# ✅ Best Practices

- Enable Multi-Factor Authentication.
- Use Active Directory or Entra ID for authentication.
- Restrict VPN access using user groups.
- Apply the Principle of Least Privilege.
- Use Split Tunnel only when required.
- Enable session logging.
- Monitor failed login attempts.
- Review inactive VPN users regularly.
- Keep FortiClient updated.
- Protect the SSL VPN portal with strong security policies.

---

# 📚 Related Documents

- 09-VPN.md
- 11-IPSec-VPN.md
- 12-Authentication.md
- 13-Logging.md
- 14-Debug.md

---

# 📌 Summary

FortiGate SSL VPN provides secure remote access for enterprise users by creating encrypted SSL/TLS tunnels between remote devices and the corporate network. It supports browser-based and full-tunnel connectivity, integrates with enterprise authentication systems, and enables secure access to internal applications while maintaining centralized security controls.

SSL VPN is an essential component of modern hybrid infrastructures, allowing organizations to securely support remote work without compromising enterprise security.

> **Note:** This document covers the **Low-Level Design** of SSL VPN. Detailed portal configuration, FortiClient deployment, authentication configuration, MFA setup, split tunneling, troubleshooting, packet flow, and CLI commands will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
11-IPSec-VPN.md
```

The next document explains FortiGate IPSec VPN architecture, including Phase 1 and Phase 2 negotiations, IKE protocols, encryption algorithms, tunnel establishment, routing integration, site-to-site connectivity, redundancy, and enterprise best practices for secure branch and datacenter communication.
