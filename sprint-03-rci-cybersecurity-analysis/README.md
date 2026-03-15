# Sprint 3: RCI Cybersecurity Analysis Report

## Overview

Conducted a Root Cause Investigation (RCI) and delivered a cybersecurity advisory report on behalf of 0x2A Security for a client that had recently suffered a significant security breach. The incident originated with a phishing email that cascaded into data exfiltration, ransomware exposure, and severe operational disruption. The report identified systemic failures and provided five prioritized recommendations to prevent recurrence.

## Engagement Details

| Field | Detail |
|---|---|
| **Client** | Undisclosed (simulated) |
| **Performed by** | Steven Anderson, 0x2A Security |
| **Report Date** | January 13, 2025 |
| **Report Type** | Root Cause Investigation & Advisory |

## Executive Summary

The investigation revealed that the breach originated from a phishing email opened by an untrained staff member — a preventable event that triggered a chain of downstream compromises. Key systemic failures included a complete absence of formal security training, no backup procedures, unencrypted data at rest and in transit, a non-functional incident response plan, and dangerously poor infrastructure documentation. The organization's IT staff were unaware of the full scope of their own network, including the criticality of the server that was ultimately compromised.

## Five Key Recommendations

### 1. Employee Security Training — Priority: Critical
The breach began with a phishing email that a trained employee would have recognized as suspicious. Implement mandatory security awareness training for all staff, with regular testing intervals. The human element is consistently the weakest link — this is the highest-impact, lowest-cost fix available.

### 2. Data Redundancy & Backup Procedures — Priority: High
The attacked server had no current backup, preventing operational continuity during the ransomware incident. Establish a consistent, tested backup schedule across all servers and workstations to ensure business resilience against both ransomware and accidental data loss.

### 3. Network Encryption & Monitoring — Priority: High
Exfiltrated data was unencrypted, making it trivially usable by adversaries after extraction. Implement encryption for data in transit and at rest across all critical systems. Complement this with robust network monitoring — ideally via a SIEM — to detect suspicious activity before a breach escalates.

### 4. IT Security Training & Formal Procedures — Priority: High
IT staff lacked documented procedures for detecting, escalating, and responding to security incidents. Establish a formal Incident Response Plan (IRP), a clear contact chain, and a regular vulnerability testing cadence. IT staff should be conducting periodic security assessments, not discovering infrastructure gaps mid-breach.

### 5. Improve Infrastructure Documentation (CMDB) — Priority: Medium
The IT team did not know the purpose or criticality of core infrastructure components, costing precious response time during the incident. Maintain an accurate Configuration Management Database (CMDB) so that any staff member can quickly understand the environment and take decisive action during a crisis.

## Tools & Frameworks Referenced

| Tool / Framework | Purpose |
|---|---|
| **MITRE ATT&CK** | TTP mapping of attack chain |
| **CMDB Principles** | Asset documentation and infrastructure visibility |
| **IRP Framework** | Incident response planning guidance |
| **MSSP Advisory** | Network monitoring and encryption strategy |

## Skills Demonstrated

- Root cause analysis and incident reconstruction
- Security advisory report writing for executive audiences
- Risk identification and prioritization
- Incident response planning fundamentals
- Security awareness program design
- Infrastructure documentation best practices

---
*TripleTen Cybersecurity Program | Sprint 3 | January 2025*
