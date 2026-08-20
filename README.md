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
| Field | Detail |
|---|---|
| **Pentester Name (Cybersecurity Professional)** | **Syed Bilal Ahmed** |
| **Program/Batch** | B082-Networkwalks|
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

## 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux tools: **WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon**. Each tool was used to collect a different category of information about the target, including domain registration details, web technologies, DNS information, HTTP metadata, WAF detection and DNS infrastructure.

First, I used **WHOIS** to collect publicly available domain registration information. The results identified the domain registrar, registration and expiry dates, domain status and authoritative name servers. The domain was registered through **GoDaddy.com, LLC**, with the authoritative name servers hosted through **HostGator**. The WHOIS result also indicated that DNSSEC was unsigned.

### 4.1.1 WHOIS

**Purpose:**  
WHOIS was used to collect publicly available domain-registration information, including the registrar, registration dates, domain status and authoritative name servers.

**Command:**

```bash
whois networkwalks.com
```
**Result:**

The command executed successfully and returned domain-registration and DNS-related information.

**Key Information Collected:**

- **Domain:** `NETWORKWALKS.COM`
- **Registrar:** `GoDaddy.com, LLC`
- **Creation Date:** `2019-11-06`
- **Registry Expiry:** `2027-11-06`
- **Name Servers:** `NS6135.HOSTGATOR.COM`, `NS6136.HOSTGATOR.COM`
- **DNSSEC:** `Unsigned`
- **Domain Protection:** Delete, Renew, Transfer and Update prohibited

**Observation:**  
The WHOIS lookup provided useful information about the domain registration and externally visible DNS infrastructure. The result is informational and does not by itself confirm a vulnerability.

**Evidence:**

<img width="1160" height="908" alt="Screenshot 2026-08-18 215617" src="https://github.com/user-attachments/assets/205afd8b-9c2c-4f5f-a6b6-6e1634c0d60b" />

- 
### 4.1.2 WhatWeb

**Purpose:**  
WhatWeb was used to fingerprint the `networkwalks.com` website and identify publicly visible web technologies, server software, frameworks, plugins and other application-related information.

**Command:**

```bash
whatweb networkwalks.com

```
**Result:**

The command successfully fingerprinted the target website and identified several web technologies.

**Key Information Collected:**

- **Web Server:** `Apache`
- **CMS:** `WordPress 7.0.4`
- **Plugin:** `WordPress Download Manager 3.3.58`
- **JavaScript:** `jQuery 3.7.1`
- **Framework:** `Bootstrap`
- **IP Address:** `192.232.216.135`
- **Page Title:** `Networkwalks Academy`
- **HTTPS Status:** `200 OK`
- **HTTP Redirect:** `301 Moved Permanently`

**Observation:**

WhatWeb revealed the externally visible technology stack of the website. This information can assist with authorized security assessment and technology review.

**Evidence:**

 <img width="1148" height="912" alt="Screenshot 2026-08-18 222516" src="https://github.com/user-attachments/assets/7114a782-e31a-46fb-b50a-8268607a2272" />


### 4.1.3 Nslookup

**Purpose:**  
Nslookup was used to resolve the `networkwalks.com` domain and identify its publicly accessible IP address.

**Command:**

```bash
nslookup networkwalks.com
```
**Result:**

The command successfully resolved the domain using DNS.

**Key Information Collected:**

- **Domain:** `networkwalks.com`
- **IPv4 Address:** `192.232.216.135`
- **IPv6-related Address:** `64:ff9b::c0e8:d887`
- **DNS Server:** `172.23.212.198`
- **Response:** `Non-authoritative answer`

**Observation:**

The DNS lookup provided the publicly returned network address information for the target domain.

**Evidence:**

<img width="1158" height="913" alt="Screenshot 2026-08-18 215805" src="https://github.com/user-attachments/assets/00a377a8-af9a-4026-88db-337922a75801" />


### 4.1.4 Curl

**Purpose:**  
Curl was used to inspect the HTTP response headers returned by the `networkwalks.com` web server.

**Command:**

```bash
curl -I https://networkwalks.com
```
**Result:**

The command successfully returned the HTTP response headers.

**Key Information Collected:**

- **HTTP Status:** `HTTP/2 200`
- **Server:** `Apache`
- **Content Type:** `text/html; charset=UTF-8`
- **X-Nginx-Cache:** `WordPress`
- **Referrer Policy:** `no-referrer-when-downgrade`
- **WordPress REST API:** `/wp-json/`
- **HttpOnly Cookie:** `wpdm_client`
- **Permissions Policy:** Present

**Observation:**

The Curl response provided useful HTTP and application-level metadata, including server information and a publicly accessible WordPress REST API endpoint.

**Evidence:**

<img width="1163" height="906" alt="Screenshot 2026-08-18 215900" src="https://github.com/user-attachments/assets/1495dac4-bb44-456a-bba4-72405da6dfb2" />


### 4.1.5 Wafw00f

**Purpose:**  
Wafw00f was used to identify whether a Web Application Firewall (WAF) was protecting the `networkwalks.com` website.

**Command:**

```bash
wafw00f networkwalks.com
```
**Result:**

The command successfully detected a Web Application Firewall.

**Key Information Collected:**

- **WAF Detected:** `Yes`
- **WAF:** `ModSecurity`
- **Provider/Technology:** `SpiderLabs`
- **Requests Used:** `2`

**Observation:**

The result indicates that the website is protected by a ModSecurity (SpiderLabs) WAF. This is an important security-control observation during reconnaissance.

**Evidence:**

<img width="1165" height="908" alt="Screenshot 2026-08-18 220045" src="https://github.com/user-attachments/assets/21f888d8-41d5-4f23-9b23-d9725e0a8000" />


### 4.1.6 DNSRecon

**Purpose:**  
DNSRecon was used to enumerate publicly available DNS records associated with `networkwalks.com`, including SOA, NS, MX, A, TXT and SRV records.

**Command:**

```bash
dnsrecon -d networkwalks.com
```
**Result:**

The command successfully enumerated multiple DNS records and infrastructure details.

**Key Information Collected:**

- **SOA Server:** `ns6135.hostgator.com`
- **Name Servers:** `ns6135.hostgator.com`, `ns6136.hostgator.com`
- **A Record:** `192.232.216.135`
- **MX Record:** `mail.networkwalks.com`
- **TXT Record:** Google site-verification record detected
- **SPF:** `v=spf1 +a +mx +ip4:50.87.144.87 +include:websitewelcome.com ~all`
- **SRV Records:** `_autodiscover._tcp.networkwalks.com`
- **Service:** `cpanelemaildiscovery.cpanel.net`
- **Service Port:** `443`
- **DNSSEC:** No DNSSEC answer returned during enumeration

**Observation:**

DNSRecon provided additional information about the target's publicly visible DNS infrastructure, including name servers, mail services, TXT/SPF records and service-discovery records.

**Evidence:**


<img width="1165" height="903" alt="Screenshot 2026-08-18 220149" src="https://github.com/user-attachments/assets/1d2e628c-ed98-4497-bfe6-c7bb8edb45bb" />

<img width="1155" height="915" alt="Screenshot 2026-08-18 220354" src="https://github.com/user-attachments/assets/026b052d-0d42-4c07-92f5-f302f4e2f363" />

---
## 4.2 OSINT Enumeration with theHarvester

As part of the OSINT enumeration activity, I used **theHarvester** to collect publicly available information associated with the `networkwalks.com` domain.

The purpose of this activity was to understand how publicly available search sources can reveal information such as autonomous systems, IP addresses, interesting URLs, subdomains and other externally visible infrastructure details.

### 4.2.1 theHarvester

**Purpose:**  
theHarvester was used to perform passive OSINT enumeration against `networkwalks.com` using multiple public information sources.

**Command:**

```bash
theHarvester -d networkwalks.com -l 10 -b all
```
**Result:**

The command executed successfully and performed an OSINT search against the target domain. Some search sources required API keys and therefore returned limited or unavailable results.

**Key Information Collected:**

- **Target:** `networkwalks.com`
- **ASNs Found:** `3`
- **ASN 1:** `AS13335`
- **ASN 2:** `AS31898`
- **ASN 3:** `AS46606`
- **Interesting URLs:** `2`
- **URL 1:** `http://networkwalks.com/`
- **URL 2:** `https://networkwalks.com/`
- **IP Addresses Found:** `4`
- **LinkedIn Users:** `0`
- **LinkedIn Links:** `0`
- **Subdomains:** `3` found using DNS fallback

**Observation:**

TheHarvester provided additional OSINT information about the target's externally visible infrastructure. The results included multiple ASNs, IP addresses, interesting URLs and subdomain information.

Some sources reported authentication or API-key limitations, including services that required API keys. Therefore, the results should be considered **partial OSINT enumeration** rather than a complete representation of all publicly available information.

The information collected is useful during the reconnaissance phase for building an initial external profile of the target.

**Evidence:**

<img width="1511" height="911" alt="Screenshot 2026-08-19 001906" src="https://github.com/user-attachments/assets/ee4cb36a-3839-4657-adde-5de119c0db58" />
<img width="1515" height="907" alt="Screenshot 2026-08-19 001924" src="https://github.com/user-attachments/assets/47ccbd03-4337-42d0-b61c-c4cc58c49da1" />
<img width="1514" height="906" alt="Screenshot 2026-08-19 001934" src="https://github.com/user-attachments/assets/4ee97674-a842-4790-aecb-f3ba9ea33727" />
<img width="1514" height="906" alt="Screenshot 2026-08-19 001934" src="https://github.com/user-attachments/assets/43e60538-c558-4457-b660-f8360f420fa4" />
<img width="1512" height="919" alt="Screenshot 2026-08-19 001944" src="https://github.com/user-attachments/assets/0ee8da7d-cdff-46ab-af3a-4d6fcf1685f5" />





