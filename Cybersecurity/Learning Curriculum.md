```toc
```
# Monthly Topic Focus
> The Goal of this sections is to organize what topics to focus for each month, to learn as much TTPs and Tools for each month. This doesn't mean that I won't be learning another stuff, it only indicates that I will focus on a specific topic as a goal per day and if I have time, learn some other stuff as well. This is in preparation for next year's Hack4Gov Capture the Flag

CTF Focus Areas: **Web Exploitation**, **Digital Forensics**, **Cryptography**, **Pwning**, **Binary Exploitation and Reverse Engineering**
[Use this as a Guide for any Blue Team Training](https://d2y9h8w1ydnujs.cloudfront.net/BTL1Syllabus.pdf)

- [x] November - Web Application Security
- [x] December - Digital Forensics w/ (Steganography OSINT)
- [ ] January -  Cryptography, Network Security
- [ ] February - Reverse Engineering, Binary Exploitation
- [ ] March - Pwn(Own), Attacking Machines
- [ ] April - Security Analyst, Security+, DFIR
- [ ] May - Blue Team Operations, Incident Handling, Threat Intelligence & Hunting
- [ ] June - Cyberdefenders, Blueteamlabs, pentester lab, tryhackme, hackthebox practice
---
## Foundational Topics
- [x] What are Capture the Flags?
- [x] Set up you Virtual Machine(Ubuntu, Kali Linux, or other) in VirtualBox
- [x] Basic Linux Commands
- [x] Basic Linux Tools Used for CTF
- [x] Network Fundamentals
- [x] Windows Filesystem
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
- [x] How to use NMAP for mapping a network
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
- [x] Cross-Site Scripting (XSS) Lecture
- [ ] How to and Do some Cross-Site Scripting (XSS) Challenges
- [x] SQL Injection Lecture
- [ ] How to and Do some SQL Injection Challenges
- [x] How does Command Injection Work and Do some challenges
- [ ] How does Cross-Site Request Forgery(CSRF) work and do some challenges
- [x] How does Session Hijacking Work
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
- [x] Research about OWASP Top 10 vulnerabilities
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
- [x] Windows File System
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
- [x] How to use Wireshark
- [x] How to make a packet using scappy


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
- [x] xxd
- [x] Binwalk
- [x] Steghide
- [ ] fcrackzip
- [ ] FTK
- [ ] Autopsy
- [ ] Volitility
- [ ] EnCase

#### Resources
- [Stego Checklist](https://stegonline.georgeom.net/checklist)
- [Windows Forensics handbook via gitbook](https://psmths.gitbook.io/windows-forensics/)

---
## Network Security
- [ ] DNS Hierarchy
- [ ] Intrusion Detection System & Intrusion prevention system
- [x] How to analyze a packet
- [ ] Types of attackers and their motivations
- [x] What are digital signatures
- [x] Public Key Infrastructure
- [ ] DES, AES, RSA, ECC
- [ ] Key management and exchange
- [x] Defense-in-depth strategy
- [ ] Packet filtering vs. stateful inspection
- [ ] Intrusion Detection Systems and Intrusion Prevention Systems
- [ ] Single Sign-On (SSO)
- [ ] S/MIME, PGP
- [ ] Role-based access control (RBAC) and Access Control
- [ ] IPSec, SSL/TLS
- [x] VPN types: Site-to-Site, Remote Access
- [ ] WEP, WPA, WPA2, WPA3
- [ ] 802.1X and EAP
- [ ] Configuring ACLs
- [ ] VLAN security
- [ ] Web proxies
- [ ] Content filtering techniques
- [x] How to analyze a Network
- [ ] Learn about Secure Network Architecture
- [x] What is and how to use NMAP
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
- [List of things to learn for eJPT](https://medium.com/@polygonben/ejpt-a-guide-on-how-to-pass-first-time-f8cec3f79a73)
#### Tools to learn
- [ ] Zeek
- [x] Wireshark
- [ ] Brim Security

---
## Cryptography
- [x] Common Encryption Algorithms 
- [ ] How to use Hashcat
- [x] What is Public Key Encryption?
### Module 1: Introduction to Cryptography

- **Week 1-2: Basics of Cryptography**
    - [x] Historical context and evolution of cryptography
    - [x] Fundamental concepts: confidentiality, integrity, availability
    - [x] Types of cryptography: symmetric vs. asymmetric
    - [x] Substitution ciphers
    - [x] transposition ciphers
    - [x] Break classical ciphers
- **Week 3-4: Cryptographic Building Blocks**
    - [x] Hash functions and their applications
    - [ ] Symmetric key encryption algorithms
	    - [ ] DES
	    - [ ] AES
	    - [x] Hash Functions(MD5, SHA-2, SHA-3)
	    - [ ] Block vs stream ciphers
	    - [ ] Modes of operation
	    - [ ] Cryptographic hash functions vs. non-cryptographic hash functions
    - [ ] Asymmetric key encryption algorithms
	    - [ ] RSA Algorithm
	    - [ ] ElGamal encryption
	    - [ ] Digital Signatures and their application
	    - [ ] Basics of elliptic curves
	    - [ ] ECC vs RSA

### Module 2: Cryptographic Protocols and Applications

- **Week 5-6: Secure Communication Protocols**
    - [x] SSL/TLS protocols
    - [ ] VPNs and their cryptographic foundations
    - [ ] Email encryption (PGP/GPG)
- **Week 7-8: Public Key Infrastructure (PKI)**
    - [x] Certificate authorities
    - [ ] X.509 certificates
    - [ ] Digital signatures and their verification

### Module 3: Cryptanalysis and Attack Techniques

- **Week 9-10: Cryptanalysis Techniques**
    
    - [x] Brute-force attacks
    - [x] Frequency analysis
    - [ ] Differential and linear cryptanalysis
- **Week 11: Side-Channel Attacks**
    
    - [ ] Timing attacks
    - [ ] Power analysis
    - [ ] Fault injection attacks

### Module 4: Cryptography in Malware Analysis and CTFs

- **Week 12: Application of Cryptography in Security and CTFs**
    - [ ] Cryptography in malware communication
    - [ ] Solving cryptographic challenges in CTFs
    - [ ] Real-world case studies and practical exercises
#### Do These Challenges after learning the basics of Cryptography
- [Cryptography Programming Challenges](https://cryptopals.com/)
- [Krypton Cryptography Wargames](https://overthewire.org/wargames/krypton/)
### Learning Resources
- https://cryptohack.org/ - awesome hands-on introduction to cryptography.
- https://cryptohack.org/courses/
---
## Reverse Engineering & Binary Exploitation
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

### Module 1: Binary Analysis and Tools
- [ ] Common Binary file formats (PE, ELF)
- [ ] Ghidra and other disassembly tools
- [ ] converting machine code to higher-level languages
- [ ] Dynamic Analysis using debuggers (GDB, WinDbg)
- [ ] Breakpoints, watchpoints, dynamic analysis tools

### Module 2: Assembly Language Basics
- [ ] Introduction to CPU architectures(x86 and ARM)
- [ ] Registers, instructions, and other addressing modes
- [ ] Control flow analysis

### Module 3: Malware Analysis
- [ ] Dynamic Malware Analysis
	- [ ] Behavior analysis using sandboxing
	- [ ] API hooking and monitoring
- [ ] Static Malware Analysis
	- [ ] Signature-based detection
	- [ ] Code and data analysis
### Module 5: Software Reverse Engineering
- [ ] Analyzing compiles software
- [ ] Recovering high-level design information
- [ ] Binary patching techniques
- [ ] Understanding and modifying application behavior

### Module 6: Network Protocol Analysis
- [ ] Identifying protocols and understanding data flow
- [ ] Analyzing proprietary protocols
- [ ] Creating protocol specification



#### Do These Challenges before moving on to assembly
- [C Assignments](https://github.com/h0mbre/Learning-C/tree/master/Assignment-22)i
- [Basic DSA in C](https://olympus.mygreatlearning.com/courses/14560/pages/linked-list?module_item_id=647846)
- [Blue Team Labs Online Reverse Engineering Challenges](https://blueteamlabs.online/home/challenges)
- [Learn DSA, use C for practice](https://www.educative.io/courses/visual-introduction-to-algorithms/what-is-an-algorithm-and-why-should-you-care)
- [Basic Exploitation](https://overthewire.org/wargames/narnia/)
- [Unix Stuff](https://overthewire.org/wargames/leviathan/)
- [Complete this master C programiz interactive course](https://app.programiz.pro/course-content/learn-c-programming)
### Learning Resources
- [x86-64 Assembly Crash Course](https://pwn.college/cse365-f2023/assembly-crash-course)
- [Basics of GDB](https://github.com/hoppersroppers/nightmare/blob/master/modules/02-intro_tooling/gdb-gef/readme.md)
- https://exploit.education/
- [Open Security: Introduction to GDB](https://p.ost2.fyi/courses/course-v1:OpenSecurityTraining2+Dbg1012_GDB_1+2021_v1/courseware/769676b3dc9a4af8838261090e69fa8c/553a2d118bb243ee9c1f39492bdc458e/?child=first)
- [LetsDefend Malware Analysis and RE](https://app.letsdefend.io/training)
- [Intro Malware Analysis Part 1 | Blog](https://intezer.com/blog/malware-analysis/malware-reverse-engineering-beginners/?fbclid=IwAR3PWi_zFkuETgn0nc6kj9vZN6UAkF9WTdm8hxkBzbmA2UHWFBkepluec1I)
- [Intro to Malware Analysis Part 2 | Blog](https://intezer.com/blog/incident-response/malware-reverse-engineering-for-beginners-part-2/?fbclid=IwAR3QYD20wCg-tHbr9EmJACRkHm4O6pP0t-qhhiP4SZfXH44IRfcgKVTE_XA)

---
## Security Analyst, Security+
### Module 1: Introduction to Cybersecurity

- [x] Overview of Cybersecurity
- [x] Importance of Cybersecurity
- [ ] Common Cyber Threats
- [ ] Cybersecurity Frameworks (NIST, ISO/IEC 27001)

### Module 2: Networking Fundamentals

- [x] OSI Model
- [x] TCP/IP Protocol Suite
- [x] Network Devices and Security
- [x] Subnetting and IP Addressing

### Module 3: Operating System Security

- [ ] Windows Security
- [ ] Linux Security
- [ ] macOS Security

### Module 4: Cyber Threats and Attack Vectors

- [ ] Malware (Types, Detection, Prevention)
- [ ] Social Engineering Attacks
- [ ] Phishing and Email Security
- [ ] Man-in-the-Middle Attacks
- [ ] Denial of Service (DoS) and Distributed Denial of Service (DDoS) Attacks

### Module 5: Web Application Security

- [ ] OWASP Top Ten
- [ ] Common Web Application Vulnerabilities
- [ ] Secure Coding Practices
- [ ] Web Application Firewalls (WAF)

### Module 6: Cryptography

- [ ] Encryption Algorithms
- [x] Hash Functions
- [ ] Public Key Infrastructure (PKI)
- [x] Digital Signatures
- [x] Certificate Authorities

### Module 7: Security Assessment and Penetration Testing

- [ ] Vulnerability Assessment
- [ ] Penetration Testing Methodologies
- [ ] Tools (Nmap, Metasploit, Burp Suite)
- [ ] Reporting and Remediation

### Module 8: Incident Response and Forensics

- [ ] Incident Response Lifecycle
- [ ] Forensic Analysis Techniques
- [ ] Chain of Custody
- [ ] Evidence Handling and Preservation

### Module 9: Security Policies and Compliance

- [ ] Developing Security Policies
- [ ] Regulatory Compliance (GDPR, HIPAA, PCI DSS)
- [ ] Security Awareness Training
- [ ] Risk Management

### Module 10: Network Security

- [ ] Firewalls and Intrusion Detection/Prevention Systems (IDS/IPS)
- [ ] VPNs and Secure Network Design
- [ ] Wireless Network Security

### Module 11: Cloud Security

- [ ] Cloud Computing Overview
- [ ] Cloud Security Architecture
- [ ] Identity and Access Management (IAM)
- [ ] Data Security in the Cloud

### Module 12: Security Monitoring and SIEM

- [ ] Security Information and Event Management (SIEM)
- [ ] Log Management
- [ ] Security Incident Monitoring
- [ ] Threat Intelligence

### Module 13: Endpoint Security

- [ ] Antivirus and Anti-malware Solutions
- [ ] Endpoint Detection and Response (EDR)
- [ ] Mobile Device Security

### Module 14: Legal and Ethical Considerations

- [ ] Cybersecurity Laws and Regulations
- [ ] Ethical Hacking and Responsible Disclosure
- [ ] Privacy and Data Protection

### Module 15: Professional Development and Certifications

- [ ] Industry-recognized Certifications (e.g., CISSP, CompTIA Security+, CEH)
- [ ] Continuous Learning and Professional Growth

### Learning Resources
- [Letsdefend Learn](https://app.letsdefend.io/training)
- [Letsdefend Practice Scenario of Being a analyst](https://app.letsdefend.io/monitoring)
- [Letsdefend Challenges and Blue Team CTF](https://app.letsdefend.io/challenge)
- [Checklist of things to learn](https://d2y9h8w1ydnujs.cloudfront.net/BTL1Syllabus.pdf)

## Hardware Security
### Module 1: Introduction to Embedded Systems
- [x] Definition and characteristics of embedded Systems
- [x] Examples of embedded systems in real-world applications
- [ ] Microcontrollers vs Microprocessors
- [x] Memory Hierarchy(RAM, ROM, Flash)
- [x] I/O devices and interfaces
- [ ] Embedded System Development Process
	- [ ] Requirement Analysis
	- [ ] System Design
	- [ ] Hardware and software development
	- [ ] Testing and validation
### Module 2: Microcontroller Architecture and Programming
- [ ] Introduction to microcontroller and their components
- [ ] Central Processing Unit
	- [ ] Instruction set architecture
	- [ ] Pipelining and parallelism
- [ ] Different types of microcontrollers (EVR, ARM, PIC)
- [ ] Assembly Programming
- [ ] C Programming for microcontrollers
- [ ] C Pointers and memory management in embedded systems
### Module 3: Embedded System Development Tools
- [ ] Overview of cross-compilation
- [ ] Setting up a cross-compilation environment
- [ ] Debugging Techniques
	- [ ] Emulators and simulators
	- [ ] In-circuit debugging tools
	- [ ] Real-time debugging techniques
### Module 4: Real-time Operating Systems
- [ ] Introduction and characteristics of real-time OS
- [ ] Types of RTOS
- [ ] Task Scheduling algorithms
- [ ] Inter-process communication and synchronization
- [ ] RTOS Application Development
	- [ ] Creating and managing tasks
	- [ ] Handling interrupts and exceptions
### Module 5: Peripheral Interfacing
- [ ] Digital and Analog I/O
	- [ ] GPIO(General Purpose Input/Output)
	- [ ] Analog-to-digital and digital-to-analog conversion
- [ ] Serial Communication Protocols
	- [ ] UART, SPI, I2C
	- [ ] Implementing communication protocols in embedded systems
- [ ] Sensors and Actuators
	- [ ] Sensor types and principles
	- [ ] Control of actuators
### Module 6: Embedded System Networking
- [ ] Wireless Communication Protocols (Bluetooth, WiFi)
- [ ] Connecting embedded systems to the internet
- [ ] IoT protocols and frameworks

## Incident Response

## Threat Intelligence, Management & Hunting
- [ ] How to Collect logs from End Devices and the Network
- [ ] 

## Windows Malware Development 
- [Windows Kernel Internals](https://www.codemachine.com/trainings/kerint.html)
- [Windows Kernel Rootkit](https://www.codemachine.com/trainings/kerrkt.html)
#### Resrouces
- [Go to the 1.0 Threat Management Section](https://www.comptia.jp/pdf/comptia-cybersecurity-analyst-(cs0-001).pdf)



## Practice Sites
- Cyberdefenders.org
- BlueTeamLabsOnline
- Tryhackme
- picoctf
- rootme.org
- overthewire.org
- letsdefend


