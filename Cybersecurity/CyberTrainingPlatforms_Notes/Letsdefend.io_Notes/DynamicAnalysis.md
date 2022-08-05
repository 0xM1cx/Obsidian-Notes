```toc
```

## What is Dynamic Malware Analysis?
Dynamic malware is an analysis method in which malware is run and examined in secure environments. This method is aimed at analyzing the behavior of malware by examining the activities like, network, and file, etc. in secure environments.

This analysis method is widely preferred by SOC analysts, as it a faster than static analysis method. Various sandbox solutions are available to automate the dynamic analysis. **Sandboxes** run the malware in their own isolated environments and automatically present the analysis results.

### Advantages of the Dynamic Analysis Method
- It produces much faster results than the static analysis method.
- You can perform automated analysis with sandboxes.
- It is an analysis method that requires less technical knowledge than static analysis, so beginners can learn easily.

### Disadvantages of the Dynamic Analysis Method
- You cannot determine the full malware capacity, as the behavior of the malware may vary from different systems.
- You cannot usually analyze advanced malware with the dynamic analysis method alone, in these cases you may need to use both dynamic and static analysis together.

---
## What is the Importance of Dynamic Malware Analysis for SOC Analysts?
If you ask a SOC analyst about what they do at work, one of the things you may probably hear will be that "I am analyzing suspicious files".

Malware analysis is one of the most important tasks of SOC. A cybersecurity professional will work with malware in their daily life.

As a SOC analyst, you are racing against time. The faster you can detect a harmful situation, the faster you can take action against it. SOC analysts first prefer the dynamic analysis method since it can produce much faster results than the static analysis.

Dynamic analysis which can be summarized as "run the malware and examine its activities", may look easy, but it is a very difficult and dangerous analysis method for a person who does not know what he is doing.

---
## What tools and software do we need for Dynamic Analysis?

### Virtualization Software
You don't want to conduct dynamic analysis on you own system as we need to run the malware to be able to examine its features. This is why virtualization software are used.

With these software, you can use different OS that fit you analysis environment requirements. If the virtual machines are configured properly, then you can perform the analysis safely. As malware cannot escape from the Virtual OS that you have configured.

Some of the most used virtualization software are:
- VMware Workstation
- VMware Fusion
- Oracle Virtualbox

The dynamic analysis environment should be completely separate physical device and a separate network. However, setting up this complex environment is very costly and unnecessary.

### Utility Software
After installing and configuring your virtual OS, you need to install software that will be useful in dynamic analysis. Example, we cannot perform dynamic analysis is suspicious files with a file extension of docx, xlsx without installing Microsoft Office or other similar and compatible software on the system.

Example of Utility Software to install:
- MS Office
- Adobe Reader
- Browser(Chrome, Opera, Firefox, etc.)
- WinRAR
- Text Editors (sublime, atom, etc.)

### Debuggers
**Debuggers** are software that are generally used by programmers to test the code and catch errors. These software help to see the instructions of a process and change the flow of the program.

Malware analysts use debuggers to learn the malware's working structure and disable some prevention features by modifying the code. 

For example, suppose you want to investigate a malware that does not function when the device name is not "Shawn" You can disable this control with the Debugger by making changes to the codes in which it is implemented, ensuring that the malware continues to run.

Some debuggers that are frequently preferred by malware analyst are as follows.
- Ollydbg
- X64dbg
- Windbg
- Radare2

### Network Monitoring Tools
Information such as the network connections by the malware, the addresses it communicates with and how it communicates with those should be reported as a result of the malware analysis. Software to detect these network activities:
- Wireshark
- Fiddler
- Burp Suite

### Process Monitoring Tools
A new process is created for the program we run for malware analysis. In order to monitor these processes, we should use process monitoring tools.

Windows already comes with a process monitoring tools called **"Task Manager"**. However, other process monitoring tools are more useful in terms of usage and features for malware analysis.
- Process Hacker
- Process Explorer (SysInternals)
- Procmon (SysInternals)

### File Activity Monitoring Tools
Malware can read files to collect information from the OS, write other components of the malware to the file system, and move itself to the startup folder to ensure persistence. Malware can be involved in various activities in the file system. We should detect and indicate these activities in the malware analysis report.
- Sysmon

### Other Tools
- SysInternal Tools
- CFF Explorer
- PEView
- TriDNet
- BinText
- PEiD
- Regshot
- HashMyFiles
---
## Tweaking Virtual Machine
### 1. Turn off anti-malware programs
Since we will be analyzing malware on our VM, we do not want the antivirus software to delete the malware we have installed for analysis. We should turn off Windows defender which comes pre-installed and active by default on Windows.


