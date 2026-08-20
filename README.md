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

<p align="center">
  <a href="W2-PM-Sample Permission Letter v1.pdf">
    <img src="https://img.shields.io/badge/🛡️%20VIEW%20LETTER%20OF%20AUTHORIZATION-2563EB?style=for-the-badge&logoColor=white&labelColor=0F172A" alt="View Letter of Authorization"/>
  </a>
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

---

## 4.3 Network Scanning with Zenmap / Nmap

For the network-scanning activity, I used **Zenmap**, the graphical interface for **Nmap**, to perform network discovery on an authorized local/lab network.

The objective was to identify active hosts, discover open TCP services and review the network topology generated from the scan.

### 4.3.1 Network Target

The network range used for the scan was:

```text
172.23.212.96/24
```
Scan Profile: Quick Scan

Nmap Command: nmap -T4 -F 172.23.212.96/24

The scan covered 256 IP addresses.

<img width="1919" height="1002" alt="Screenshot 2026-08-19 230844" src="https://github.com/user-attachments/assets/b12b50ba-1334-4d95-b9bd-f86c36368c08" />

### 4.3.2 Host Discovery and Service Enumeration

The scan identified **2 active hosts** within the scanned network:

- `172.23.212.198`
- `172.23.212.96`

For `172.23.212.198`, the following service was identified:

- **53/tcp — DNS**

For `172.23.212.96`, the following open TCP services were identified:

| Port | State | Service |
|---|---|---|
| `135/tcp` | Open | `msrpc` |
| `139/tcp` | Open | `netbios-ssn` |
| `445/tcp` | Open | `microsoft-ds` |
| `5432/tcp` | Open | `postgresql` |

**Result:**
```text

Nmap scan report for 172.23.212.198
Host is up.
53/tcp open domain

Nmap scan report for 172.23.212.96
Host is up.
135/tcp open msrpc
139/tcp open netbios-ssn
445/tcp open microsoft-ds
5432/tcp open postgresql

Nmap done: 256 IP addresses (2 hosts up)

```
**Observation:**

The Nmap scan successfully identified active hosts and their exposed network services within the authorized local/lab environment.

The discovered ports represent **observed services and do not automatically indicate vulnerabilities**. Further authorized assessment would be required to determine whether any service is misconfigured or vulnerable.

**Evidence:**
<img width="1906" height="1008" alt="Screenshot 2026-08-19 230922" src="https://github.com/user-attachments/assets/1b625afe-9550-4240-a498-efe88efc4e26" />

### 4.3.3 Zenmap Host View

The Zenmap interface displayed the discovered hosts in the host list.

The identified hosts were:

```text
172.23.212.198
172.23.212.96

```
The Zenmap legend was also reviewed to understand the host and connection indicators.

Evidence:
<img width="1919" height="1007" alt="Screenshot 2026-08-19 230957" src="https://github.com/user-attachments/assets/99381b31-fbf7-4a82-8c9b-403613ddf2f0" />

### 4.3.4 Zenmap Topology

After completing the scan, I opened the Topology section in Zenmap to visualize the discovered network relationships.

The topology displayed:
```text

localhost
172.23.212.198
172.23.212.96
```

The Zenmap legend was also reviewed to understand the host and connection indicators.

Evidence:
<img width="1919" height="1007" alt="Screenshot 2026-08-19 230957" src="https://github.com/user-attachments/assets/8faf05c2-3925-4c9b-b27b-f9c78924bdc8" />

### 4.3.5 Topology Export

The generated topology was prepared for documentation using Zenmap's Save Graphic / Save Topology option.

The topology was exported as a PDF for inclusion in the practical documentation.

Evidence:

<img width="1917" height="1009" alt="Screenshot 2026-08-19 231230" src="https://github.com/user-attachments/assets/39a5551f-c101-4081-8ef7-ee8af72594ad" />
<img width="1902" height="997" alt="Screenshot 2026-08-19 231742" src="https://github.com/user-attachments/assets/82c34bd3-7573-4512-9208-8d2be66f0ce7" />

### 4.3.6 Network Scanning Summary

| Category | Result |
|---|---|
| **Tool** | Zenmap / Nmap |
| **Scan Profile** | Quick Scan |
| **Target Network** | `172.23.212.96/24` |
| **IP Addresses Scanned** | `256` |
| **Active Hosts** | `2` |
| **Host 1** | `172.23.212.198` |
| **Host 2** | `172.23.212.96` |
| **DNS** | `53/tcp` |
| **MSRPC** | `135/tcp` |
| **NetBIOS-SSN** | `139/tcp` |
| **Microsoft-DS / SMB** | `445/tcp` |
| **PostgreSQL** | `5432/tcp` |
| **Topology Generated** | Yes |
| **Topology Exported** | PDF |

**Final Observation:**

The Zenmap/Nmap activity demonstrated how network scanning can be used to identify live hosts and exposed services within an authorized network. The results provide a useful initial view of the network and can support further authorized security assessment.

**Evidence:**

<img width="1906" height="1008" alt="Screenshot 2026-08-19 230922" src="https://github.com/user-attachments/assets/a1e079fb-0a42-4940-aa8b-b4f637480a5a" />

# 5. Risk Analysis / Impact

Based on the information collected during the **footprinting, reconnaissance, OSINT and network scanning activities**, the following potential security observations were identified.

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Web technology information exposed | WhatWeb identified Apache, WordPress `7.0.4`, WP Download Manager `3.3.58`, jQuery and Bootstrap | Exposed technology information may assist further authorized security assessment and technology identification | **● Medium** |
| 2 | Publicly identifiable server IP | Nslookup resolved `networkwalks.com` to `192.232.216.135` | Provides information about the externally visible network location of the web service | **● Low** |
| 3 | HTTP and application information exposed | Curl returned HTTP response headers and identified the `/wp-json/` endpoint | May assist technology fingerprinting and further authorized enumeration | **● Low** |
| 4 | WAF technology identifiable | Wafw00f identified `ModSecurity (SpiderLabs)` | Reveals information about the web application's security architecture | **● Low** |
| 5 | DNS infrastructure information exposed | DNSRecon identified SOA, NS, A, MX, TXT, SPF and SRV records | DNS information can help build an external profile of the target infrastructure | **● Medium** |
| 6 | OSINT information publicly discoverable | theHarvester identified ASNs, IP addresses, URLs and subdomain information | Publicly available infrastructure information may assist further reconnaissance | **● Medium** |
| 7 | Multiple active hosts identified | Zenmap/Nmap identified `2` active hosts in the authorized local/lab network | Unknown or unauthorized devices may increase the network attack surface | **● Medium** |
| 8 | Multiple network services exposed | Nmap identified DNS `53/tcp`, MSRPC `135/tcp`, NetBIOS-SSN `139/tcp`, Microsoft-DS/SMB `445/tcp` and PostgreSQL `5432/tcp` | Unnecessary or improperly secured services may increase the attack surface and should be reviewed | **● Medium** |

### Risk Level Key

- **● Critical** — Potentially severe security impact requiring immediate investigation
- **● Medium** — Security-relevant observation requiring review
- **● Low** — Informational observation with limited direct impact

The findings listed above are **security observations from the reconnaissance and scanning exercises and are not confirmed vulnerabilities**.

The activities primarily involved information gathering, OSINT enumeration, host discovery and service identification. No exploitation, credential attacks, privilege escalation, persistence or destructive testing was performed.

Therefore, identifying a software version, IP address, DNS record, WAF or open network service does not by itself confirm that a vulnerability exists. Further authorized security testing would be required to validate any potential weakness.

---

# 6. Recommendations

Based on the observations collected during the practical activities, the following security recommendations are suggested:

1. **Review publicly exposed technology information**  
   Regularly review publicly visible information about web servers, CMS platforms, plugins and frameworks.

2. **Keep web technologies updated**  
   Ensure that WordPress, plugins, web servers and other application components are maintained with appropriate security updates.

3. **Review HTTP response information**  
   Review HTTP response headers and application endpoints to minimize unnecessary technical information exposure.

4. **Review DNS infrastructure**  
   Periodically review publicly available DNS records and remove unnecessary or outdated records and services.

5. **Maintain WAF protection**  
   Keep the detected ModSecurity WAF properly configured, updated and monitored for security events.

6. **Review publicly available OSINT information**  
   Organizations should periodically review what infrastructure information can be discovered through publicly available sources.

7. **Perform regular internal network discovery**  
   Authorized network scans should be performed periodically to identify active devices and exposed services.

8. **Review open network services**  
   Services such as DNS, SMB, MSRPC and PostgreSQL should be reviewed to ensure that they are required, properly configured and appropriately restricted.

9. **Investigate unknown hosts**  
   Any unexpected device identified during network discovery should be verified and investigated.

10. **Maintain network documentation**  
    Hosts, services and network topology should be documented and kept up to date.

11. **Perform security testing within authorized scope**  
    Reconnaissance, scanning and any subsequent security testing should only be performed against systems and networks for which appropriate authorization has been provided.

---

# 7. Conclusion

During Week 2 of my **Cybersecurity and Ethical Hacking internship**, I completed practical activities covering **footprinting, reconnaissance, OSINT enumeration and network scanning**.

During the footprinting and reconnaissance activity, I used six Kali Linux tools: **WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon**. These tools helped me collect information about domain registration, web technologies, DNS records, HTTP metadata, WAF protection and publicly visible DNS infrastructure.

The WHOIS activity provided domain registration information, including the registrar, registration dates, name servers and DNSSEC status. WhatWeb helped identify the externally visible web technology stack, while Nslookup provided the domain's publicly returned IP address.

Curl was used to inspect HTTP response headers, and Wafw00f identified **ModSecurity (SpiderLabs)** as the detected WAF technology. DNSRecon provided additional DNS information, including SOA, NS, A, MX, TXT, SPF and SRV records.

I also used **theHarvester** for OSINT enumeration. The activity identified publicly available information including ASNs, IP addresses, interesting URLs and subdomain information. Some external sources required API keys, so the results were treated as **partial OSINT enumeration**.

For network scanning, I used **Zenmap/Nmap** against the authorized local/lab network. The scan covered `172.23.212.96/24` and identified **2 active hosts**:

- `172.23.212.198`
- `172.23.212.96`

The scan identified services including **DNS, MSRPC, NetBIOS-SSN, Microsoft-DS/SMB and PostgreSQL**. I also reviewed the discovered hosts through Zenmap and generated a network topology for documentation.

Overall, these activities helped me understand how a cybersecurity professional can collect and analyze information before performing further security assessment. I also learned the importance of documenting commands, results, observations, evidence and potential security impact in a structured penetration-testing report.

All activities documented in this repository were performed within the **authorized educational cybersecurity training and local/lab environment**. No exploitation or destructive testing was performed.

---

# 8. Evidence Collected

| Evidence | Tool | Purpose |
|---|---|---|
| WHOIS Output | WHOIS | Domain registration information |
| Web Fingerprint | WhatWeb | Web technology identification |
| DNS Resolution | Nslookup | IP address resolution |
| HTTP Headers | Curl | HTTP/application metadata |
| WAF Detection | Wafw00f | WAF identification |
| DNS Enumeration | DNSRecon | DNS infrastructure information |
| OSINT Enumeration | theHarvester | Public infrastructure information |
| Network Scan | Nmap | Host and service discovery |
| Host View | Zenmap | Graphical host/result review |
| Topology | Zenmap | Network relationship visualization |
| Topology Export | Zenmap | PDF documentation |

---

<p align="center">
  <h1 align="center">🛡️ NETWORKWALKS</h1>
</p>


<p align="center">
  Footprinting • Reconnaissance • OSINT • DNS Analysis • Web Fingerprinting • WAF Detection • Network Scanning
</p>

<p align="center">
  <a href="Networkwalks_Week_2_Final_Professional_Report_Syed_Bilal_Ahmed_v3_COMPLETED(1)-2.pdf">
    <img src="https://img.shields.io/badge/📄%20VIEW%20FULL%20PENETRATION%20TESTING%20REPORT-2563EB?style=for-the-badge&logoColor=white" alt="View Full Penetration Testing Report"/>
  </a>
</p>

---

#  Mentor & Program Credit

This practical project was completed as part of the **Networkwalks Cybersecurity & Ethical Hacking training program**.

Special thanks to the **Networkwalks training team and mentors** for providing the practical cybersecurity exercises, structured learning modules and guidance throughout the internship.

The project provided hands-on exposure to industry-relevant reconnaissance, OSINT and network-scanning techniques in an authorized educational environment.

### Mentor

**Waqas Karim CCIE**  
Cybersecurity Professional  
Networkwalks

> Grateful for the guidance and practical learning provided throughout the cybersecurity training program.

---

#  Professional Note

This repository represents my practical learning and hands-on work during **Week 02** of the cybersecurity training program.

The purpose of this project is to demonstrate my understanding of reconnaissance, information gathering, OSINT, DNS analysis and network discovery while following an authorized and ethical testing approach.

All findings documented in this repository should be interpreted within the scope of the educational exercise.


# Author

<p align="center">

<strong>Syed Bilal Ahmed</strong>

</p>

<p align="center">

Cybersecurity Student | Ethical Hacking & Network Security

</p>

<p align="center">

Footprinting • Reconnaissance • OSINT • Network Security • Penetration Testing

</p>


<p align="center">
  <strong>W2-PM-FINAL | NETWORKWALKS | WEEK 02</strong>
</p>

<p align="center">
  🛡️ <strong>Learn • Practice • Document • Secure</strong> 🛡️
</p>

---
**End of Report**

