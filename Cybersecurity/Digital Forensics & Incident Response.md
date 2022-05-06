# Topics
+ [[Basics of Digital Forensics]]
+ [[Windows File System]]
+ [Memory Forensics](/Cybersecurity/Memory Forensics)


# Tools and Distros
-  [Oracle VirtualBox](https://www.virtualbox.org/)
-   [Flare VM](https://www.fireeye.com/blog/threat-research/2017/07/flare-vm-the-windows-malware.html)* (Comes with several [DFIR/Malware Analysis tools](https://github.com/fireeye/flare-vm) installed)
-   [Security Onion](https://securityonion.net/)
-   [Kali Linux](https://www.kali.org/)
-   [CSI Linux](https://csilinux.com/) (Comes with several [OSINT/DFIR/Malware Analysis tools](https://csilinux.com/features.html) installed)
-   [Remnux](https://remnux.org/) (Comes with several [malware analysis tools](https://zeltser.com/remnux-tools-list/) installed)
-   [Tsurugi Linux](https://tsurugi-linux.org/) (Comes with several [OSINT/DFIR/Malware Analysis tools](https://tsurugi-linux.org/documentation_tsurugi_linux_tools_listing.php#) installed)
-   [SANS SIFT](https://digital-forensics.sans.org/community/downloads) (ova format – comes with several DFIR tools installed)
-   [Alienvault OSSIM](https://cybersecurity.att.com/products/ossim)
-   [The Hive Project (Training VM)](https://github.com/TheHive-Project/TheHiveDocs/blob/master/training-material.md)
-   [Autopsy](https://www.sleuthkit.org/autopsy/)
-   [FTK Imager](https://accessdata.com/product-download)
-   [CurrPorts](https://www.nirsoft.net/utils/cports.html)
-   [Wireshark](https://www.wireshark.org/) (You can find sample PCAP files [here](https://wiki.wireshark.org/SampleCaptures))
-   [Dependency Walker](http://www.dependencywalker.com/)
-   [pestudio](https://www.winitor.com/)
-   [Structured Storage Viewer](https://www.mitec.cz/ssv.html)

*In addition to tools, Flare VM also contains lab files for the [Practical Malware Analysis](https://nostarch.com/malware) book.

## More tools and Resources
- [Startme](https://start.me/p/q6mw4Q/forensics)
- [Awesome Malware Analysis](https://github.com/rshipp/awesome-malware-analysis) – A curated list of malware analysis tools and resources.
- [Awesome Incident Response](https://github.com/meirwah/awesome-incident-response) – A curated list of tools for incident response.
- [Awesome Forensics](https://github.com/Cugu/awesome-forensics) – A curated list of forensic analysis tools and resources.
- [DFIR Training](https://www.dfir.training/tools-sw-hw) – DFIR software and hardware database
- [DFIR Learning Platform](https://www.iblue.team/linux-forensics/linux)

# CTF and Forensics Challenges
- https://www.amanhardikar.com/mindmaps/ForensicChallenges.html
- [Memlabs Memory CTFs; see this page to get the instructions about the challenge.](https://github.com/stuxnet999/MemLabs)


## Incident Response
An **_incident_** usually refers to a data breach or cyber attack; however, in some cases, it can be something less critical, such as a misconfiguration, an intrusion attempt, or a policy violation. Examples of a cyber attack include an attacker making our network or systems inaccessible, defacing (changing) the public website, and data breach (stealing company data). How would you **_respond_** to a cyber attack? Incident response specifies the methodology that should be followed to handle such a case. The aim is to reduce damage and recover in the shortest time possible. Ideally, you would develop a plan ready for incident response.

The four major phases of the incident response process are:

1.  **Preparation**: This requires a team trained and ready to handle incidents. Ideally, various measures are put in place to prevent incidents from happening in the first place.
2.  **Detection and Analysis**: The team has the necessary resources to detect any incident; moreover, it is essential to further analyze any detected incident to learn about its severity.
3.  **Containment, Eradication, and Recovery**: Once an incident is detected, it is crucial to stop it from affecting other systems, eliminate it, and recover the affected systems. For instance, when we notice that a system is infected with a computer virus, we would like to stop (contain) the virus from spreading to other systems, clean (eradicate) the virus, and ensure proper system recovery.
4.  **Post-Incident Activity**: After successful recovery, a report is produced, and the learned lesson is shared to prevent similar future incidents. ![[Pasted image 20220506165905.png]]

## Malware Analysis
*Link for resources/tools by malwareuncorn*: https://malwareunicorn.org/#/resources
Malware stands for malicious software. _Software_ refers to programs, documents, and files that you can save on a disk or send over the network. Malware includes many types, such as:

-   **Virus** is a piece of code (part of a program) that attaches itself to a program. It is designed to spread from one computer to another; moreover, it works by altering, overwriting, and deleting files once it infects a computer. The result ranges from the computer becoming slow to unusable.
-   **Trojan Horse** is a program that shows one desirable function but hides a malicious function underneath. For example, a victim might download a video player from a shady website that gives the attacker complete control over their system.
-   **Ransomware** is a malicious program that encrypts the user’s files. Encryption makes the files unreadable without knowing the encryption password. The attacker offers the user the encryption password if the user is willing to pay a “ransom.”

Malware analysis aims to learn about such malicious programs using various means:

1.  **Static analysis** works by inspecting the malicious program without running it. Usually, this requires solid knowledge of assembly language (processor’s instruction set, i.e., computer’s fundamental instructions).
2.  **Dynamic analysis** works by running the malware in a controlled environment and monitoring its activities. It lets you observe how the malware behaves when running.