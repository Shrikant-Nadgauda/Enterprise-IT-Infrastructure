# 📌 Project Scope

> **Document:** 10-Scope.md

![Scope](https://img.shields.io/badge/Project-Scope-blue?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Review-red?style=for-the-badge)
![Infrastructure](https://img.shields.io/badge/Hybrid-Environment-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | Project Scope |
| Project | Enterprise Infrastructure Security Review |
| Environment | Production |
| Version | 1.0 |

---

# 📖 Introduction

This document defines the overall scope of the Enterprise Infrastructure Security Review project.

It clearly identifies which infrastructure components are included in the assessment, which components are excluded, the review boundaries, assumptions, project deliverables, and the responsibilities of all stakeholders involved.

The objective is to ensure that every participant has a common understanding of the project before the detailed technical assessment begins.

---

# 🎯 Project Objectives

- Assess the overall security posture of the enterprise infrastructure
- Review configuration of critical infrastructure components
- Identify security risks and configuration weaknesses
- Verify adherence to industry best practices
- Recommend security improvements
- Produce standardized review documentation

---

# ✅ In Scope

The following infrastructure components are included in this project.

## 🌐 Network Infrastructure

- Internet Connectivity
- Public IP Configuration
- FortiGate Firewall
- Core Layer-3 Switch
- Internal VLANs
- Site-to-Site IPSec VPN
- Routing
- NAT Configuration

---

## 🖥 On-Premises Infrastructure

- Active Directory
- Certificate Authority
- WSUS
- Backup Server
- NTP Server
- Email Protector
- Network Monitoring Server
- File Server
- Application Server
- Database Server

---

## ☁ Microsoft Cloud

- Microsoft Entra ID
- Microsoft 365
- Microsoft Intune
- Microsoft Authenticator

---

## 👤 Identity & Access

- User Accounts
- Administrative Accounts
- Security Groups
- Group Policies
- Password Policy
- Multi-Factor Authentication
- Azure AD Connect Synchronization

---

## 💻 Endpoints

- Windows Laptops
- Windows Desktops
- Intune Managed Devices
- Device Compliance
- BitLocker Configuration

---

## 🔐 Security Review

- Configuration Review
- Security Best Practices
- Administrative Access
- Patch Management
- Backup Verification
- Certificate Review
- Logging & Monitoring
- Authentication Review

---

# ❌ Out of Scope

The following components are not included unless specifically requested.

- Source Code Review
- Application Penetration Testing
- Web Application Assessment
- Secure Code Review
- Database Performance Tuning
- Network Performance Optimization
- Physical Security Assessment
- Social Engineering
- Wireless Penetration Testing
- Third-Party SaaS Applications
- Cloud Cost Optimization

---

# 🎯 Review Boundaries

| Area | Included |
|------|----------|
| Network Infrastructure | ✅ |
| Firewall Configuration | ✅ |
| Server Configuration | ✅ |
| Microsoft Cloud Services | ✅ |
| Identity Management | ✅ |
| Endpoint Management | ✅ |
| Security Configuration | ✅ |
| Operational Processes | Limited Review |

---

# 📦 Project Deliverables

Upon completion of the engagement, the following documents will be delivered.

- Infrastructure Documentation
- High-Level Design (HLD)
- Low-Level Design (LLD)
- Security Review Checklists
- Evidence Documents
- Risk Observations
- Findings Report
- Best Practice Recommendations
- Executive Summary
- Remediation Recommendations

---

# 📑 Review Methodology

The assessment follows a structured approach.

```text
Project Kickoff
        │
        ▼
Environment Understanding
        │
        ▼
Architecture Review
        │
        ▼
Configuration Review
        │
        ▼
Evidence Collection
        │
        ▼
Risk Identification
        │
        ▼
Recommendations
        │
        ▼
Final Documentation
```

---

# 🤝 Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| Customer IT Team | Provide Access & Information |
| Security Consultant | Perform Security Review |
| Infrastructure Team | Validate Configuration |
| Project Manager | Coordinate Activities |
| Management | Review Final Report |

---

# ⚠ Assumptions

The following assumptions apply during the assessment.

- Required administrative access will be provided.
- Production changes are outside the scope unless approved.
- Customer representatives will be available during scheduled review sessions.
- Existing infrastructure documentation is assumed to be accurate where provided.
- Security review is configuration-based and non-intrusive.

---

# 🚫 Limitations

- No production changes without approval.
- No disruptive testing.
- No denial-of-service testing.
- No exploitation of discovered vulnerabilities.
- Findings are based on the environment at the time of assessment.

---

# 📊 Success Criteria

The project will be considered successful when:

- All in-scope components are reviewed.
- Evidence is collected for every checklist item.
- Security gaps are identified and documented.
- Actionable recommendations are provided.
- Final documentation is approved by stakeholders.

---

# 📌 Summary

This document establishes the scope and boundaries of the Enterprise Infrastructure Security Review. It ensures that both the customer and the review team have a clear understanding of the systems being assessed, the expected deliverables, and the overall objectives of the engagement.

This concludes the **Project Documentation** section and provides the foundation for the detailed technical documentation that follows in subsequent directories.

---

📌 Next Directory

```text
02-HLD/
```
