# Sprint 6: Network Modernization Proposal — Yagé Botanicals

## Overview

Designed and delivered a full network modernization proposal for Yagé Botanicals, a simulated growing business whose existing network infrastructure was outdated, undocumented, and unable to support secure scaling. The proposal covered network architecture redesign, security hardening, and a phased implementation roadmap — translating business requirements into a modern, defensible network.

## Client Profile

| Field | Detail |
|---|---|
| **Client** | Yagé Botanicals (simulated) |
| **Analyst** | Steven Anderson |
| **Completed** | March–April 2025 |
| **Deliverable** | Full Network Modernization Proposal |

## Objectives

- Assess the current network state and identify security and performance gaps
- Design a modernized network architecture aligned with security best practices
- Propose segmentation, access controls, and monitoring improvements
- Deliver a phased implementation plan that minimizes operational disruption
- Provide cost and priority justification for each recommendation

## Current State Assessment

Key issues identified in the existing Yagé Botanicals environment:

- **Flat network topology** — No segmentation between user, server, and guest traffic, creating unrestricted lateral movement risk
- **No firewall or access control policies** — Internal assets exposed to all internal traffic without restriction
- **Unmonitored network** — No logging, SIEM, or IDS/IPS in place to detect threats
- **Outdated hardware and software** — End-of-life devices and operating systems across the environment
- **No documented network diagram or asset inventory** — IT staff operating without visibility into their own infrastructure

## Proposed Architecture

### Network Segmentation Design

| Zone | Purpose | Key Assets |
|---|---|---|
| **Corporate LAN** | Standard employee workstations and productivity systems | User endpoints, printers |
| **Server DMZ** | Internally accessible servers isolated from user traffic | File servers, internal apps |
| **Public DMZ** | Internet-facing services separated from internal network | Web server, email gateway |
| **Guest Network** | Isolated VLAN for visitor and IoT devices | Guest Wi-Fi, smart devices |
| **Management Network** | Restricted zone for network infrastructure administration | Switches, routers, firewalls |

### Security Infrastructure Additions

| Component | Purpose | Priority |
|---|---|---|
| **Next-Gen Firewall (NGFW)** | Enforce zone-based traffic policies and deep packet inspection | Critical |
| **IDS/IPS** | Detect and block malicious traffic patterns | High |
| **SIEM** | Centralized log aggregation and alert correlation | High |
| **VPN** | Secure remote access for staff | High |
| **NAC (Network Access Control)** | Enforce device compliance before granting network access | Medium |
| **CMDB / Network Documentation** | Maintain accurate, current asset and topology records | Medium |

## Phased Implementation Roadmap

### Phase 1 — Foundation (Months 1–2)
- Deploy NGFW and establish zone-based firewall policies
- Implement VLAN segmentation across all identified zones
- Patch and update all EOL systems and firmware

### Phase 2 — Visibility (Months 3–4)
- Deploy IDS/IPS inline on critical segments
- Implement SIEM with log sources from firewall, endpoints, and servers
- Configure alerting baselines and escalation procedures

### Phase 3 — Access Hardening (Months 5–6)
- Roll out VPN for all remote access
- Implement NAC for endpoint compliance enforcement
- Complete network documentation and CMDB

## Skills Demonstrated

- Network architecture design and security zone planning
- Threat-informed infrastructure modernization
- VLAN segmentation and DMZ design
- Security tool selection and justification (NGFW, IDS/IPS, SIEM, VPN, NAC)
- Phased project planning and stakeholder communication
- Risk-based prioritization and cost justification
- Technical proposal writing for business audiences

---
*TripleTen Cybersecurity Program | Sprint 6 | March–April 2025*
