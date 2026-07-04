# ⚙️ FortiGate High Availability (HA)

> **Document:** `15-High-Availability.md`

![FortiGate](https://img.shields.io/badge/FortiGate-High%20Availability-red?style=for-the-badge)
![HA](https://img.shields.io/badge/High%20Availability-Failover-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate High Availability |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Redundancy & Business Continuity |

---

# 📖 Purpose

High Availability (HA) ensures that the enterprise firewall infrastructure remains operational even if a firewall device experiences a hardware failure, software issue, or planned maintenance.

FortiGate HA combines multiple firewalls into a single logical cluster, allowing services to continue with minimal interruption through automatic failover.

---

# 🎯 Design Objectives

- Eliminate Single Point of Failure
- Ensure Business Continuity
- Minimize Downtime
- Automatic Failover
- Session Continuity
- Configuration Synchronization
- High Network Availability
- Simplified Management

---

# 🏗 Enterprise HA Architecture

```text
                     🌐 Internet
                          │
                          │
                ┌─────────┴─────────┐
                │                   │

        🛡 FortiGate A        🛡 FortiGate B
          (Primary)            (Secondary)

                ═════ Heartbeat ═════

                │                   │
                └─────────┬─────────┘
                          │
                    Core L3 Switch
                          │
                 Enterprise Network
```

---

# 📌 What is High Availability?

High Availability (HA) is a redundancy mechanism where two or more FortiGate firewalls operate together as a cluster.

If the primary firewall becomes unavailable, the secondary firewall automatically takes over network traffic, reducing service interruption.

---

# 🌍 Why HA is Important?

Enterprise networks require continuous availability for critical services such as:

- Internet Access
- VPN Connectivity
- Business Applications
- Email Services
- Cloud Connectivity
- Remote Access
- Branch Connectivity

Without HA, a firewall failure can interrupt all network communication.

---

# 🔄 HA Operation Flow

```text
Normal Operation

        │

Primary Firewall Active

        │

Heartbeat Monitoring

        │

Primary Failure

        │

Automatic Failover

        │

Secondary Firewall Active
```

---

# 🔧 HA Components

| Component | Purpose |
|-----------|---------|
| Primary Firewall | Processes production traffic |
| Secondary Firewall | Standby or load-sharing member |
| Heartbeat Interface | Monitors cluster health |
| Configuration Sync | Synchronizes configuration |
| Session Sync | Maintains active sessions |
| Cluster ID | Identifies HA members |

---

# 🔹 HA Modes

FortiGate supports multiple HA deployment modes.

### Active-Passive

- One firewall actively processes traffic.
- Secondary firewall remains on standby.
- Automatic failover occurs if the primary fails.

---

### Active-Active

- Multiple firewalls process traffic simultaneously.
- Traffic is distributed across cluster members.
- Suitable for high-performance environments.

---

# ❤️ Heartbeat Communication

HA members continuously exchange heartbeat messages.

Heartbeat communication verifies:

- Device Health
- Link Status
- Cluster Membership
- Synchronization Status

Loss of heartbeat triggers the failover process.

---

# 🔄 Configuration Synchronization

Configuration changes made on the primary firewall are automatically synchronized to the secondary firewall.

Synchronized items typically include:

- Firewall Policies
- Address Objects
- Routing Configuration
- VPN Configuration
- Security Profiles
- User Configuration

---

# 🔁 Session Synchronization

Session synchronization allows existing network sessions to remain active during failover.

Examples include:

- Web Browsing
- VPN Sessions
- File Transfers
- Application Connections

This minimizes disruption for end users.

---

# 🌐 Enterprise Traffic Flow

```text
Internet

↓

Primary FortiGate

↓

Firewall Inspection

↓

LAN

↓

Users

↓

(Primary Failure)

↓

Secondary FortiGate

↓

Traffic Continues
```

---

# 📊 Failover Process

During failover, FortiGate performs the following actions:

1. Detect Primary Failure
2. Promote Secondary Firewall
3. Assume Virtual MAC/IP
4. Continue Traffic Processing
5. Synchronize Cluster Status

The transition is automatic and designed to minimize downtime.

---

# 🛡 Design Considerations

Before deploying HA, consider:

- Number of Cluster Members
- Dedicated Heartbeat Interfaces
- Identical Hardware Models
- Firmware Version Consistency
- Session Synchronization
- Redundant ISP Connections
- Network Topology
- Monitoring Requirements

---

# ⚙ Enterprise Use Cases

HA is commonly deployed for:

- Datacenters
- Head Offices
- Internet Edge Firewalls
- VPN Gateways
- Cloud Connectivity
- Critical Business Networks

---

# ✅ Best Practices

- Use identical FortiGate models.
- Keep firmware versions consistent.
- Configure dedicated heartbeat interfaces.
- Enable session synchronization.
- Test failover regularly.
- Monitor HA status continuously.
- Backup configurations before upgrades.
- Document HA topology and recovery procedures.

---

# 📚 Related Documents

- 04-Routing.md
- 05-Firewall-Policies.md
- 09-VPN.md
- 11-IPSec-VPN.md
- 13-Logging.md
- 14-Debug.md

---

# 📌 Summary

FortiGate High Availability provides redundancy and resilience by combining multiple firewalls into a single logical cluster. Through heartbeat communication, configuration synchronization, session synchronization, and automatic failover, HA minimizes downtime and ensures continuous access to enterprise services.

A properly designed HA deployment strengthens business continuity and is a key requirement for mission-critical enterprise environments.

> **Note:** This document introduces the **Low-Level Design** of FortiGate High Availability. Detailed HA configuration, Active-Passive vs Active-Active deployment, heartbeat interfaces, failover testing, session pickup, firmware upgrades, split-brain prevention, CLI commands, and troubleshooting will be covered in the **Infrastructure Deep Dive** section.

---

📌 Next Document

```text
16-Security-Profiles.md
```

The next document explains FortiGate Security Profiles, including Antivirus, IPS, Web Filtering, Application Control, DNS Filtering, AntiSpam, SSL Inspection, profile attachment to firewall policies, and enterprise best practices for layered threat protection.
