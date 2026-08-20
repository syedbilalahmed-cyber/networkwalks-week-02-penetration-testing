<h1 align="center">🛡️ PENETRATION TESTING REPORT</h1>

<h3 align="center">Footprinting, Reconnaissance & Network Scanning Phases</h3>

<p align="center">
  <strong>W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS</strong>
</p>

<p align="center">

  <img src="https://img.shields.io/badge/NETWORKWALKS-2563EB?style=for-the-badge&logoColor=white" alt="Networkwalks"/>

  <img src="https://img.shields.io/badge/WEEK%2002-7C3AED?style=for-the-badge&logoColor=white" alt="Week 02"/>

  <img src="https://img.shields.io/badge/FOOTPRINTING-0891B2?style=for-the-badge&logoColor=white" alt="Footprinting"/>

  <img src="https://img.shields.io/badge/RECONNAISSANCE-0EA5E9?style=for-the-badge&logoColor=white" alt="Reconnaissance"/>

  <img src="https://img.shields.io/badge/OSINT-06B6D4?style=for-the-badge&logoColor=white" alt="OSINT"/>

  <img src="https://img.shields.io/badge/DNS%20ENUMERATION-14B8A6?style=for-the-badge&logoColor=white" alt="DNS Enumeration"/>

  <img src="https://img.shields.io/badge/THEHARVESTER-0F766E?style=for-the-badge&logoColor=white" alt="theHarvester"/>

  <img src="https://img.shields.io/badge/ZENMAP%20%2F%20NMAP-4F46E5?style=for-the-badge&logoColor=white" alt="Zenmap Nmap"/>

</p>

<p align="center">

  <img src="https://img.shields.io/badge/KALI%20LINUX-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux"/>

  <img src="https://img.shields.io/badge/WEB%20RECON-6366F1?style=for-the-badge&logoColor=white" alt="Web Reconnaissance"/>

  <img src="https://img.shields.io/badge/NETWORK%20SECURITY-0284C7?style=for-the-badge&logoColor=white" alt="Network Security"/>

  <img src="https://img.shields.io/badge/STATUS%20%7C%20COMPLETED-16A34A?style=for-the-badge&logoColor=white" alt="Completed"/>

</p>

<p align="center">
  <strong>networkwalks-week-02-penetration-testing</strong>
</p>

<p align="center">
  Footprinting • Reconnaissance • OSINT • DNS Analysis • Web Fingerprinting • WAF Detection • Network Scanning
</p>

---

# PENETRATION TESTING REPORT

### Footprinting, OSINT Enumeration & Network Scanning Phases

**W2-PM-FINAL  |  CYBERSECURITY  |  NETWORKWALKS**

---

| Field | Detail |
|---|---|
| **Pentester Name (Cybersecurity Professional)** | **Syed Bilal Ahmed** |
| **Program/Batch** | Cybersecurity / Ethical Hacking Internship |
| **Organization** | Networkwalks |
| **Week** | Week 02 |
| **Date** | 19–20 August 2026 |
| **Modules Completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM4 (theHarvester OSINT)<br>W2-PM5 (Zenmap Scanning) |
| **Final Deliverable** | W2-PM-FINAL — Penetration Testing Report |
| **Client/Target** | 1. Networkwalks (`networkwalks.com`)<br>2. Authorized local/lab network |
| **Permission / Scope** | Authorized educational cybersecurity training |
| **Phases Covered** | **Phase 1:** Reconnaissance & Footprinting<br>**Phase 2:** OSINT Enumeration<br>**Phase 3:** Scanning & Network Discovery |

---

# 1. Liability Disclaimer

I performed these activities only within the authorized educational cybersecurity training scope and on systems/networks permitted for the practical exercises.

All materials in this repository are provided for educational and research purposes only. The techniques demonstrated here should only be used on systems where appropriate authorization has been obtained or on systems owned by the tester.

Unauthorized access, scanning, enumeration, exploitation, or misuse of cybersecurity techniques may violate applicable laws and regulations.

No exploitation, credential attacks, persistence, privilege escalation, or destructive testing was performed as part of the activities documented in this report.

---

# 2. Introduction

This report documents the practical cybersecurity activities completed during **Week 2 of the Networkwalks Cybersecurity / Ethical Hacking Internship**.

The work covered three practical modules:

- **W2-PM1 — Footprinting & Reconnaissance using multiple Kali Linux tools**
- **W2-PM4 — theHarvester-based OSINT enumeration**
- **W2-PM5 — Zenmap / Nmap network scanning**

The objective was to understand how a cybersecurity professional collects publicly observable information, identifies web technologies and DNS infrastructure, performs OSINT enumeration, discovers active hosts, identifies exposed services, and documents security-relevant observations.

The reconnaissance activities were performed using Kali Linux tools against the assigned training target, while Zenmap was used for an authorized local/lab network environment.

All findings in this report are treated as **observations rather than confirmed vulnerabilities** unless separately validated through authorized security testing.

---

# 3. Tools Used

The table below lists each tool used in this report and its purpose.

| Tool | Purpose |
|---|---|
| **Kali Linux** | Cybersecurity testing and reconnaissance environment |
| **WHOIS** | Find domain registration details, registrar, dates and name servers |
| **WhatWeb** | Fingerprint web technologies, CMS, plugins and server information |
| **nslookup** | Resolve the domain name to IP addresses using DNS |
| **curl -i** | Inspect HTTP response and security/application headers |
| **Wafw00f** | Identify the presence of a Web Application Firewall |
| **DNSRecon** | Enumerate DNS records including NS, MX, TXT, SOA and SRV |
| **theHarvester** | Perform OSINT-based domain, host and infrastructure enumeration |
| **Zenmap / Nmap** | Discover live hosts and identify exposed TCP services |
| **Windows / Local Network Tools** | Support local network identification and scanning |

---

# 4. Activities Performed

## 4.1 Footprinting & Reconnaissance — W2-PM1

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux tools:

**WHOIS, WhatWeb, nslookup, curl, Wafw00f and DNSRecon.**

Each tool was used to collect a different type of information about the target.

---

### WHOIS

First, I used **WHOIS** to obtain publicly available domain registration information.

### Target

```text
networkwalks.com
