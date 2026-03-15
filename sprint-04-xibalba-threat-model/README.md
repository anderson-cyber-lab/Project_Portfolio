# Sprint 4: Xibalba Interactive — Threat Model Report

## Overview

Developed a comprehensive threat model for Xibalba Interactive, a fictional online gaming company whose player base includes government employees — creating a unique and sensitive threat profile. The report identified threat actors, mapped attack surfaces to MITRE ATT&CK TTPs, and delivered a full solution roadmap covering honeypot strategies, data sources, and preventive mitigations.

## Client Profile

| Field | Detail |
|---|---|
| **Client** | Xibalba Interactive (simulated gaming company) |
| **Analyst** | Steven Anderson |
| **Completed** | February 2025 |
| **Key Risk Factor** | Player base includes government employees, attracting Nation State Actors |

## Threat Actors Identified

### 1. Cybercriminals
Motivated by financial gain through theft or ransoming of intellectual property (IP) and client payment information.

**Key Scenarios:**
- **IP Theft** — Phishing-led compromise of trusted accounts to exfiltrate game source code via C2 channels
  - TTPs: T1566, T1505, T1020, T1078, T1133
- **Payment Info Theft** — Credential theft via phishing to access payment processing servers
  - TTPs: T1566, T1078, T1657, T1189, T1190

### 2. Insider Threats
Disgruntled employees seeking to disrupt or destroy company property via access or credential abuse.

**Key Scenarios:**
- Code injection or data destruction via compromised internal accounts
  - TTPs: T1566, T1189, T1505, T1659, T1040

### 3. Nation State Actors
Motivated by political intelligence gathering through infiltration of in-game communications between government-employee players.

**Key Scenarios:**
- Espionage via impersonation of trusted players in chat systems
  - TTPs: T1589, T1656, T1078

## Attack Surface Analysis

| Attack Surface | Key Assets | Likelihood | Impact |
|---|---|---|---|
| Development Server | Intellectual Property (IP) | Possible (3) | Catastrophic (5) |
| Company Network | Intellectual Property (IP) | Possible (3) | Major (4) |
| Source Code | Intellectual Property (IP) | Possible (3) | Major (4) |
| Staff | Intellectual Property (IP) | Possible (3) | Catastrophic (5) |
| Payment Processing Server | Client payment data | Possible (3) | Catastrophic (5) |
| In-game Communication Client | Private player chat | Possible (3) | Moderate (3) |

## Solution Roadmap

### 🍯 Honeypot Strategies

| Solution | Type | Difficulty | Priority |
|---|---|---|---|
| Honeycreds | Decoy admin credentials | Easy | High |
| Honeydata | Fake IP/financial files | Easy | High |
| Honeymail | Decoy C-class email account | Easy | Medium |
| HoneyNet | Decoy network segment | Hard | Medium |
| Honeyservices | Decoy file server | Medium | Medium |

### 📊 Data Sources for Detection

| Data Source | MITRE DS ID | Priority |
|---|---|---|
| Network Traffic Content | DS0029 | High |
| Logon Session Metadata | DS0028 | High |
| File Creation | DS0022 | Low |
| Application Log Content | DS0015 | High |
| Command Execution | DS0017 | Medium |

### 🔮 Preventive Mitigations

| Mitigation | MITRE ID | Priority | Timeline |
|---|---|---|---|
| Multi-Factor Authentication | M1032 | High | 1 month (MFA), 6 months (biometrics) |
| User Security Training | M1017 | High | 3 months initial, bi-monthly testing |
| Encrypt Sensitive Information | M1041 | High | 3 months |

## Tools & Frameworks

| Tool / Framework | Purpose |
|---|---|
| **MITRE ATT&CK** | TTP identification and mapping |
| **MITRE D3FEND** | Defensive countermeasure reference |
| **Honeypot Methodology** | Deception-based threat detection strategies |
| **SIEM** | Alert creation and monitoring for all data sources |

## Skills Demonstrated

- Threat modeling and adversary profiling
- MITRE ATT&CK TTP mapping (offense and defense)
- Attack surface analysis with likelihood and impact scoring
- Honeypot strategy design (creds, data, mail, net, services)
- Defensive data source selection and SIEM alert planning
- Security roadmap development with stakeholder-aligned goals
- Executive-level report writing

---
*TripleTen Cybersecurity Program | Sprint 4 | February 2025*
