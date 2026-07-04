# 🛡 FortiGate Security Profiles

> **Document:** `16-Security-Profiles.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Security%20Profiles-red?style=for-the-badge)
![Threat Protection](https://img.shields.io/badge/Threat%20Protection-Layered%20Security-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Security Profiles |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Threat Protection |

---

# 📖 Purpose

Security Profiles are FortiGate's advanced security engines that inspect network traffic after it matches a firewall policy. They provide protection against malware, network attacks, malicious websites, unauthorized applications, spam, and encrypted threats.

Instead of relying only on allow or deny firewall policies, Security Profiles inspect the content of traffic to identify and block modern cyber threats.

---

# 🎯 Design Objectives

- Layered Threat Protection
- Malware Prevention
- Intrusion Detection & Prevention
- Web Content Filtering
- Application Visibility
- Secure DNS Resolution
- Email Protection
- Secure Encrypted Traffic Inspection

---

# 🏗 Enterprise Security Profile Architecture

```text
                 🌐 Internet
                      │
                      ▼

             🛡 FortiGate Firewall

                      │

              Firewall Policy Match

                      │

        ┌─────────────┼─────────────┐
        ▼             ▼             ▼

   Antivirus        IPS      Web Filter

        │             │             │
        ├─────────────┼─────────────┤
        ▼             ▼             ▼

 Application     DNS Filter   SSL Inspection

                      │

               Clean Traffic

                      │

              Enterprise Network
```

---

# 📌 What are Security Profiles?

Security Profiles are inspection modules that analyze network traffic after it has been permitted by a firewall policy.

Each profile performs a specific security function to protect enterprise users, applications, and data from cyber threats.

---

# 🔄 Traffic Inspection Flow

```text
Internet Traffic

        │

Firewall Policy

        │

Security Profiles

        │

Threat Analysis

        │

Allow or Block

        │

User
```

---

# 🛡 Antivirus (AV)

The Antivirus profile scans files and network traffic for malicious software.

Protects Against:

- Viruses
- Worms
- Trojans
- Ransomware
- Malicious Downloads

---

# 🚨 Intrusion Prevention System (IPS)

IPS detects and blocks known network attacks by inspecting traffic against predefined attack signatures.

Protects Against:

- Exploits
- Vulnerability Attacks
- Network Scanning
- Buffer Overflow Attempts
- Protocol Abuse

---

# 🌐 Web Filter

Web Filtering controls user access to Internet websites.

Typical Controls:

- Category-Based Filtering
- URL Filtering
- Safe Search
- Content Restrictions
- Reputation-Based Blocking

---

# 📱 Application Control

Application Control identifies applications regardless of port or protocol.

Examples:

- Facebook
- WhatsApp
- YouTube
- Zoom
- BitTorrent
- Dropbox

Organizations can allow, monitor, or block applications according to business requirements.

---

# 🌍 DNS Filter

DNS Filtering protects users before they reach malicious websites.

It blocks access to domains associated with:

- Malware
- Phishing
- Botnets
- Command & Control Servers
- Newly Registered Malicious Domains

---

# 📧 AntiSpam

The AntiSpam profile protects enterprise email systems from unwanted or malicious emails.

Capabilities include:

- Spam Detection
- Phishing Protection
- Blacklist Filtering
- Reputation Checks
- Email Security Policies

---

# 🔐 SSL Inspection

Many cyber threats are hidden inside encrypted HTTPS traffic.

SSL Inspection allows FortiGate to inspect encrypted sessions for malicious content before forwarding traffic.

Common Inspection Modes:

- Certificate Inspection
- Deep SSL Inspection

---

# 🔗 Security Profile Integration

Security Profiles are attached to Firewall Policies.

```text
User

↓

Firewall Policy

↓

Security Profiles

↓

Traffic Inspection

↓

Destination
```

Only traffic matching a policy can be inspected.

---

# 🏢 Enterprise Security Layers

```text
Internet

↓

Firewall Policy

↓

Antivirus

↓

IPS

↓

Web Filter

↓

Application Control

↓

DNS Filter

↓

SSL Inspection

↓

Enterprise Users
```

This layered approach improves overall security and reduces the attack surface.

---

# 📊 Enterprise Benefits

Security Profiles provide:

- Threat Detection
- Malware Protection
- Safe Internet Browsing
- Application Visibility
- Data Protection
- Compliance Support
- Centralized Security Enforcement

---

# ⚙ Design Considerations

Before deploying Security Profiles, consider:

- Organization Security Policy
- Performance Requirements
- SSL Inspection Strategy
- User Categories
- Compliance Requirements
- Licensing
- Reporting Needs
- Threat Intelligence Updates

---

# ✅ Best Practices

- Apply Security Profiles to all Internet-facing firewall policies.
- Enable IPS and Antivirus for production environments.
- Use Web Filtering to restrict unsafe websites.
- Monitor applications using Application Control.
- Enable DNS Filtering for phishing protection.
- Use SSL Inspection where organizational policies permit.
- Keep FortiGuard security databases updated.
- Review Security Profile logs regularly.

---

# 📚 Related Documents

- 05-Firewall-Policies.md
- 06-NAT.md
- 12-Authentication.md
- 13-Logging.md
- 14-Debug.md

---

# 📌 Summary

FortiGate Security Profiles provide advanced threat protection beyond traditional firewall policies. By combining Antivirus, IPS, Web Filtering, Application Control, DNS Filtering, AntiSpam, and SSL Inspection, organizations can implement a layered defense strategy that protects users, applications, and data from modern cyber threats.

When integrated with firewall policies and centralized monitoring, Security Profiles become a key component of enterprise network security.

> **Note:** This document introduces the **Low-Level Design** of FortiGate Security Profiles. Detailed configuration of each profile, FortiGuard services, profile tuning, signature updates, SSL certificate deployment, troubleshooting, CLI commands, and real-world attack scenarios will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
17-Best-Practices.md
```

The next document explains FortiGate deployment and operational best practices, including firewall hardening, policy design, administrative security, firmware management, backup strategy, monitoring, logging, high availability, and recommendations for maintaining a secure and reliable enterprise firewall environment.
