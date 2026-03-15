# Sprint 5: Incident Response Plan — Capybara Unlimited

## Overview

Developed a comprehensive Incident Response Plan (IRP) for Capybara Unlimited, a simulated organization requiring a structured, repeatable framework for detecting, containing, and recovering from cybersecurity incidents. The plan established formal procedures across all NIST-aligned IR lifecycle phases and was designed to be operationally actionable by both technical staff and non-technical stakeholders.

## Client Profile

| Field | Detail |
|---|---|
| **Client** | Capybara Unlimited (simulated) |
| **Analyst** | Steven Anderson |
| **Completed** | March 2025 |
| **Deliverable** | Full Incident Response Plan (IRP) |

## Objectives

- Define a clear, repeatable process for responding to cybersecurity incidents
- Establish roles, responsibilities, and escalation paths for the IR team
- Develop playbooks for common incident types (malware, data breach, unauthorized access)
- Align the plan with NIST SP 800-61 incident response guidelines
- Ensure the plan enables rapid containment to minimize business impact

## IR Lifecycle Phases Covered

### 1. Preparation
- Defined the IR team structure with assigned roles (IR Lead, Security Analyst, IT Support, Legal/Compliance, Communications)
- Established asset inventory and criticality classifications
- Documented tooling and access requirements for the IR team
- Created communication templates and notification procedures for internal and external stakeholders

### 2. Detection & Analysis
- Defined detection sources: SIEM alerts, IDS/IPS, endpoint alerts, and user reports
- Established severity classification framework (Critical, High, Medium, Low) with response SLAs per level
- Documented triage procedures for validating true vs. false positive alerts
- Created log collection and evidence preservation guidelines

### 3. Containment, Eradication & Recovery
- Short-term containment: network isolation procedures for affected hosts
- Long-term containment: account lockouts, firewall rule changes, credential rotation
- Eradication: malware removal, patch deployment, system reimaging procedures
- Recovery: restoration from clean backups, return-to-service validation checklist

### 4. Post-Incident Activity
- Defined the post-incident review (PIR) process and required documentation
- Lessons learned reporting template
- IRP update procedure triggered after each major incident

## Incident Playbooks Included

| Incident Type | Key Steps |
|---|---|
| **Malware / Ransomware** | Isolate host → preserve logs → identify patient zero → eradicate → restore from backup |
| **Unauthorized Access** | Lock account → review logs → determine scope → reset credentials → patch entry vector |
| **Phishing** | Block sender → quarantine email → identify recipients → check for payload execution → remediate |
| **Data Breach** | Identify exfiltrated data → contain source → notify legal → assess regulatory obligations → report |

## Frameworks & Standards Referenced

| Framework | Application |
|---|---|
| **NIST SP 800-61** | Primary IR lifecycle structure |
| **MITRE ATT&CK** | TTP context for playbook development |
| **GDPR / Data Privacy Regulations** | Breach notification guidance |

## Skills Demonstrated

- Incident response planning and documentation
- Security policy and procedure writing
- Stakeholder communication planning
- Severity classification and SLA definition
- Playbook development for common threat scenarios
- NIST framework application
- Business continuity and recovery planning

---
*TripleTen Cybersecurity Program | Sprint 5 | March 2025*
