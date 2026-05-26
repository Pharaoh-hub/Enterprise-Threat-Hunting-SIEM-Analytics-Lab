# Forensic Incident Report: IR-001-SSH-BruteForce

## 🕵️ Reconnaissance & Traffic Analysis Summary
During a routine security posture assessment, internal network boundaries were audited to isolate unhardened assets and analyze active traffic streams.

### 1. Perimeter Mapping via Nmap
An internal credentialed scan was executed across the subnet block to map active listening services and identify exposed ports.
* **Execution Command:** `nmap -sV -sC -p- -T4 10.0.4.0/24`
* **Discovery:** Vector exposed an active OpenSSH layer running on an unhardened staging gateway asset, which was flagged for immediate boundary isolation.

### 2. Protocol Forensics via Wireshark
Packet captures (`.pcap`) were extracted during a simulated brute-force lifecycle to analyze behavioral telemetry flags.
* **Analysis Focus:** Inspected TCP handshake sequences and payload lengths using targeted display filters (`tcp.flags.syn == 1 and tcp.flags.ack == 0`).
* **Observation:** Isolated high-frequency connection attempts originating from a single anomalous source IP, confirming a coordinated brute-force footprint before the automated SIEM alerts triggered active response containment rules.

### 3. Web Application Auditing via Burp Suite
To proactively harden the application's authentication endpoints against credential stuffing, proxy intercept tools were deployed.
* **Methodology:** Used **Burp Suite Professional (Repeater & Intruder)** to audit session state persistence, analyze CSRF token strength, and test the microservice's resilience against automated rate-limiting failures.
* **Remediation:** The vulnerabilities exposed during intercept testing were mapped directly into the zero-trust compliance blueprints to enforce absolute multi-factor hardware restrictions.
