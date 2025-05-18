# ETHICAL-HACKING-PROJECTS
# 🛡️ Ethical Hacking Project

## 📘 Overview

This project simulates real-world **penetration testing** and **defense mechanisms** using virtualized vulnerable environments and industry-grade tools. It is designed to provide hands-on experience with ethical hacking methodologies, including scanning, enumeration, exploitation, and mitigation.

## 🎯 Objectives

- Simulate real-world cyberattacks in a controlled environment.
- Learn and practice ethical hacking techniques.
- Understand how to detect and defend against common vulnerabilities.
- Propose and implement effective security remediations.

## 💻 Virtual Lab Environment

| Machine          | Role              | Description                                                                 |
|------------------|-------------------|-----------------------------------------------------------------------------|
| **Kali Linux**    | Attacker Machine  | Advanced penetration testing distribution for security professionals.       |
| **Metasploitable**| Target Machine    | Vulnerable Linux VM designed for testing and training in cybersecurity.     |

## 🛠️ Tools Used

- [Nmap](https://nmap.org) – Network discovery and security auditing  
- [Metasploit Framework](https://www.metasploit.com) – Exploitation framework  
- [John the Ripper](https://www.openwall.com/john/) – Password cracking  
- Metasploitable2 – Vulnerable target environment  

## 📋 Tasks Breakdown

### 1. 🔍 Network Scanning
- Detect live hosts and open ports:
  ```bash
  nmap -v 192.168.112.1/24
2. 🕵️ Reconnaissance
Hidden port scan:

bash
Copy
Edit
nmap -v -p- 192.168.112.1
Service version detection:

bash
Copy
Edit
nmap -v -sV 192.168.112.1
OS detection:

bash
Copy
Edit
nmap -v -O 192.168.112.1
3. 📑 Enumeration
Operating System: Linux 2.6.9 - 2.6.33

MAC Address: 00:0C:29:5D:FE:0B

Device Type: General purpose

Common open services include:

FTP (vsftpd 2.3.4)

SSH (OpenSSH 4.7p1)

Telnet, SNTP, HTTP, Apache, Samba, MySQL, PostgreSQL, VNC, X11

Hidden ports include services like Ruby DRb, RMI Registry, nlockmgr

4. 💣 Exploitation
Exploiting FTP backdoor (vsftpd 2.3.4):
Exploit module: exploit/unix/ftp/vsftpd_234_backdoor

Exploiting R services: ports 512, 513, 514

Exploiting Samba trans2open vulnerability:
Exploit module: exploit/linux/samba/trans2open

5. 🔐 Privilege Escalation
Add a new root user:

bash
Copy
Edit
adduser newuser1
View credentials:

/etc/passwd

/etc/shadow

Example hash:

perl
Copy
Edit
newuser1:$1$M/R1KkTD$XGDnXXTvygtDeyM3JiDlU0:20224:0:99999:7:::
6. 🔓 Password Cracking
Save hash to a file (e.g., hash.txt)

Crack with John the Ripper:

bash
Copy
Edit
john hash.txt
john --show hash.txt
7. 🛠️ Remediation Recommendations
Issue	Risk Level	Remediation
vsftpd 2.3.4	High	Upgrade to version 3.0.5
OpenSSH 4.7p1	Medium	Update to OpenSSH 9.6 or latest stable version
Java RMI open to public	High	Disable or restrict using firewall rules
Samba outdated	High	Upgrade to patched version

📚 Key Learnings
Practical use of Nmap for scanning and enumeration.

Service exploitation using Metasploit.

Creating users and cracking hashes using John the Ripper.

Critical thinking around cybersecurity defense and remediation.
