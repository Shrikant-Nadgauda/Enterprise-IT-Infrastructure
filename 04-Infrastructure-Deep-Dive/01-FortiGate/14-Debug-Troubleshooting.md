# 🛠 FortiGate Debug

> **Document:** `14-Debug.md`

![FortiGate](https://img.shields.io/badge/FortiGate-Debug-red?style=for-the-badge)
![Troubleshooting](https://img.shields.io/badge/Troubleshooting-Diagnostics-blue?style=for-the-badge)
![LLD](https://img.shields.io/badge/Documentation-LLD-green?style=for-the-badge)

---

# 📋 Document Information

| Item | Details |
|------|---------|
| Document Name | FortiGate Debug |
| Document Type | Low-Level Design (LLD) |
| Technology | FortiGate Firewall |
| Category | Diagnostics & Troubleshooting |

---

# 📖 Purpose

Debugging is the process of identifying, analyzing, and resolving network, security, routing, VPN, and system issues within the FortiGate firewall.

FortiGate provides a comprehensive set of diagnostic tools that allow administrators to observe packet processing, routing decisions, policy matching, VPN negotiations, interface status, and system health. These tools help quickly isolate problems and reduce downtime in enterprise environments.

---

# 🎯 Design Objectives

- Diagnose Network Issues
- Verify Packet Flow
- Troubleshoot VPN Connectivity
- Validate Routing Decisions
- Analyze Firewall Policies
- Monitor Sessions
- Improve Incident Response
- Reduce Service Downtime

---

# 🏗 Enterprise Debug Architecture

```text
             👤 User / Server

                    │

               Connectivity Issue

                    │

                    ▼

            🛡 FortiGate Firewall

                    │

        ┌───────────┼────────────┐
        ▼           ▼            ▼

   Debug Flow   Packet Capture  Logs

        │           │            │
        └───────────┼────────────┘
                    │

            Problem Identification

                    │

              Issue Resolution
```

---

# 📌 What is Debugging?

Debugging is the process of examining how the firewall processes traffic and system events to determine why a particular service, application, or connection is not functioning as expected.

Unlike logs, debugging provides real-time operational information during packet processing and protocol negotiations.

---

# 🔍 Common Troubleshooting Areas

FortiGate debugging is commonly used for:

- Traffic Flow Issues
- Firewall Policy Matching
- NAT Translation
- Routing Problems
- IPSec VPN Failures
- SSL VPN Connectivity
- DNS Resolution
- Authentication Failures
- Session Problems
- Performance Analysis

---

# 🛠 Diagnostic Components

| Component | Purpose |
|-----------|---------|
| Debug Flow | Analyze packet processing |
| Packet Capture | Inspect network packets |
| Session Table | Verify active sessions |
| Routing Table | Validate route selection |
| VPN Diagnostics | Check tunnel status |
| Interface Status | Monitor interface health |
| System Logs | Review operational events |

---

# 🔄 Enterprise Troubleshooting Flow

```text
Issue Reported

        │

Verify Connectivity

        │

Check Logs

        │

Analyze Debug Output

        │

Identify Root Cause

        │

Implement Fix

        │

Verify Resolution
```

---

# 🌐 Packet Flow Analysis

Debug Flow helps administrators understand how FortiGate processes packets.

Typical verification includes:

- Packet Arrival
- Route Lookup
- Firewall Policy Match
- NAT Processing
- Security Inspection
- Session Creation
- Packet Forwarding

This provides visibility into the complete packet journey.

---

# 📦 Packet Capture

Packet capture allows administrators to inspect network packets entering or leaving the firewall.

Common uses include:

- Protocol Verification
- DNS Analysis
- TCP Handshake Validation
- Application Troubleshooting
- VPN Traffic Analysis
- Connectivity Testing

---

# 🔄 Session Inspection

FortiGate maintains a session table for all active connections.

Session inspection helps verify:

- Active Sessions
- Session State
- Source and Destination
- NAT Translation
- Session Timeouts
- Traffic Counters

---

# 🛣 Routing Diagnostics

Routing diagnostics confirm how traffic is forwarded.

Administrators typically verify:

- Default Route
- Static Routes
- Dynamic Routes
- Route Priority
- Next Hop
- Interface Selection

---

# 🔐 VPN Troubleshooting

VPN diagnostics help identify tunnel issues.

Typical verification areas include:

- Tunnel Status
- Phase 1 Negotiation
- Phase 2 Negotiation
- Authentication
- Encryption Parameters
- Routing
- Traffic Selectors

---

# 📊 System Health Monitoring

System diagnostics provide visibility into firewall resources.

Common monitoring includes:

- CPU Usage
- Memory Utilization
- Disk Usage
- Interface Status
- Session Count
- Hardware Health

---

# ⚙ Design Considerations

Before performing debugging, consider:

- Enable Debug Only When Required
- Limit Debug Scope
- Monitor Resource Utilization
- Verify System Time
- Collect Relevant Logs
- Document Findings
- Disable Debug After Testing

---

# ✅ Best Practices

- Start with logs before enabling debug.
- Narrow the scope to affected traffic only.
- Verify routing before investigating policies.
- Check VPN status before analyzing encryption.
- Capture packets when application issues occur.
- Save debug output for future analysis.
- Disable debugging after troubleshooting is complete.
- Document root cause and corrective actions.

---

# 📚 Related Documents

- 04-Routing.md
- 05-Firewall-Policies.md
- 06-NAT.md
- 09-VPN.md
- 10-SSL-VPN.md
- 11-IPSec-VPN.md
- 13-Logging.md

---

# 📌 Summary

FortiGate debugging provides administrators with real-time visibility into packet processing, routing decisions, VPN negotiations, session management, and system operations. Combined with logs and monitoring tools, debugging enables rapid identification and resolution of network and security issues while minimizing service disruption.

A structured troubleshooting methodology improves operational efficiency, reduces downtime, and ensures reliable enterprise network performance.

> **Note:** This document introduces the **Low-Level Design** of FortiGate Debugging. Detailed CLI debug commands, `diagnose debug flow`, packet capture techniques, session table analysis, VPN debugging, routing diagnostics, log interpretation, and real-world troubleshooting scenarios will be covered extensively in the **Infrastructure Deep Dive** section.

---
 Next Document

```text
15-High-Availability.md
```

The next document explains FortiGate High Availability (HA) architecture, including HA modes, cluster formation, heartbeat communication, session synchronization, failover process, redundancy design, and enterprise best practices for ensuring continuous network availability.
