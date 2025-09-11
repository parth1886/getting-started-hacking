# 📘 Chapter 10a – Sniffing & Protocol Analysis (Basics)

---

## 🔹 1. What is Sniffing?  
- **Definition**: capturing and analyzing network traffic.  
- Purpose:  
  - Intercept credentials, cookies, and sessions.  
  - Map communications between hosts.  
  - Identify unencrypted sensitive data.  
- Hackers use sniffing for **post-exploitation** and lateral movement.  

---

## 🔹 2. Types of Sniffing  

### 2.1 Passive Sniffing  
- Listen to traffic without altering it.  
- Works only on **hub-based networks** or in environments with broadcast traffic.  
- Stealthy → less chance of detection.  

### 2.2 Active Sniffing  
- Manipulate traffic to intercept data.  
- Techniques:  
  - ARP poisoning (man-in-the-middle)  
  - MAC flooding  
  - DNS spoofing  
- Riskier → easier to detect but more powerful.  

---

## 🔹 3. Protocols of Interest  

- **HTTP** → cleartext usernames, passwords, cookies.  
- **HTTPS** → secure, but vulnerable to SSL stripping/MITM.  
- **FTP / Telnet** → send credentials in plaintext.  
- **SMTP / POP3 / IMAP** → email credentials often unencrypted.  
- **SMB** → Windows file sharing, can leak hashes.  
- **DNS** → can reveal browsing activity and tunneling attempts.  

---

## 🔹 4. Sniffing Tools  

### 4.1 Wireshark  
- GUI-based packet capture & analysis.  
- Features:  
  - Filters (`http.request`, `ftp`, `dns`)  
  - Protocol dissection  
  - Follows TCP streams  
- Usage example:  
  ```bash
  wireshark
  ```

### 4.2 tcpdump  
- Command-line packet capture.  
- Lightweight and scriptable.  
- Example:  
  ```bash
  tcpdump -i eth0 port 80
  ```

### 4.3 Ettercap  
- Specialized for **MITM attacks**.  
- Supports ARP poisoning, DNS spoofing.  
- Can inject malicious content into sessions.  

### 4.4 Dsniff Suite  
- Includes tools like `dsniff`, `arpspoof`, `macof`.  
- Designed for password sniffing & traffic manipulation.  

### 4.5 MITMf (Man-in-the-Middle Framework)  
- Modular MITM attack platform.  
- Can strip SSL, inject scripts, capture credentials.  

---

## 🔹 5. Attack Techniques  

### 5.1 ARP Poisoning  
- Trick a target into sending traffic through attacker’s machine.  
- Tools: `arpspoof`, `ettercap`.  

### 5.2 DNS Spoofing  
- Forge DNS responses to redirect victims.  
- Used to send users to fake login portals.  

### 5.3 Session Hijacking  
- Steal cookies to impersonate authenticated users.  
- Example: capture a web session cookie → reuse to bypass login.  

### 5.4 SSL Stripping  
- Downgrade HTTPS connections to HTTP.  
- Attacker reads traffic in plaintext.  

---

## 🔹 6. Defensive Measures  
- Use **encryption** (HTTPS, SSH, VPN).  
- Implement **static ARP entries** on critical devices.  
- Use **IDS/IPS** to detect ARP/DNS spoofing.  
- Network segmentation → limits sniffing scope.  
- Monitor for abnormal MAC activity.  

---

## ✅ Key Takeaways  
- Sniffing = capturing traffic for credentials, sessions, and data.  
- Two types: **passive (stealthy)** and **active (powerful but noisy)**.  
- Tools: **Wireshark, tcpdump, Ettercap, Dsniff, MITMf**.  
- Key attacks: ARP poisoning, DNS spoofing, session hijacking, SSL stripping.  
- Defense = **encrypt traffic + monitor networks for anomalies**.  

---

