# 📘 Chapter 6 – Active Reconnaissance  

Notes and study guide from *Getting Started Becoming a Master Hacker* by **OccupyTheWeb**.  

---

## 🔹 1. What is Active Reconnaissance?  
- **Definition**: Gathering information about a target by **directly interacting** with its systems.  
- Examples: scanning ports, probing services, sending crafted packets.  
- Risk: can trigger IDS/IPS or leave logs on the target.  
- Complements passive recon with **real-time technical details**.  

---

## 🔹 2. Goals of Active Recon  
- Identify **live hosts**.  
- Discover **open ports and services**.  
- Detect **OS and software versions**.  
- Map the **network topology**.  
- Find potential **vulnerabilities** for exploitation.  

---

## 🔹 3. Techniques  

### 3.1 Ping Sweeps  
- Used to identify **which hosts are alive**.  
- Tools:  
  - `ping`  
  - `nmap -sn <network>` (no port scan, host discovery only)  

### 3.2 Port Scanning  
- Determines which services are listening.  
- Common flags:  
  - `nmap -p- <target>` → scan all ports  
  - `nmap -sS <target>` → SYN (stealth) scan  
  - `nmap -sU <target>` → UDP scan  

### 3.3 Service & Version Detection  
- Identifies what’s running on open ports.  
- `nmap -sV <target>` → probes for service versions.  
- Banner grabbing with `nc` (netcat) or `telnet`.  

### 3.4 OS Fingerprinting  
- Determines target operating system.  
- Techniques:  
  - TCP/IP stack fingerprinting  
  - TTL and window size analysis  
- Tools:  
  - `nmap -O <target>`  
  - `xprobe2`  

### 3.5 Firewall/IDS Evasion  
- Modify scans to bypass detection.  
- Techniques:  
  - Decoy scans (`nmap -D`)  
  - Fragmented packets (`nmap -f`)  
  - Timing options (`-T0` to `-T5`)  
- Example: slow scans to avoid alerts.  

---

## 🔹 4. Tools for Active Recon  

- **Nmap** → all-purpose network scanner.  
- **Hping3** → custom packet crafting, firewall testing.  
- **Netcat (nc)** → banner grabbing, manual connections.  
- **WhatWeb / BuiltWith** → identify web server frameworks and technologies.  
- **Unicornscan** → high-speed alternative to Nmap.  

---

## 🔹 5. Risks & Considerations  
- Easier to detect than passive recon.  
- Logs may capture:  
  - Source IP  
  - Scan type and timestamps  
- Legal risk if performed on systems without authorization.  
- Always use in **controlled labs** or with **written permission**.  

---

## ✅ Key Takeaways  
- Active reconnaissance = **direct interaction with target systems**.  
- Essential for mapping open ports, services, and OS details.  
- Tools: **Nmap, Hping3, Netcat, WhatWeb, Unicornscan**.  
- Must balance thoroughness with **stealth and legality**.  

---
