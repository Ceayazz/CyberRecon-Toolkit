# CyberRecon-Toolkit

> A Python-based automated reconnaissance framework for cybersecurity attack surface analysis. Built for OSINT-driven domain intelligence gathering, DNS enumeration, subdomain discovery, and security assessment reporting.

---

## Overview

CyberRecon-Toolkit automates the full reconnaissance lifecycle against a target domain. It collects and correlates data from public sources — DNS records, WHOIS data, subdomains, IP ownership, HTTP security headers, and social media presence — and produces structured JSON reports for analysis.

Developed as part of a 6-week cybersecurity reconnaissance project and used during a Cyber Security internship at **Black Kite** to conduct attack surface analysis for 50+ companies.

---

## Features

| Module | Description |
|---|---|
| **WHOIS & Domain Analysis** | Extracts domain owner, registration/expiry dates, registrar info |
| **DNS Analysis** | Queries A, MX, NS, TXT records; identifies misconfigurations |
| **Subdomain Discovery** | Enumerates subdomains via Sublist3r / SecurityTrails API |
| **IP & Geolocation Analysis** | Maps IPs to physical locations and ownership via IPWhois |
| **HTTP Security Header Analysis** | Checks HSTS, CSP, X-Frame-Options, X-Content-Type-Options |
| **Social Media & OSINT** | Discovers LinkedIn employees, Twitter handles, public profiles |
| **Automated Reporting** | Aggregates all findings into structured JSON + summary report |

---

## Tech Stack

- **Language:** Python 3.x
- **Libraries:** `whois`, `dnspython`, `requests`, `beautifulsoup4`, `socket`, `nmap`
- **APIs:** SecurityTrails API, IPWhois
- **Output:** JSON, plain-text reports
- **Interface:** CLI (Command Line Interface)

---

## Installation

```bash
# Clone the repository
git clone https://github.com/Ceayazz/CyberRecon-Toolkit.git
cd CyberRecon-Toolkit

# Install dependencies
pip install -r requirements.txt
```

---

## Usage

Each module runs independently, following the reconnaissance phases in order:

```bash
# Week 1 — Environment setup & research
python hafta1.py

# Week 2 — Domain & DNS analysis
python hafta2.py

# Week 3 — Subdomain discovery
python hafta3.py

# Week 4 — IP & related domain analysis
python hafta4.py

# Week 5 — Social media & employee OSINT
python hafta5.py
```

Output files are saved as JSON and text reports in the project root:
- `cikti.json` — aggregated reconnaissance data
- `result.json` — final analysis results
- `kocholding_analysis_report.txt` — sample target report
- `KOC_social_media_data.json` — social media OSINT output

---

## Sample Output Structure

```json
{
  "domain": "example.com",
  "whois": {
    "registrar": "GoDaddy",
    "creation_date": "2010-03-15",
    "expiry_date": "2026-03-15"
  },
  "dns": {
    "A": ["93.184.216.34"],
    "MX": ["mail.example.com"],
    "NS": ["ns1.example.com", "ns2.example.com"]
  },
  "subdomains": ["mail.example.com", "dev.example.com"],
  "security_headers": {
    "HSTS": "present",
    "CSP": "missing",
    "X-Frame-Options": "present"
  }
}
```

---

## Reconnaissance Methodology

This tool follows a structured 6-phase approach:

1. **Domain & WHOIS Intelligence** — ownership, registration, expiry
2. **DNS Enumeration** — record types, misconfigurations
3. **Subdomain Discovery** — attack surface expansion
4. **IP & Network Analysis** — geolocation, ASN, ownership
5. **Social Media OSINT** — employee mapping, public exposure
6. **Web Security Assessment** — HTTP headers, security posture scoring

---

## Ethical & Legal Notice

This tool is intended for **authorized security assessments only**. Only use against domains you have explicit permission to analyze. Unauthorized reconnaissance may violate laws including the Computer Fraud and Abuse Act (CFAA) and similar regulations.

---

## Author

**Celal Enes Ayaz**
Cyber Security & Network Engineer | Python | OSINT | SOC

- LinkedIn: [linkedin.com/in/celalenesayaz](https://linkedin.com/in/celalenesayaz)
- GitHub: [github.com/Ceayazz](https://github.com/Ceayazz)
