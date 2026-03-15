# Sprint 12: Incident Response — WordPress Brute Force Attack

## Overview

Investigated a high-severity security incident involving a brute-force attack against a WordPress server. Using PCAP analysis and SIEM log correlation, identified the attacker's methods, timeline, and the full scope of credential compromise. Produced a formal IR Triage Report with disposition, impact analysis, and remediation recommendations.

## Incident Details

| Field | Value |
|---|---|
| **Alert ID** | ZgUGhV1CEwAABx43AYAAAAAB |
| **Source** | ModSecurity |
| **Severity** | HIGH |
| **Disposition** | True Positive (TP) |
| **Analyst** | Steven Anderson |
| **Date** | July 29, 2025 |

## Incident Summary

A ModSecurity alert flagged repeated authentication attempts against a WordPress server at `192.168.100.2` originating from `192.168.100.20`. Over a 6-minute window, the attacker successfully authenticated using the **Hydra** brute-force tool, obtaining both user-level and admin-level credentials.

### Attack Timeline

| Time (UTC) | Event |
|---|---|
| 2025-04-10 15:42:22 | Attack begins — brute force initiated against `/wp-login.php` |
| 2025-04-10 15:42:28 | Attacker authenticates as user `elliot` (user-level access) |
| 2025-04-10 15:42:37–56 | Repeated authentications as `elliot` across multiple ports |
| 2025-04-10 15:48:41 | Attacker successfully authenticates as `admin` (admin-level access) |

### Indicators of Compromise

- **Attacker IP:** `192.168.100.20`
- **Target:** Apache/WordPress at `192.168.100.2` — `wp-login.php`
- **User-Agent:** `Mozilla/5.0 (Hydra)` — known brute-force tool signature
- **Compromised Credentials:** `elliot` (user), `admin` (administrator)

## MITRE ATT&CK Mapping

| Technique | ID | Description |
|---|---|---|
| Brute Force: Password Guessing | T1110.001 | Repeated credential stuffing against `/wp-admin` |

## Recommendations

- Suspend compromised user accounts (`elliot`, `admin`) immediately and force credential resets
- Escalate to L2 for deeper investigation of post-authentication activity
- Implement account lockout and rate-limiting on login endpoints
- Enforce MFA on all WordPress admin accounts
- Update firewall rules to restrict the server to essential port ranges only
- Create SIEM detection rules correlating failed-to-successful login ratios within a 10-minute window
- Add `Mozilla/5.0 (Hydra)` to known malicious user-agent blocklists

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Wireshark / PCAP Analysis** | Packet capture investigation |
| **Wazuh SIEM** | Log correlation and alert triage |
| **ModSecurity** | WAF alert source |
| **MITRE ATT&CK** | TTP classification |

## Skills Demonstrated

- Incident response triage and investigation
- PCAP and log analysis
- SIEM alert correlation
- MITRE ATT&CK TTP mapping
- Formal IR report writing with disposition and recommendations

---
*TripleTen Cybersecurity Program | Sprint 12 | July 2025*
