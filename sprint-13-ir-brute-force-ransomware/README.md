# Sprint 13: Incident Response — Brute Force & Ransomware Infection

## Overview

Investigated a critical, multi-stage security incident involving a successful brute-force attack followed by a ransomware deployment across a corporate network. Using SIEM log analysis and log correlation techniques, reconstructed the full attack chain spanning 15 days. Produced a formal IR Triage Report with a detailed timeline, MITRE TTP mapping, and escalation recommendations.

## Incident Details

| Field | Value |
|---|---|
| **Alert ID** | UR-INT-20250603-0047 |
| **Source** | User Reported |
| **Severity** | CRITICAL |
| **Disposition** | True Positive (TP) |
| **Analyst** | Steven Anderson |
| **Date** | August 9, 2025 |

## Incident Summary

A user-reported alert revealed a two-phase attack beginning with a brute-force campaign against a web server and culminating in a network-wide ransomware infection 14 days later. Admin credentials were compromised in phase one, enabling lateral movement and ultimately the execution of **Cerber ransomware** on a file server and user endpoint.

### Attack Timeline

| Time (UTC) | Event |
|---|---|
| 2016-08-10 21:45:10 | Brute-force campaign begins — 412 login attempts from `23.22.63.114` |
| 2016-08-10 21:46:25 | Admin password successfully guessed |
| 2016-08-10 21:48:04 | Attacker logs in from `40.80.148.42` using stolen credentials |
| 2016-08-10 21:52:45 | Malicious file `3791.exe` uploaded and executed on server `192.168.250.70`, pivoting to `192.168.250.100` |
| 2016-08-10 22:06:21 | Defacement image pulled from external C2 domain |
| 2016-08-24 16:48:12 | Host at `192.168.250.100` visits known malicious domain `solidaritedeproximite.org` |
| 2016-08-24 16:48:21 | VBS script hidden in `121214.tmp` executes Cerber ransomware |
| 2016-08-24 17:15:12 | Host queries Cerber C2 domain; ransom note VBS executed |

### Indicators of Compromise

- **Attacker IPs:** `23.22.63.114`, `40.80.148.42`
- **Malicious File:** `3791.exe`
- **Malicious Domains:** `solidaritedeproximite.org`, `cerberhhyed5frqa.xmfir0.win`, `prankglassinebracket.jumpingcrab.com`
- **User-Agent (Brute Force):** `Python-urllib/2.7`
- **Ransomware:** Cerber

## MITRE ATT&CK Mapping

| Technique | ID |
|---|---|
| Brute Force: Password Guessing | T1110.001 |
| Command and Scripting Interpreter | T1059 |
| Lateral Movement (implicit) | — |

## Recommendations

- Immediately escalate to highest-level IR team and take the network offline
- Scrub all compromised hosts (`192.168.250.70`, `192.168.250.100`, `192.168.250.20`) of malicious processes
- Blacklist all identified malicious IPs and domains at the firewall and DNS level
- Implement EDR, IDS, and SIEM detections against Cerber ransomware hashes and behavioral patterns
- Enforce stronger authentication and MFA to prevent credential-based initial access

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Wazuh SIEM** | Log correlation and alert investigation |
| **Splunk** | Log search and timeline reconstruction |
| **MITRE ATT&CK** | TTP mapping |
| **Threat Intelligence** | Malicious domain and IP lookup |

## Skills Demonstrated

- Multi-stage attack chain reconstruction
- Critical incident triage and escalation
- SIEM log correlation across a 15-day event window
- MITRE ATT&CK TTP mapping
- Ransomware incident response
- Formal IR report writing

---
*TripleTen Cybersecurity Program | Sprint 13 | August 2025*
