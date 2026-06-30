# 🏢 Active Directory Architecture

> **Document:** `04-Active-Directory-Architecture.md`

![Microsoft](https://img.shields.io/badge/Microsoft-Active%20Directory-blue?style=for-the-badge)
![Identity](https://img.shields.io/badge/Identity-Management-green?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Documentation-HLD-orange?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Active Directory Architecture |
| Document Type | High-Level Design (HLD) |
| Technology | Microsoft Active Directory Domain Services |
| Environment | Production |

---

# 📖 Introduction

Microsoft Active Directory (AD DS) is the primary identity and authentication platform of the enterprise infrastructure.

It provides centralized management of users, computers, servers, security groups, and organizational policies. Every employee authenticates against Active Directory before accessing enterprise resources such as file servers, business applications, printers, VPN, and Microsoft Cloud services.

In a hybrid environment, Active Directory also acts as the identity source for Microsoft Entra ID through Azure AD Connect.

---

# 🎯 Business Objectives

- Centralize Identity Management
- Secure User Authentication
- Simplify User Administration
- Apply Enterprise Security Policies
- Enable Single Sign-On (SSO)
- Integrate with Microsoft Cloud
- Manage Enterprise Devices

---

# 🏗 Active Directory Position

```text
                         Employees
                              │
                              ▼
                     Windows Computers
                              │
                              ▼
                  Active Directory Domain
                              │
      ┌──────────────┬──────────────┬
      ▼              ▼              ▼

 Users           Computers      Security Groups

      │              │              │
      └──────────────┼──────────────┘
                     ▼

               Group Policies

                     │
                     ▼

                 DNS Services

                     │
                     ▼

             Azure AD Connect

                     │
                     ▼

           Microsoft Entra ID
```

---

# 🏢 Core Components

| Component | Purpose |
|-----------|---------|
| Domain | Central Identity Database |
| Domain Controller | Authentication & Authorization |
| DNS | Name Resolution |
| Organizational Units (OU) | Administrative Structure |
| Users | Employee Accounts |
| Groups | Permission Management |
| Computers | Domain-Joined Devices |
| Group Policy | Centralized Configuration |

---

# 👥 Identity Management

Active Directory stores and manages:

- Employee Accounts
- Administrator Accounts
- Service Accounts
- Computer Accounts
- Security Groups
- Organizational Units

This allows IT administrators to manage the entire organization from a centralized platform.

---

# 🔐 Authentication Flow

```text
User Login
     │
     ▼
Windows Computer
     │
     ▼
Domain Controller
     │
     ▼
Credential Verification
     │
     ▼
Authentication Successful
     │
     ▼
Access Enterprise Resources
```

---

# 🏢 Organizational Units (OU)

Organizational Units help organize enterprise objects logically.

Example:

```text
Company
│
├── Users
├── Servers
├── Workstations
├── IT
├── HR
├── Finance
└── Branch Offices
```

This structure simplifies administration and Group Policy deployment.

---

# 📜 Group Policy (GPO)

Group Policies provide centralized management of domain devices.

Common policy examples include:

- Password Policies
- Account Lockout Policies
- Desktop Restrictions
- Windows Updates
- Security Settings
- USB Restrictions
- Software Deployment
- Login Scripts

---

# 🌐 DNS Integration

Active Directory depends heavily on DNS.

DNS provides:

- Domain Name Resolution
- Domain Controller Discovery
- Authentication Support
- Service Location

Without DNS, Active Directory authentication cannot function correctly.

---

# ☁ Hybrid Identity

The organization uses a Hybrid Identity architecture.

```text
Active Directory
        │
        ▼
Azure AD Connect
        │
        ▼
Microsoft Entra ID
        │
        ├── Microsoft 365
        ├── Microsoft Intune
        └── Microsoft Authenticator
```

This allows users to access both on-premises and cloud resources using the same identity.

---

# 🔗 Enterprise Integrations

Active Directory integrates with:

| Service | Purpose |
|----------|---------|
| Certificate Authority | Certificate Authentication |
| File Server | User Permissions |
| WSUS | Computer Targeting |
| Application Servers | User Authentication |
| VPN | User Authentication |
| Microsoft Entra ID | Identity Synchronization |
| Microsoft 365 | Cloud Authentication |
| Microsoft Intune | Device Identity |

---

# 🛡 Security Features

Active Directory improves enterprise security by providing:

- Centralized Authentication
- Role-Based Access Control (RBAC)
- Group-Based Permissions
- Password Policies
- Account Lockout Policies
- Security Auditing
- Kerberos Authentication
- LDAP Directory Services

---

# 📈 Business Benefits

- Single User Identity
- Centralized Administration
- Simplified User Lifecycle Management
- Secure Authentication
- Consistent Security Policies
- Hybrid Cloud Integration
- Reduced Administrative Overhead
- Improved Compliance

---

# 📚 Related Documents

- 05-Certificate-Authority-Architecture.md
- 14-Microsoft-Entra-ID-Architecture.md
- 19-Security-Architecture.md

---

# 📌 Summary

Active Directory is the foundation of the enterprise identity infrastructure. It centralizes authentication, authorization, device management, and policy enforcement while integrating seamlessly with Microsoft Entra ID to provide a secure hybrid identity solution.

As the organization's primary identity provider, Active Directory enables secure access to both on-premises resources and Microsoft Cloud services through a single, centralized identity platform.

> **Note:** This document provides the architectural overview of Active Directory. Installation, Domain Controller deployment, OU design, user creation, Group Policy configuration, troubleshooting, PowerShell, and administration will be covered in the **LLD** and **Learning** sections.

---

📌 Next Document

```text
05-Certificate-Authority-Architecture.md
```
