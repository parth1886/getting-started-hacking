# 📘 Chapter 5 – Passive Reconnaissance  

Notes and study guide from *Getting Started Becoming a Master Hacker* by **OccupyTheWeb**.  

---

## 🔹 1. What is Passive Reconnaissance?  
- **Definition**: Gathering information about a target **without directly engaging** its systems.  
- Purpose: build a profile of the target to aid in later attacks.  
- Stealthy → leaves no trace in target logs.  
- Part of the **OSINT (Open Source Intelligence)** process.  

---

## 🔹 2. Sources of Passive Recon  

### 2.1 WHOIS Lookup  
- Reveals domain registration info:  
  - Owner’s name / organization  
  - Contact details  
  - Registrar and DNS servers  
- Tools:  
  - `whois` command-line  
  - Online WHOIS lookup  

### 2.2 DNS Reconnaissance  
- Domain info: subdomains, mail servers, TXT records.  
- Techniques:  
  - Zone transfers (if misconfigured)  
  - Reverse lookups  
- Tools:  
  - `nslookup`  
  - `dig`  
  - `dnsrecon`  

### 2.3 Google Dorking  
- Crafting advanced queries to extract sensitive info.  
- Examples:  
  - `site:example.com` → pages only on target domain  
  - `filetype:pdf site:example.com` → find PDF files  
  - `intitle:"index of"` → exposed directories  
- Useful for finding: config files, login portals, leaked docs.  

### 2.4 Shodan Search Engine  
- Search engine for Internet-connected devices.  
- Can reveal:  
  - Routers, cameras, IoT devices  
  - Industrial systems (SCADA, ICS)  
  - Misconfigured servers and databases  

### 2.5 Social Media & OSINT  
- Employees often leak details unknowingly.  
- Data sources:  
  - LinkedIn → employee roles & company hierarchy  
  - Twitter / Facebook → usernames, emails, photos  
  - GitHub repos → exposed code or API keys  

### 2.6 Metadata Analysis  
- Documents (PDF, Word, images) often contain metadata.  
- Reveals usernames, software versions, geolocation.  
- Tools:  
  - `exiftool`  
  - FOCA (Fingerprinting Organizations with Collected Archives)  

---

## 🔹 3. Passive Recon Tools  
- `theHarvester` → gathers emails, subdomains, hostnames.  
- `Maltego` → OSINT visualization tool.  
- `Recon-ng` → framework for automated recon.  
- `Google Hacking Database (GHDB)` → prebuilt search queries.  
- `Censys` → alternative to Shodan for Internet-wide scans.  

---

## 🔹 4. Advantages & Limitations  

### Advantages  
- Stealthy (no logs on target).  
- Can reveal huge amounts of info before active probing.  
- Legal if using only public data.  

### Limitations  
- Data may be **outdated or incomplete**.  
- No confirmation of current vulnerabilities.  
- Some info sources may be restricted (e.g., GDPR-protected WHOIS).  

---

## ✅ Key Takeaways  
- Passive reconnaissance = **first step of hacking** → builds intelligence before scanning.  
- Use OSINT, Google dorking, WHOIS, Shodan, and metadata.  
- Combine multiple sources for a strong target profile.  
- Remember: **stealth now, attack later.**  

---
