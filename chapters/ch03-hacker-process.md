# 📘 Chapter 3 – The Hacker Process  

Notes and study guide from *Getting Started Becoming a Master Hacker* by **OccupyTheWeb**.  

---

## 🔹 1. Hacking as a Process  
- Hacking is **systematic**, not random.  
- Follows a **methodical process** similar to the scientific method.  
- Core steps:  
  1. Fingerprinting  
  2. Reconnaissance  
  3. Password cracking  
  4. Exploitation  
  5. Post-exploitation  
  6. Covering tracks  

---

## 🔹 2. Fingerprinting  
- Goal: identify **target system details**.  
- Key info to gather:  
  - Operating system  
  - Services and ports  
  - Applications in use  
- Tools:  
  - `nmap` (service/version detection, OS fingerprinting)  
  - `hping3` (packet-level probing)  
  - Banner grabbing via `netcat`  

---

## 🔹 3. Reconnaissance  

### 3.1 Passive Reconnaissance  
- Collect info **without interacting** directly with target.  
- Sources:  
  - **OSINT (Open Source Intelligence)**  
  - Google dorking (`site:`, `filetype:`, `intitle:`)  
  - WHOIS records (domain ownership)  
  - Shodan (internet device search)  
  - Social media, employee info leaks  

### 3.2 Active Reconnaissance  
- Direct interaction with target systems.  
- Involves **network scans and probes**.  
- Tools:  
  - `nmap` (TCP/UDP scans, version detection)  
  - `hping3` (firewall/protocol probing)  
  - `whatweb` / `builtwith` (web tech fingerprinting)  

---

## 🔹 4. Password Cracking  
- Attack methods:  
  - Dictionary attacks (wordlists like **rockyou.txt**)  
  - Brute force attacks  
  - Hybrid (dictionary + mutations)  
  - Rainbow tables  
- Tools:  
  - `john` (John the Ripper)  
  - `hashcat`  
  - `THC-Hydra`  
- Common hashes: MD5, SHA-1, SHA-256, NTLM.  

---

## 🔹 5. Exploitation  
- Goal: gain **access** via vulnerabilities.  
- Sources of exploits:  
  - Known CVEs (Common Vulnerabilities & Exposures)  
  - Zero-day exploits (rare, valuable)  
- Tools:  
  - Metasploit Framework  
  - Custom Python/Perl scripts  
  - Manual exploitation techniques  

---

## 🔹 6. Post-Exploitation  
- Once inside → establish **persistence** and escalate privileges.  
- Common actions:  
  - Create backdoors  
  - Privilege escalation (user → root/admin)  
  - Data extraction / exfiltration  
  - Pivoting to other systems on the network  
- Tools:  
  - Meterpreter (Metasploit payload)  
  - PowerShell Empire  
  - Custom shell scripts  

---

## 🔹 7. Covering Tracks  
- Remove or alter evidence of compromise.  
- Techniques:  
  - Clearing logs (`/var/log`, Event Viewer)  
  - Timestomping (altering file timestamps)  
  - Rootkits to hide processes/files  
  - Encrypted tunnels for C2 (Command & Control)  
- ⚠️ Reminder: In real-world pentests → report findings instead of hiding them.  

---

## ✅ Key Takeaways  
- Hacking = **step-by-step process**, not random trial & error.  
- Each phase builds on the previous (recon → exploit → post-exploit).  
- Tools are important, but **mindset + methodology** matter most.  
- Always differentiate between **ethical pentesting** vs **illegal hacking**.  

---
