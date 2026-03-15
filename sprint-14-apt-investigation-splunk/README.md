# Sprint 14: APT Investigation — Multi-Domain Threat Hunting with Splunk

## Overview

Conducted an advanced threat hunting and APT investigation across a simulated enterprise environment (Frothly Brewing Company) using Splunk. This was a multi-phase, multi-domain investigation spanning AWS cloud infrastructure, Windows and Linux endpoints, Office 365, and network flow data. Each phase required pivoting across diverse log sources to reconstruct complex attack chains.

## Objectives

- Identify and investigate malicious activity across AWS CloudTrail, S3, endpoint, and network logs
- Detect and scope cryptocurrency mining activity on corporate endpoints
- Investigate leaked AWS key pairs and unauthorized cloud resource provisioning
- Trace a compromised endpoint through privilege escalation, persistence, and lateral movement
- Investigate a phishing campaign culminating in a domain admin compromise
- Perform deep file investigation to uncover C2 infrastructure and attacker tooling

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Splunk** | Primary SIEM for all log search, correlation, and analysis |
| **AWS CloudTrail** | IAM, S3, and EC2 event logging |
| **Sysinternals Sysmon** | Windows endpoint process and network monitoring |
| **Osquery** | Linux endpoint process, file, and network telemetry |
| **Microsoft Azure AD / O365** | Identity and email log analysis |
| **Cisco NVM Flow Data** | Network flow duration analysis |
| **Symantec Endpoint Protection** | Malware detection and blocking logs |
| **CyberChef** | Base64 decoding and artifact analysis |
| **OSINT** | CVE lookups, IP geolocation, malware intelligence |

---

## Investigation Phases

### Phase 1 — AWS IAM & S3 Breach
- Identified four IAM users with CloudTrail access: `bstoll`, `btun`, `splunk_access`, `web_admin`
- Detected an S3 bucket (`frothlywebcode`) made publicly accessible via `PutBucketAcl` by user `bstoll`, exposed for 56 minutes
- Discovered a plaintext file (`OPEN_BUCKET_PLEASE_FIX.txt`) and a 2.93 MB archive (`frothly_html_memcached.tar.gz`) uploaded during the exposure window

### Phase 2 — Cryptocurrency Mining
- Identified host `BSTOLL-L` making repeated DNS queries to `coinhive.com` and subdomains using Microsoft Edge and Chrome processes pegged at 100% CPU
- Confirmed 6 unique cryptocurrency mining domains contacted across the environment
- Found host `BTUN-L` as the endpoint that successfully blocked the coin miner via Symantec EP (46 blocked events)
- Measured cryptomining session duration at **1,667 seconds** via Cisco NVM flow log analysis

### Phase 3 — Leaked AWS Keys
- Identified the AWS access key with the highest failure rate via CloudTrail IAM logs
- Correlated SMTP logs to find AWS security notification email (Support Case `5244329601`) sent to `bstoll@froth.ly`
- Traced unauthorized use of the leaked key to the tool **ElasticWolf/5.1.6**
- Determined the attacker launched an Ubuntu EC2 instance using the compromised key

### Phase 4 — Compromised Endpoint
- Traced a successful login using an expired Azure AD account (`kevin.lagerfield@froth.ly`) from IP `199.66.91.253`
- Identified malicious file upload via OneDrive using a suspicious user agent string
- Found a new backdoor user (`svcvnc`) created post-compromise with the password `ilovedavidverve`, added to both `Administrators` and `Users` groups
- Identified a process listening on elite port `1337` with PID `14356` on Linux host `hoth`
- Discovered domain admin's endpoint (`FYODOR-L`) compromised with `hdoor.exe` uploaded as first malicious executable

### Phase 5 — Phishing & Domain Admin Compromise
- Traced a phishing campaign delivering a malicious Excel macro file (`W97M.Empstage`)
- Confirmed 7 unique endpoints clicked the anonymous phishing link via O365 logs
- Found the attacker downloaded tools via port `3333` using a PowerShell-based HTTP client disguised as a browser
- Decoded a base64-obfuscated PowerShell payload revealing the C2 server at `https://45.77.53.176:443/admin/get.php`
- Identified Linux privilege escalation via a Ubuntu 16.04 BPF kernel exploit (CVE reference) executed through Tomcat
- Traced attacker-created BCC transport rule in Exchange forwarding mail to an adversarial address

### Phase 6 — Files, Files, Files
- Confirmed C2 server URI (`/admin/get.php`) via PowerShell event logs
- Identified the attacker's IP as originating from **Moscow, Russia** via Linux secure log geolocation
- Traced a suspicious file (`logos.png`) used as a malicious payload download container via HTTP on port 3333

---

## Skills Demonstrated

- Advanced Splunk SPL query writing including `rex`, `eval`, `stats`, `lookup`, `spath`, and `join`
- Multi-source log correlation (CloudTrail, Sysmon, Osquery, O365, SMTP, DNS, network flow)
- AWS cloud security investigation (IAM, S3, EC2, CloudWatch)
- Endpoint forensics (Windows and Linux)
- Cryptomining detection and scoping
- Phishing and macro malware investigation
- Privilege escalation and persistence analysis
- C2 infrastructure identification and decoding
- OSINT for malware classification, CVE lookup, and IP attribution
- Professional investigation documentation and note-taking

---
*TripleTen Cybersecurity Program | Sprint 14 | August–September 2025*
