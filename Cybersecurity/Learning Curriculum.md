```toc
```
# Monthly Topic Focus
> The Goal of this sections is to organize what topics to focus for each month, to learn as much TTPs and Tools for each month. This doesn't mean that I won't be learning another stuff, it only indicates that I will focus on a specific topic as a goal per day and if I have time, learn some other stuff as well. This is in preparation for next year's Hack4Gov Capture the Flag

CTF Focus Areas: **Web Exploitation**, **Digital Forensics**, **Cryptography**, **Pwning**, **Binary Exploitation and Reverse Engineering**
[Use this as a Guide for any Blue Team Training](https://d2y9h8w1ydnujs.cloudfront.net/BTL1Syllabus.pdf)

- [x] November - Web Application Security
- [ ] December - Digital Forensics w/ (Steganography OSINT)
- [ ] January -  Cryptography, Network Security
- [ ] February - Reverse Engineering, Binary Exploitation
- [ ] March - Pwn(Own), Attacking Machines
- [ ] April - Security Analyst, Security+
- [ ] May - Blue Team Operations, Incident Handling, Threat Intelligence & Hunting
- [ ] June - Cyberdefenders, Blueteamlabs, pentester lab, tryhackme, hackthebox practice
---
## Foundational Topics
- [x] What are Capture the Flags?
- [x] Set up you Virtual Machine(Ubuntu, Kali Linux, or other) in VirtualBox
- [x] Basic Linux Commands
- [x] Basic Linux Tools Used for CTF
- [x] Network Fundamentals
- [ ] Windows Filesystem
- [ ] Linux File system
- [x] How TCP Handshake works
- [ ] How Domain Name System works
- [x] How HTTP works
- [x] How cookies work
- [x] How does Symmetric work
- [x] Asymmetric Cryptography work
- [x] How does Hashing and Hashin+Salt work
- [x] How DHCP works
- [ ] Bash Scripting
- [ ] Powershell Scripting
- [ ] PHP Programming
- [ ] What are YARA Rules? How to Create and User them

---
## Basic Skills to learn
- [x] How to use the Strings tool in Linux
- [ ] How to use NMAP for mapping a network
- [x] How to use ssh
- [x] How to use wget
- [x] How to use Burpsuit
- [ ] How to use Regular Expression
- [ ] How to use John the Ripper
- [ ] The Metasploit Framework (Host & Network Penetration Testing)
---
## Web Application Security
- [x] Introduction to Web Security
- [x] Intro to the HTTP protocol
- [x] How does a web session work
- [ ] Cross-Site Scripting (XSS) Lecture
- [ ] How to and Do some Cross-Site Scripting (XSS) Challenges
- [x] SQL Injection Lecture
- [ ] How to and Do some SQL Injection Challenges
- [x] How does Command Injection Work and Do some challenges
- [ ] How does Cross-Site Request Forgery(CSRF) work and do some challenges
- [ ] How does Session Hijacking Work
- [ ] JSON Web Tokens
- [x] Cookie Based Authentication
- [x] File Inclusion Vulnerabilities
- [x] Server-Side Request Forgery(SSRF) how it works
- [ ] What is Cross-Origin Resource Sharing and how does it work
- [ ] What is XML external entity (XXE) injection
- [ ] What is HTTP request Smuggling 
- [ ] What is HTTP Basic Authentication
- [x] Content discovery, How to discover hidden/private content in a webserver
- [x] How does Insecure Direct Object Reference(IDOR)
- [ ] Research about OWASP Top 10 vulnerabilities
#### Learning Resources
- [ ] https://www.hacksplaining.com/lessons
#### Notes
- [[SQL Injection]]
- [[Authentication Vulnerabilities]]
- [[OS Command Injection]]
- [[Standard Files on Websites]]
- [[File Upload Vulnerabilities]]
- [[Path Traversal]]
- [[Server-side request forgery]]
#### Tools to learn
- [ ] Dirbuster
- [ ] Apache2
- [x] Burpsuit
- [ ] Zap

---
## Digital Forensics
### Windows Forensics
- [ ] Registry Structure and Function, and Analyze Registry Hives
- [ ] Event logs and Auditing 
- [ ] Windows Kernel Architecture
- [ ] Windows Architecture
- [ ] File & Disk Analysis
- [ ] Learn file systems(FAT, exFAT, NTFS)
- [ ] Windows File System
- [ ] How to use Foremost
- [ ] Understanding Windows Process Structure
- [ ] Windows Security Models
- [ ] User Account Management

### Linux Forensics
- [ ] File System(Ext4, XFS, ZFS)
- [ ] Log Files(Syslog, authlogs) and analysis and interpretation of those files
- [ ] User Account management(User Accounts, groups, permissions)
- [ ] Pluggable Authentication Module(PAM)
- [ ] Bash Scripting


### Network Forensics
- [ ] System & Network Forensics
- [ ] Packet Analysis
- [ ] Packet headers
- [ ] How to use Wireshark
- [ ] How to make a packet using scappy


### Memory Analysis
- [ ] User and Kernel Modes
- [ ] Processes, Threads and services
- [ ] System Calls
- [ ] How to collect artifacts on Memory
- [ ] Memory Forensics
- [ ] Pagefile analysis
- [ ] Process and Kernel Memory
- [ ] How to create memory dumps for analysis
- [ ] Identifying running processes
- [ ] Extracting information about the loaded modules
- [ ] Examining network connections in memory
- [ ] Analyzing process memory
- [ ] Identifying threads and their states
- [ ] Identifying open file handles
- [ ] Analyzing loaded DLLs and shared libraries
- [ ] Extracting information from the registry in memory
- [ ] Analyzing file system structure in memory

### Other DFIR skills
- [ ] Linux File System
- [ ] How to collect artifacts on Disk
- [ ] Artifact Acquisition on systems(network, file, memory, etc)
- [ ] Log Analysis, Timelines and Reporting

#### Notes:
- [[Windows Architecture]]

#### Tools to learn
- [ ] xxd
- [ ] Binwalk
- [ ] Steghide
- [ ] fcrackzip
- [ ] FTK
- [ ] Autopsy
- [ ] Volitility
- [ ] EnCase

#### Resources
- [Stego Checklist](https://stegonline.georgeom.net/checklist)

---
## Network Security
- [ ] DNS Hierarchy
- [ ] How to analyze a packet
- [ ] How to analyze a Network
- [ ] Learn about Secure Network Architecture
- [ ] What is and how to use NMAP
- [ ] Learn In-dept about the structure of the Packet
- [ ] GPS Spoofing
- [ ] Information Gathering (Assessment Methodologies)
- [ ] Footprinting & Scanning (Assessment Methodologies)
- [ ] Enumeration (Assessment Methodologies)
- [ ] Vulnerability Assessment (Assessment Methodologies)
- [ ] Auditing Fundamentals (Assessment Methodologies)
- [ ] System/Host Based Attacks (Host & Network Penetration Testing)
- [ ] Network-Based Attacks (Host & Network Penetration Testing)
- [ ] Exploitation (Host & Network Penetration Testing)
- [ ] Post-Exploitation (Host & Network Penetration Testing)
- [ ] Social Engineering (Host & Network Penetration Testing)
#### Do these challenges
- https://www.vulnhub.com/
#### Tools to learn
- [ ] Zeek
- [ ] Wireshark
- [ ] Brim Security

---
## Cryptography
- [ ] Common Encryption Algorithms 
- [ ] How to use Hashcat
#### Do These Challenges after learning the basics of Cryptography
- [Cryptography Programming Challenges](https://cryptopals.com/)
### Learning Resources
- https://cryptohack.org/ - awesome hands-on introduction to cryptography.
- https://cryptohack.org/courses/
---
## Reverse Engineering && Exploitation
- [ ] Learn about the fetch, decode and execute cycle
- [ ] What are Registers
- [ ] How to use ldd
- [ ] What is Executable and Linkable Format
- [ ] How to use readelf
- [ ] Learn how to use gdb
- [ ] Learn some general and special purpose Registers
- [ ] Parts of the CPU
- [ ] Learn some x86 assemble
- [ ] Learn to read malware code in C
- [ ] Learn to read malware code in Python
- [ ] Learn to read malware code in Powershell
- [ ] Learn to read malware code in Bash
- [ ] Learn some basics in Binary Exploitation
- [ ] Learn about shellcode and how to create them

#### Do These Challenges before moving on to assembly
- [C Assignments](https://github.com/h0mbre/Learning-C/tree/master/Assignment-22)
### Learning Resources
- [x86-64 Assembly Crash Course](https://pwn.college/cse365-f2023/assembly-crash-course)
- [Basics of GDB](https://github.com/hoppersroppers/nightmare/blob/master/modules/02-intro_tooling/gdb-gef/readme.md)
- https://exploit.education/

---
## Security Analyst, Security+



## Incident Response

## Threat Intelligence, Management & Hunting
- [ ] How to Collect logs from End Devices and the Network
- [ ] 

#### Resrouces
- [Go to the 1.0 Threat Management Section](https://www.comptia.jp/pdf/comptia-cybersecurity-analyst-(cs0-001).pdf)

## Practice Sites
- Cyberdefenders.org
- BlueTeamLabsOnline
- Tryhackme
- picoctf
- rootme.org
- overthewire.org
- 
