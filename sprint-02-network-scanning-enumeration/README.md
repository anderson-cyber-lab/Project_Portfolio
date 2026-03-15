# Sprint 2: MegaQuagga Network Scanning & Enumeration

## Overview

Conducted comprehensive network scanning and enumeration of the MegaQuagga enterprise network environment as part of a simulated cybersecurity assessment. This project focused on building a complete picture of the network topology, identifying active hosts, open ports, running services, and web applications across multiple subnets.

## Objectives

- Map the full network topology across all subnets
- Identify all live hosts and their associated services using Nmap
- Enumerate web applications and services via directory fuzzing
- Document findings and provide security recommendations based on discovered attack surface

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Nmap** | Host discovery, port scanning, service/OS fingerprinting |
| **Dirb / Fuzzing** | Web application directory enumeration |
| **Firefox / Browser** | Manual verification of discovered web services |
| **CloudShare** | Lab network environment |

## Key Findings

- Identified the network gateway at `192.168.100.1` operating across 8 subnet aliases, providing WAN access and firewall services to all subnets
- Discovered critical web monitoring platforms including **Nagios**, **Zabbix**, **Wazuh** (port 443), **Prometheus** (port 9090), and **Grafana** (port 3000)
- Determined the DMZ architecture and identified a potential weakness — the server network lacked protection behind the internal firewall
- Flagged the presence of a honeypot system as a security concern due to its visibility on the network

## Security Recommendations

- Relocate the server network behind the internal firewall and DMZ to limit lateral movement risk
- Segment access by role — finance staff should not have access to web monitoring software
- Reposition the management subnet deeper within the network to reduce exposure from the network perimeter
- Remove or better conceal the honeypot system to avoid telegraphing its presence to adversaries
- Apply `-Pn` flag awareness to network monitoring policies to account for hosts that reject ICMP ping probes

## Skills Demonstrated

- Network reconnaissance and host discovery
- Service and version enumeration
- Web application fingerprinting
- Network architecture analysis and risk identification
- Technical documentation of findings

---
*TripleTen Cybersecurity Program | Sprint 2 | January 2025*
