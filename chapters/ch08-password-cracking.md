# 📘 Chapter 8 – Password Cracking  

Notes and study guide from *Getting Started Becoming a Master Hacker* by **OccupyTheWeb**.  

---

## 🔹 1. Why Password Cracking Matters  
- Passwords = **weakest link** in most security systems.  
- Used for:  
  - System logins  
  - Database authentication  
  - Web applications  
  - Wireless networks  
- Goal: **obtain valid credentials** for further exploitation.  

---

## 🔹 2. Password Attack Methods  

### 2.1 Brute Force  
- Try **every possible combination**.  
- Guaranteed success, but extremely slow with complex passwords.  

### 2.2 Dictionary Attack  
- Use precompiled wordlists of common passwords.  
- Faster than brute force but limited to known words.  
- Example: `rockyou.txt` wordlist.  

### 2.3 Hybrid Attack  
- Start with dictionary → apply mutations.  
- Examples:  
  - Replace letters with numbers (`password` → `p@ssw0rd`).  
  - Add numbers/symbols at start/end.  

### 2.4 Rainbow Tables  
- Precomputed hash databases.  
- Match password hashes to cracked equivalents.  
- ⚠️ Limited by hash type & salt usage.  

### 2.5 Credential Stuffing  
- Using **leaked usernames & passwords** from other breaches.  
- Works due to password reuse across platforms.  

---

## 🔹 3. Password Hashes  
- Systems don’t store plain-text passwords → they store **hashes**.  
- Common hash algorithms:  
  - MD5 (fast, weak)  
  - SHA-1 (deprecated)  
  - SHA-256 (more secure)  
  - NTLM (Windows)  
- Hashes can be cracked if:  
  - Algorithm is weak  
  - Password is short/common  
  - Rainbow tables or GPUs are used  

---

## 🔹 4. Tools for Password Cracking  

- **John the Ripper (JtR)** → fast, versatile cracker.  
- **Hashcat** → GPU-accelerated cracking, highly efficient.  
- **THC-Hydra** → brute force network logins (FTP, SSH, Telnet, etc.).  
- **Medusa** → parallel brute forcing tool.  
- **CeWL** → custom wordlist generator from websites.  
- **Crunch** → wordlist generator with patterns.  

---

## 🔹 5. Wireless Password Cracking  
- **WEP** → easily broken with tools like `aircrack-ng`.  
- **WPA/WPA2** → captured handshake cracked offline with Hashcat.  
- Tools:  
  - `airmon-ng`, `airodump-ng`, `aireplay-ng`, `aircrack-ng`.  

---

## 🔹 6. Defensive Perspective  
- Use **long, complex, unique passwords**.  
- Enable **multi-factor authentication (MFA)**.  
- Monitor login attempts & lockouts.  
- Store hashes with **salt** and use strong algorithms (e.g., bcrypt, scrypt, Argon2).  

---

## ✅ Key Takeaways  
- Password cracking is often the **entry point to deeper system access**.  
- Attack methods: brute force, dictionary, hybrid, rainbow tables, credential stuffing.  
- Tools: **John the Ripper, Hashcat, Hydra, Medusa, CeWL, Crunch**.  
- Wireless networks remain a major target (WEP/WPA2).  
- Defense = **strong passwords + MFA + proper hashing**.  

---
