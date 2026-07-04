# 🛡 02 - How Firewall Works

> **FortiGate Infrastructure Deep Dive Series**

---

# 📖 Introduction

In the previous chapter, we learned **what a Firewall is** and why every enterprise network requires one.

Now the next question naturally arises:

> **How does a Firewall actually work?**

When a user opens a website, accesses an application, downloads a file, or connects to a server, thousands of network packets travel through the network. The Firewall sits between different networks and examines every packet before deciding whether it should be allowed or blocked.

A Firewall is therefore not just a device that blocks traffic—it is an intelligent security system that inspects, analyzes, and controls network communication based on predefined security policies.

---

# 🌍 Enterprise Example

Consider a typical enterprise network.

```text
                Internet
                    │
                    │
            Public IP Address
                    │
            +------------------+
            |    FortiGate     |
            |     Firewall     |
            +------------------+
              │            │
              │            │
        Internal LAN      DMZ
              │            │
        Employee PCs   Web Server
```

Every packet entering or leaving the organization must first pass through the FortiGate Firewall.

The firewall becomes the central decision point for all network communication.

---

# 🚀 What Happens When Traffic Arrives?

Whenever a packet reaches the firewall, it goes through a series of checks before a decision is made.

At a high level, the process looks like this:

```text
Packet Arrives
        │
        ▼
Interface Detection
        │
        ▼
Route Lookup
        │
        ▼
Firewall Policy Check
        │
        ▼
Security Inspection
        │
        ▼
NAT Processing (if required)
        │
        ▼
Allow or Deny
        │
        ▼
Forward Packet
```

Each stage has a specific purpose and helps ensure that only legitimate traffic is allowed to pass.

---

# 📦 Step 1 — Packet Arrival

The first thing that happens is that a network packet reaches one of the firewall interfaces.

Examples include:

- Internet traffic arriving on the WAN interface
- User traffic arriving from the LAN
- VPN traffic arriving through an IPSec tunnel
- SSL VPN user connections
- Traffic from another VLAN

The firewall first identifies **where the packet came from**.

---

# 🔎 Step 2 — Interface Identification

Every packet enters through an interface.

For example:

```text
Internet
    │
    ▼
WAN1 Interface
```

or

```text
Employee PC
      │
      ▼
LAN Interface
```

Knowing the incoming interface helps the firewall understand the source network.

---

# 🧭 Step 3 — Route Lookup

After identifying the incoming interface, the firewall determines where the packet should go.

It consults its routing table to find the best path to the destination network.

Example:

```text
Destination:
172.16.10.50

↓

Routing Table

↓

Send via Internal Network
```

Without a valid route, the packet cannot be forwarded.

---

# 📜 Step 4 — Firewall Policy Evaluation

Once the destination path is known, FortiGate checks its firewall policies.

The firewall compares the packet against configured rules.

Typical checks include:

- Source Interface
- Destination Interface
- Source Address
- Destination Address
- Service or Port
- Schedule
- User or User Group (if applicable)

If a matching policy is found and it permits the traffic, processing continues.

If no matching policy exists, the traffic is denied by the **Implicit Deny** rule.

---

# 🛡 Step 5 — Security Inspection

Before forwarding the packet, FortiGate can inspect it using various security services.

Examples include:

- Antivirus
- Intrusion Prevention System (IPS)
- Web Filtering
- Application Control
- DNS Filtering
- SSL Inspection

These features help detect and block malicious or unauthorized traffic.

---

# 🌐 Step 6 — NAT Processing

If Network Address Translation (NAT) is configured, the firewall performs address translation.

Examples include:

- Source NAT (SNAT) for outbound Internet access
- Destination NAT (DNAT/VIP) for publishing internal servers
- IP Pool translation for outbound traffic

NAT allows private and public networks to communicate securely.

---

# ✅ Step 7 — Allow or Deny

After completing all required checks, the firewall makes a final decision.

```text
Policy Matched
        │
        ▼
Security Inspection Passed
        │
        ▼
Traffic Allowed
```

or

```text
No Matching Policy
        │
        ▼
Traffic Blocked
```

This decision is enforced immediately for every new connection.

---

# 🔄 Stateful Inspection

Modern FortiGate firewalls use **Stateful Inspection**.

Instead of evaluating every packet independently, FortiGate tracks the state of each connection in a session table.

For example:

```text
Client
   │
Request
   │
Firewall
   │
Session Created
   │
Server
   │
Response
   │
Firewall
   │
Session Verified
   │
Client
```

This improves both security and performance because return traffic belonging to an existing session does not require a full policy evaluation again.

---

# 🏢 Real Enterprise Scenario

An employee opens Microsoft Outlook.

The sequence is:

1. Outlook generates network traffic.
2. Traffic reaches the FortiGate firewall.
3. The firewall identifies the incoming interface.
4. It checks the routing table.
5. It evaluates firewall policies.
6. Security profiles inspect the traffic.
7. Source NAT translates the private IP to a public IP.
8. The traffic is forwarded to Microsoft 365.
9. The response returns through the existing session.

All of this happens in milliseconds.

---

# 📌 Key Takeaways

- Every packet passes through the firewall before reaching its destination.
- The firewall follows a structured decision-making process.
- Routing determines where traffic should go.
- Firewall policies determine whether traffic is permitted.
- Security profiles inspect traffic for threats.
- NAT translates addresses when required.
- Stateful inspection keeps track of active sessions for efficient and secure communication.

---

# 📚 What's Next?

Now that you understand how a firewall processes traffic at a high level, the next step is to see **how a packet actually travels through a FortiGate Firewall internally**.

In the next chapter, we will follow a packet from the moment it enters an interface until it exits the firewall, examining every stage of FortiGate's packet processing engine.

---

# 📌 Continue Learning

```text
03-Packet-Flow.md
```

> The next document explains the complete FortiGate packet flow, including packet reception, session creation, route lookup, policy matching, NAT processing, security inspection, forwarding, and return traffic handling inside the FortiGate operating system.