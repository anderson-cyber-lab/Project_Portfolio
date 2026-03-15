# Sprint 11: SIEM Deployment & Purple Team Testing

## Overview

Designed and implemented enhancements to an existing Wazuh SIEM deployment, then conducted purple team testing using the Atomic Red Team (ART) framework to validate detection coverage. This project combined blue team configuration work with red team simulation to measure and improve the environment's logging and alerting effectiveness.

## Objectives

- Expand Wazuh SIEM log ingestion to cover all available log sources from the observer server
- Install and configure Atomic Red Team on the observer workstation for adversary simulation
- Execute ART tests mapped to MITRE ATT&CK techniques to evaluate detection capability
- Document results and identify gaps in current logging and detection coverage

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Wazuh SIEM** | Security event correlation and alerting |
| **Atomic Red Team (Invoke-AtomicRedTeam)** | Adversary simulation framework |
| **ossec.conf** | Wazuh agent configuration |
| **Apache / ModSecurity** | Log sources integrated into SIEM |
| **MITRE ATT&CK** | TTP framework for test selection |
| **CloudShare** | Lab environment |

## SIEM Modifications

### Modification 1 — Expanded Apache Log Forwarding
Configured `ossec.conf` to forward two previously missing log sources from the observer server to Wazuh:
- `modsec_audit.log`
- `other_vhosts_access.log`

**Objective:** Increase visibility into remote access attempts and WAF activity.

### Modification 2 — Atomic Red Team Installation
Installed `Invoke-AtomicRedTeam` on the observer workstation to enable repeatable, MITRE-mapped adversary simulations.

## Purple Team Experiments

| # | MITRE TTP | Technique | Objective |
|---|---|---|---|
| 1 | T1071.001 | Application Layer Protocol: Web Protocols | Test SIEM detection of C2-style HTTP traffic blending into normal web traffic |
| 2 | T1563.002 | RDP Session Hijacking | Validate logging of remote session hijack activity in access logs |
| 3 | T1014 | Rootkit | Assess whether SIEM can detect rootkit deployment attempts |

## Key Outcomes

- Successfully expanded SIEM visibility to all 4 available log sources from the observer server
- Executed three ART tests and evaluated corresponding log activity in Wazuh
- Identified detection gaps and log coverage blind spots for future tuning
- Demonstrated end-to-end purple team workflow: configure → simulate → detect → improve

## Skills Demonstrated

- SIEM configuration and log source integration (Wazuh)
- Purple team methodology (red + blue team combined)
- Adversary simulation using Atomic Red Team
- MITRE ATT&CK technique mapping
- Detection engineering and gap analysis

---
*TripleTen Cybersecurity Program | Sprint 11 | June 2025*
