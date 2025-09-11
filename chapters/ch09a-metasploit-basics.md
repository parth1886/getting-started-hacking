# 📘 Chapter 9a – Metasploit Exploitation (Basics & Workflow)

---

## 🔹 1. Introduction to Metasploit

**Metasploit Framework (MSF)** is the industry-standard exploitation framework used by penetration testers and security researchers. It provides a modular platform for discovering, verifying, and exploiting vulnerabilities, delivering payloads, and performing post-exploitation tasks.

**Key capabilities:**
- Large module library (exploits, auxiliary, post, payloads, encoders).
- Meterpreter: a powerful in-memory payload/shell.
- Integration with scanners and other tools.
- Extensible: write and add custom modules.

**Use cases:**
- Penetration testing
- Exploit development and testing
- Post-exploitation procedures
- Rapid proof-of-concept development in labs

> **Ethics & legality:** Use Metasploit **only** on systems you own or have explicit permission to test. Unauthorized exploitation is illegal.

---

## 🔹 2. Keywords and Core Commands

Basic `msfconsole` workflow commands:

```bash
msfconsole          # start console
search <term>       # search modules
use <module>        # select a module
show options        # display required options
set RHOSTS <ip>     # set target hosts
set RPORT <port>    # set target port
exploit             # run exploit
sessions -l         # list sessions
sessions -i <id>    # interact with a session
```

Other helpers: `info`, `setg`, `unset`, `back`, `load`.

---

## 🔹 3. Strategy for Finding the Proper Module

1. Recon first — know the OS, services, versions.
2. Search MSF modules by service/CVE:
   ```bash
   search type:exploit name:ms17_010
   search cve:2017
   ```
3. Check module info.
4. Validate prerequisites.
5. Test in a lab environment.
6. Choose payloads that fit the target/system.
7. Use auxiliary modules to verify vulnerabilities.

---

## 🔹 4. Metasploit Directory Structure

- Modules: `/usr/share/metasploit-framework/modules/`
- Config/DB: `~/.msf4/`
- Binary: `/usr/bin/msfconsole`

---

## 🔹 5. Reconnaissance with Metasploit

Examples:

- Port scanning:
  ```bash
  use auxiliary/scanner/portscan/tcp
  set RHOSTS 192.168.56.0/24
  run
  ```

- SSH service banner:
  ```bash
  use auxiliary/scanner/ssh/ssh_version
  set RHOSTS 10.0.0.5
  run
  ```

- SMB enumeration:
  ```bash
  use auxiliary/scanner/smb/smb_version
  set RHOSTS 10.0.0.0/24
  run
  ```

---

## 🔹 6. Vulnerability Scanning Integration

- Import scan results with `db_import`.
- Use `db_nmap` from msfconsole:
  ```bash
  db_nmap -sV -A 192.168.56.0/24
  hosts
  services
  vulnerabilities
  ```

---

👉 Continue with **[Chapter 9b – Advanced Exploitation & Post-Exploitation](ch09b-metasploit-advanced.md)**
