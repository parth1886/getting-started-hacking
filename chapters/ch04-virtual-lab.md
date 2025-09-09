# 📘 Chapter 4 – Creating Our Virtual Lab  

Notes and study guide from *Getting Started Becoming a Master Hacker* by **OccupyTheWeb**.  

---

## 🔹 1. Why a Virtual Lab?  
- Safe environment to **practice hacking legally**.  
- Prevents damage to real systems or networks.  
- Enables testing of exploits, malware, and payloads.  
- Flexible → reset, snapshot, and clone machines as needed.  

---

## 🔹 2. Virtualization Basics  
- Virtualization allows running **multiple OS instances** on one machine.  
- Benefits:  
  - Isolated environments  
  - Easy resets with **snapshots**  
  - Cost-effective (no need for multiple PCs)  

**Popular software:**  
- VirtualBox (free, open-source)  
- VMware Workstation / Fusion (paid, more features)  

---

## 🔹 3. Recommended Lab Setup  

### 3.1 Host Machine  
- Your primary computer that runs virtualization software.  
- Requirements:  
  - 8+ GB RAM (16 GB preferred)  
  - 100+ GB disk space free  
  - CPU with virtualization support (Intel VT-x / AMD-V)  

### 3.2 Guest Machines (Virtual Machines)  
- **Kali Linux**  
  - Industry-standard penetration testing distro.  
  - Includes Nmap, Metasploit, Wireshark, Burp Suite, etc.  
- **Windows 10 (Victim)**  
  - Target for privilege escalation, malware testing, password attacks.  
- **Metasploitable 2/3**  
  - Intentionally vulnerable Linux/Windows VMs for practice.  
- **Other options**  
  - DVWA (Damn Vulnerable Web App)  
  - OWASP Broken Web Apps Project  

---

## 🔹 4. Networking in the Lab  

### 4.1 NAT (Network Address Translation)  
- Default mode.  
- VMs share host’s IP for external access.  
- Safer but limits attacks on external devices.  

### 4.2 Host-Only Adapter  
- Isolated private network between host and VMs.  
- Best for **contained hacking practice**.  

### 4.3 Bridged Adapter  
- VMs appear as separate devices on real network.  
- Allows interaction with other physical devices.  
- ⚠️ More risky — only use with caution.  

---

## 🔹 5. Snapshots & Checkpoints  
- Save VM states before experiments.  
- Roll back if something breaks or malware spreads.  
- Essential for **safe repeated practice**.  

---

## 🔹 6. Tools for Lab Management  
- **VBoxManage** (VirtualBox command-line control).  
- **VMware Workstation snapshots** for advanced recovery.  
- **Vagrant** → automates VM creation.  

---

## ✅ Key Takeaways  
- Virtual lab = **safe, controlled hacking playground**.  
- Always include at least: **Kali Linux + vulnerable target VM**.  
- Networking modes matter → **host-only** is safest.  
- Snapshots are your safety net → always snapshot before hacking.  

---
