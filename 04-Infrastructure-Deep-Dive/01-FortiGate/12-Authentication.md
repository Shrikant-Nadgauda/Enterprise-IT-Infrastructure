# 🔐 FortiGate Authentication

> **Document:** `12-Authentication.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Authentication-red?style=for-the-badge)
![Identity](https://img.shields.io/badge/Identity-Access%20Management-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Authentication |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Identity & Access Management |

---

# 📖 Purpose

Authentication is the process of verifying the identity of users, administrators, and devices before granting access to enterprise resources.

FortiGate supports multiple authentication methods that integrate with enterprise identity platforms, enabling centralized user management, secure administrator access, VPN authentication, captive portal authentication, and policy-based access control.

A properly designed authentication architecture improves security, simplifies user management, and supports compliance requirements.

---

# 🎯 Design Objectives

- Verify User Identity
- Secure Administrator Access
- Centralize Authentication
- Support Enterprise Directory Services
- Enable Multi-Factor Authentication
- Control Network Access
- Improve Audit & Compliance
- Reduce Unauthorized Access

---

# 🏗 Enterprise Authentication Architecture

```text
                     👤 Users / Administrators
                               │
                 Username + Password / MFA
                               │
                               ▼
                     🛡 FortiGate Firewall
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼

     Local Users          Active Directory        LDAP

          │                    │                    │
          └────────────────────┼────────────────────┘
                               │
                               ▼

                         User Groups

                               │

                      Firewall Policies

                               │

                   Enterprise Resources
```

---

# 📌 What is Authentication?

Authentication is the process of confirming that a user or device is who they claim to be before allowing access to protected resources.

FortiGate authenticates users before allowing access to:

- Firewall Management
- SSL VPN
- IPSec VPN
- Wi-Fi Networks
- Captive Portal
- Firewall Policies
- Administrative Console

---

# 🌍 Authentication Components

| Component | Purpose |
|-----------|---------|
| User | Person requesting access |
| Credentials | Username & Password |
| Authentication Server | Validates User Identity |
| User Group | Applies Access Permissions |
| Firewall Policy | Controls Resource Access |
| MFA | Additional Security Layer |

---

# 🔹 Local Authentication

FortiGate maintains its own local user database.

Suitable for:

- Small Deployments
- Emergency Accounts
- Test Environments
- Backup Administrator Access

Advantages:

- Simple Configuration
- No External Dependency
- Fast Authentication

---

# 🔹 Active Directory Authentication

FortiGate can integrate directly with Microsoft Active Directory.

Benefits:

- Centralized User Management
- Domain Authentication
- Existing User Accounts
- Group-Based Access Control
- Single Identity Source

Common Uses:

- SSL VPN
- Administrator Login
- Firewall Policies
- Captive Portal

---

# 🔹 LDAP Authentication

LDAP enables FortiGate to authenticate users from directory services.

Supported Directories:

- Microsoft Active Directory
- OpenLDAP
- Other LDAP-Compatible Servers

Typical Use Cases:

- VPN Authentication
- User-Based Policies
- Web Filtering
- Captive Portal

---

# 🔹 RADIUS Authentication

RADIUS provides centralized authentication for enterprise network devices.

Common Integration:

- Microsoft NPS
- Cisco ISE
- FreeRADIUS

Typical Uses:

- VPN Users
- Wi-Fi Authentication
- Network Access Control
- Administrator Authentication

---

# 🔹 TACACS+ Authentication

TACACS+ is primarily used for administrator authentication.

Advantages:

- Command Authorization
- Centralized Administrator Control
- Detailed Accounting Logs
- Role-Based Administration

Commonly used in large enterprise environments.

---

# 🔹 Certificate-Based Authentication

Instead of passwords, users authenticate using digital certificates.

Benefits:

- Strong Identity Verification
- Passwordless Authentication
- Higher Security
- Reduced Credential Theft Risk

Typical Uses:

- SSL VPN
- IPSec VPN
- Device Authentication

---

# 🔹 Multi-Factor Authentication (MFA)

MFA requires users to provide an additional verification factor beyond a password.

Common MFA Methods:

- Microsoft Authenticator
- FortiToken
- OTP
- Push Notification
- Hardware Token

Benefits:

- Prevents Credential Theft
- Reduces Unauthorized Access
- Improves Identity Security

---

# 👥 User Groups

Authentication is commonly combined with User Groups.

```text
Users

↓

Authentication

↓

User Group

↓

Firewall Policy

↓

Application Access
```

Example Groups:

- IT Administrators
- Employees
- HR
- Finance
- Vendors
- Support Engineers

---

# 🔄 Authentication Flow

```text
User Login

      │

Credential Verification

      │

Authentication Server

      │

User Group Validation

      │

Firewall Policy

      │

Access Granted
```

---

# 🛡 Authentication for VPN

Authentication is a key component of VPN security.

```text
Remote User

↓

SSL VPN Portal

↓

Authentication

↓

MFA

↓

VPN Tunnel

↓

Enterprise Network
```

Only authenticated users are allowed to establish VPN sessions.

---

# 🔐 Administrator Authentication

Administrator access should always use centralized authentication.

Recommended Methods:

- Active Directory
- TACACS+
- RADIUS
- MFA
- Certificate Authentication

This ensures administrative activities are traceable and centrally managed.

---

# ⚙ Design Considerations

Before implementing authentication, consider:

- Identity Source
- User Population
- MFA Requirements
- Password Policies
- Administrator Security
- User Group Design
- High Availability
- Audit Requirements

---

# ✅ Best Practices

- Use Active Directory as the primary identity source.
- Enable MFA for all remote access users.
- Separate administrator accounts from user accounts.
- Use role-based user groups.
- Disable unused local accounts.
- Enforce strong password policies.
- Review authentication logs regularly.
- Apply the Principle of Least Privilege.

---

# 📚 Related Documents

- 09-VPN.md
- 10-SSL-VPN.md
- 11-IPSec-VPN.md
- 13-Logging.md
- 14-Debug.md

---

# 📌 Summary

Authentication is a critical security function within FortiGate, ensuring that only verified users and administrators can access enterprise resources. By integrating with centralized identity providers such as Active Directory, LDAP, RADIUS, and TACACS+, FortiGate simplifies identity management while improving security and compliance.

Combining authentication with user groups, firewall policies, and Multi-Factor Authentication enables organizations to implement secure, scalable, and manageable access control across the enterprise.

> **Note:** This document covers the **Low-Level Design** of FortiGate Authentication. Detailed LDAP integration, Active Directory configuration, RADIUS, TACACS+, certificate authentication, MFA deployment, troubleshooting, CLI configuration, and authentication debugging will be covered in the **Infrastructure Deep Dive** section.

---

# 📌 Next Document

```text
13-Logging.md
```

The next document explains FortiGate logging architecture, including local logging, FortiAnalyzer integration, Syslog forwarding, log categories, event auditing, log retention, monitoring workflows, and enterprise best practices for centralized security visibility.
