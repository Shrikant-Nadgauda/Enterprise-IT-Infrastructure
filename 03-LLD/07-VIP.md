# 🌐 FortiGate Virtual IP (VIP)

> **Document:** `07-Virtual-IP.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Virtual%20IP-red?style=for-the-badge)
![Publishing](https://img.shields.io/badge/Publishing-Server%20Access-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Virtual IP (VIP) |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Destination NAT / Server Publishing |

---

# 📖 Purpose

A Virtual IP (VIP) is a FortiGate object used to publish internal resources to external users by translating a public IP address to a private IP address.

When Internet users access a public IP, the FortiGate firewall performs **Destination NAT (DNAT)** and forwards the traffic to the appropriate internal server based on the configured VIP.

VIPs are commonly used to publish web servers, application servers, mail servers, APIs, and other enterprise services securely.

---

# 🎯 Design Objectives

- Publish Internal Servers
- Hide Private IP Addresses
- Support Destination NAT
- Enable Port Forwarding
- Secure Public Services
- Simplify Server Publishing
- Support Multiple Applications
- Centralize Access Control

---

# 🏗 Enterprise VIP Architecture

```text
                  🌐 Internet
                       │
             Public IP Address
              150.242.201.79
                       │
                       ▼
              ┌────────────────┐
              │   FortiGate    │
              └────────────────┘
                       │
             Destination NAT (VIP)
                       │
                       ▼
               Internal Server
               192.168.1.100
```

---

# 📌 What is a Virtual IP?

A Virtual IP (VIP) is a mapping between a **Public IP Address** and an **Internal Private IP Address**.

Instead of exposing private IP addresses directly, FortiGate listens on the public IP and redirects traffic to the internal server.

---

# 🔄 VIP Processing Flow

```text
Internet Client
        │
        ▼
Public IP Address
        │
        ▼
FortiGate VIP Lookup
        │
        ▼
Destination NAT
        │
        ▼
Firewall Policy Check
        │
        ▼
Internal Server
```

---

# 🌐 VIP Components

A standard VIP contains:

| Component | Description |
|-----------|-------------|
| External IP | Public IP exposed to the Internet |
| Internal IP | Private IP of the destination server |
| External Interface | Interface receiving Internet traffic |
| Port Forwarding | Optional port translation |
| Protocol | TCP / UDP |
| Firewall Policy | Controls access to the server |

---

# 🔹 One-to-One VIP

Maps one public IP directly to one internal server.

Example:

```text
Public IP

150.242.201.79

        │

        ▼

Private Server

192.168.1.100
```

Commonly used for:

- Web Servers
- Mail Servers
- Application Servers

---

# 🔹 Port Forwarding VIP

Only specific ports are forwarded to the internal server.

Example:

```text
Internet

↓

150.242.201.79:443

↓

FortiGate VIP

↓

192.168.1.100:8443
```

Benefits:

- Reduced Attack Surface
- Flexible Port Mapping
- Better Security

---

# 🔹 Multiple VIPs

One firewall can host multiple Virtual IP objects.

Example:

```text
150.242.201.79

↓

Web Server

150.242.201.80

↓

Application Server

150.242.201.81

↓

Mail Server
```

---

# 📊 VIP Traffic Flow

```text
Internet User

        │

HTTPS Request

        │

FortiGate

        │

VIP Match

        │

Firewall Policy

        │

Application Server
```

---

# 🔐 Security Considerations

Publishing a server does **not** automatically make it accessible.

A successful connection requires:

- Valid VIP
- Matching Firewall Policy
- Allowed Service
- Correct Routing
- Healthy Server
- Open Listening Port

Without a firewall policy, the published server remains inaccessible.

---

# 🛡 Enterprise Deployment Example

| Public Service | Public IP | Internal Server |
|---------------|-----------|-----------------|
| Company Website | 150.242.201.79 | 192.168.1.20 |
| HR Portal | 150.242.201.80 | 192.168.1.30 |
| API Server | 150.242.201.81 | 192.168.1.40 |
| Mail Gateway | 150.242.201.82 | 192.168.1.50 |

---

# ⚙ Design Considerations

Before creating a VIP, verify:

- Public IP availability
- Internal server IP
- Required service ports
- Firewall policy
- DNS records
- SSL certificate requirements
- Routing configuration
- Security inspection requirements

---

# ✅ Best Practices

- Publish only required services.
- Use HTTPS instead of HTTP.
- Restrict access with firewall policies.
- Enable logging for published services.
- Apply IPS and Web Application Firewall (WAF) where applicable.
- Use meaningful VIP names.
- Document all VIP mappings.
- Periodically review unused VIPs.

---

# 📚 Related Documents

- 05-Firewall-Policies.md
- 06-NAT.md
- 08-IP-Pools.md
- 09-VPN.md

---

# 📌 Summary

Virtual IP (VIP) is the primary mechanism used by FortiGate to securely publish internal resources to external users through **Destination NAT (DNAT)**. It provides a controlled mapping between public and private IP addresses while relying on firewall policies to authorize access.

A well-designed VIP implementation ensures secure application publishing, simplifies management, and protects internal infrastructure from unnecessary exposure.

> **Note:** This document explains the **Low-Level Design** of Virtual IPs. Detailed VIP creation, port forwarding configuration, one-to-one NAT, load balancing VIPs, CLI commands, packet flow analysis, and troubleshooting will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
08-IP-Pools.md
```

The next document explains FortiGate IP Pools, including source NAT address pools, overload and one-to-one translation, public IP allocation strategies, outbound traffic design, and enterprise best practices for scalable Internet connectivity.
