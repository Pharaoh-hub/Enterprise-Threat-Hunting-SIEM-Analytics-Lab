# Enterprise Threat Hunting & SIEM Telemetry Analytics

A comprehensive security operations engineering repository documenting the deployment, configuration, and structural tuning of an enterprise-grade Security Information and Event Management (SIEM) environment. This framework handles distributed log aggregation, endpoint behavioral auditing, and active threat hunting.

## 🎯 Lab Topology & Telemetry Stream

[ Compromised Endpoint ] ──► [ Wazuh Log Agent ] ──► [ Central SIEM Indexer ] ──► [ Elastic Search Dashboard ]


## ⚡ Technical Implementations & Security Controls
* **SIEM Core Orchestration:** Configured a centralized **Wazuh Indexer** and manager layer inside an isolated hypervisor environment to process event streams from distributed Windows and Linux server assets.
* **Vulnerability Assessment Pipeline:** Integrated **OpenVAS/GVM** network feed databases to perform automated, prioritized credentialed scans across active internal asset boundaries.
* **Traffic Forensic Auditing:** Developed deep protocol-level visibility profiles using **Wireshark** and **TCPDump** to analyze active network handshakes, inspect malformed packet flags, and isolate malicious command-and-control (C2) callback patterns.

## 🕵️ Active Incident Response Case Study: Brute-Force Mitigation
* **The Vector:** Monitored a simulated brute-force authentication attempt directed at a core corporate Linux gateway asset via SSH.
* **Detection Logic:** Aggregated syslogs triggered customized alert correlation thresholds within the SIEM engine, alerting on high-frequency login failures coming from an isolated IP.
* **Active Containment Executed:** Programmed a custom active response workflow that pushed a zero-trust network firewall rule to the endpoint agent, instantly dropping traffic from the attacking host IP address.

## 📁 Repository Structure
```text
enterprise-siem-threat-hunting/
├── configs/
│   ├── wazuh/
│   │   └── ossec.conf              # Customized endpoint logging configuration
│   └── rules/
│       └── local_rules.xml         # Custom regex-based brute-force threat signatures
├── scripts/
│   ├── telemetry_installer.sh      # Bash script for automated agent onboarding
│   └── log_parser.py               # Python parser extracting anomalous source IPs
├── incident-reports/
│   └── IR-001-SSH-BruteForce.md    # Formatted analytical post-incident report
└── README.md
👤 Maintainer
Oladoye Toyeeb

Role: Cybersecurity Analyst & DevSecOps Engineer

Location: Lagos, Nigeria
