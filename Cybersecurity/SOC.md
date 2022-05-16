# Introduction to SOC
> Revisite the Topics below on the LetsDefend SOC environment to get hands-on experience.
## The Structure of a SOC
##### What is a SOC?
A Security Operation Center (SOC) is the facility where the information security team constantly monitors and analyzes the security of an organization. The main purpose of the SOC team is to detect, analyze and respond to cyber security incidents by using technology, people and processes.

###### Types of SOC Models
Depending on security requirements and budget, there are several types of SOC:

**In-house SOC**
The enterprise builds its own cybersecurity team. Firms considering establishing an internal SOC should have a budget to support continuity.

**Virtual SOC**
The security team does not have its own facility and often works remotely in different locations.

**Co-Managed SOC**
The Co-Managed SOC consists of internal SOC personnel working with an external Managed Security Service Provider (MSSP). The coordination is really important for this type of model.

**Command SOC**
A senior group that oversees smaller SOCs in a large region. Organizations using this model include major telecom providers and defense agencies.

###### People, Process and Technology
Building a successful SOC requires serious coordination. In particular, there should be a strong relationship between people, processes, and technologies.

In simple terms, we will talk about which people, processes and technologies are required for SOC.

**People**
We need highly trained personnel familiar with security alerts and attack scenarios. As attack types are constantly changing, we need a teammate that can easily adapt to new attack types and is willing to research.
 
**Processes**
To bring your SOC structure to good maturity, you need to align it with many different types of security requirements such as NIST, PCI, HIPAA. Processes require extreme standardization of actions to ensure nothing is skipped.  
   
**Technology**
You need to have various products for many topics such as penetration test, detection, prevention, analyze. You need to follow the market and technology closely to find the best solution for you. Sometimes the best product on the market may not be the best for you. This may be due to your low budget.

###### SOC Positions
**Soc Analyst**
It can be divided into groups as Level 1, 2 and 3 according to the SOC structure. A security analyst classifies the alert, looks for the cause, and advises on remedial measures.

**Incident Responder**
The incident response officer is the person who will take part in threat detection. This person performs the initial assessment of security breaches.

**Threat Hunter**
A team member whose purpose is to find vulnerabilities before the attacker can exploit them with an attack.

**Security Engineer**
Security Engineers maintain the security infrastructure of SIEM solutions and SOC products. For example, this person prepares the connection between SIEM and SOAR product.

**SOC Manager**
A SOC Manager takes on management responsibilities such as budgeting, strategizing, managing personnel and coordinating operations. He/She deals with operational rather than technical matters.

----
## The Operation of a SOC
###### The Advantages of Being a SOC Analyst
There are many various techniques of attack vectors and malicious software and they increase more and more every day. As an analyst you will get greater enjoyment from investigating these varying types of incidents. Even though the operating systems, security products…etc. that you use will be the same the job will feel less monotonous(less interesting) because you will be analyzing different incidents. Also, you may not encounter such techniques (not every week or every day).

###### General Routine
Throughout the day a SOC analyst will generally examine alerts on the SIEM and determine which ones are real threats. To reach a conclusion he will utilize various security products such as EDR, Log Management and SOAR. We will explain in detail why and how these products are used later in the training program.

To be a successful SOC analyst who is not dependent on security products and can correctly analyze SIEM alerts one needs to have the following competencies.

**Operating Systems**
To be able to detect what is abnormal in a system one must primarily know what is accepted as normal. For example, there are multiple services within the Windows operating system and it is hard to detect which of these are suspicious without knowing which are or could be normal Windows services. For this reason, you should know the basic logic of how Windows/Linux operating systems work.

**Network**
First and foremost, we will be handling many malicious IPs and URL addresses. And we will have to check if there are any devices on the network trying to connect to these addresses. If we can control this then it will set the tone of our analysis.

As a more complicated step we might have to detect a potential data leak on the network. To be able to carry out all these functions we need to know the basics of networking.


**Malware Analysis**
You will come across some kind of malicious software when dealing with most threats. In order to be able to understand what the actual purpose of these malwares are (they sometimes display different behaviors to mislead analysts) you need to have some skills in malware analysis.  

It is important to at least determine what the malicious file’s command and control center is and whether or not there is a device communicating with this address.

We have generally discussed what a SOC analyst is, what he/she does and what kind of skills he/she needs to have. As we continue with the program we will address technical areas, we will start with the SIEM.

---
## SOC Tools/Products
###### What is a SIEM?
**Security information and event management (SIEM)**, is a security solution that provides the real time logging of events in an environment. The actual purpose for event logging is to detect security threats.

In general, SIEM products have a number of features. The ones that interest us most as SOC analysts are: <u>they filter the data that they collect and create alerts for any suspicious events.</u>

Example of an alert: **If someone on a Windows operating system attempts to enter 20 incorrect passwords in 10 seconds, this is suspicious activity**, it is not likely that someone who forgot their password would try to re-enter their password so many times in such a short period. This is why we create a SIEM rule/filter, to determine such activities that exceed the threshold values. Due to this SIEM rule an alert will be created if such a situation occurs.
![[Pasted image 20220504210344.png]]
**Some popular SIEM solutions: IBM QRadar, ArcSight ESM, FortiSIEM, Splunk etc.**

**Relationship Between a SOC Analyst and SIEM**
Although SIEM solutions have many features, as SOC analysts we generally only follow alerts. There are other groups/people who develop configurations and rule correlations.

As we mentioned above, alerts are created by data that is passed through filters. The alerts are primarily analyzed by a SOC analyst. This is exactly where a SOC analyst’s duty in the security operations center begins. Fundamentally, he must decide whether this created alert is a real threat or a false alarm.

As a SOC analyst we should analyze the details related to these alerts with the help of other SOC products (such as EDR, Log Management, Threat Intelligence Feed, etc.) and lastly we should determine whether or not they are real threats.

---
## How a SOC Analyst should use his tools
### **Log Management**
You will be doing a lot of log analysis as a SOC Analyst. For this reason, it is important to be familiar with “Log Management” systems/solutions. What brand product you use is not important, rather what’s important is knowing what to look for and where to look for it.

In the continuation of this article, we will discuss how “Log Management” solutions can be effectively used by SOC Analysts.

**What is Log Management?**
As implied by its name, it is a log management solution. In short, it enables access to all the logs in an environment (web logs, OS logs, FW, PRoxy, EDR, etc.) and it allows for the management of these logs from one point. Thus, it improves usability and saves time.

If we can’t access the logs from one point, then the same query (for example I want to determine all users at letsdefend.io) would need to be sent to various devices. This would increase our margin of error and the amount of time we need to spend.

If you go to the “Log Management” page in LetsDefend, you will see various log sources such as Proxy, Exchange, and Firewall listed as “Type”. This means that all these log sources have been collected in one place and we can see log output from sources like Proxy, FW, etc. with just one query.

**Purpose of Use**

As SOC Analysts we generally use “Log Management” to check if there is communication with a certain address and to see the details of this communication. Let’s say you came across a piece of malware and after executing it you detected that it had communicated with the “letsdefend.io” address and executed commands from it. In this situation the command control center is “letsdefend.io”, you can search for “letsdefend.io” on your company’s Log Management to see if there have been any devices attempting to communicate with the command control center.  
  
  
This solution provides us with a second situation, which is: You see a SIEM alert that indicates that a LetsDefendHost device which is on your network is leaking data to the IP address 122[.]194[.]229[.]59. You conducted an investigation, you isolated the device from the network, and performed the required processes and now you are in control. But there is still something we haven’t addressed, are there any other devices sending data to the suspicious Ip address (122[.]194[.]229[.]59)? The alert may have only included LetsDefendHost but we still should search for the suspicious address on Log Management to see if there is anything the system might not have detected and try to find any connections.

### **Endpoint Detection and Response**
A SOC Analyst needs to spend a large amount of time using EDR while conducting analyses on an endpoint device. In the following sections we will discuss why EDR is beneficial for us as SOC Analysts and how we can use it effectively.

**What is EDR**
Endpoint detection and response (EDR), also known as endpoint threat detection and response (ETDR), is an integrated endpoint security solution that combines real-time continuous monitoring and collection of endpoint data with rules-based automated response and analysis capabilities.  
(Definition source: mcafee.com)

Some popular EDR solutions used in the workplace: **CarbonBlack**, **SentinelOne**, **FireEye HX**.

**Containment**
We must isolate a hacked machine from the network. There are important reasons behind this: to be able to stop the attacker’s connection to the inner network and to prevent his movement throughout the inner network.

Therefore the device should be cut off from inner and outer networks until the security gaps are fixed and the device is usable again. We can ensure that isolation happens using the “Containment” feature of EDR solutions. This feature allows the selected device to communicate only with the EDR center. This means that even though the device is isolated from the network we can still continue our analysis.

**Quick Tip**
If you have any kind of IOC such as a file hash, file name, etc. you can perform a search in EDR among all hosts and see if there is a match. For example, let’s say you are sure that a device has been hacked and you have obtained a file with an MD5 hash of “ac596d282e2f9b1501d66fce5a451f00”. You can search for this hash value in EDR and determine whether this file is present or executed on other devices. Therefore you can understand who was affected by this attack.

### Security Orchestration Automation and Response (SOAR)
SOAR enables the security products and tools within an environment to work together and therefore makes the SOC team members' jobs easier. For example it will automatically perform a search for the source IP of a SIEM alert in Virustotal and so it lightens the load of the SOC analyst.
Some SOAR products frequently used within the industry:  
-   Splunk Phantom
-   IBM Resilient
-   Logsign
-   Demisto
![[Pasted image 20220512211255.png]]

**Benefits of SOAR**
- **Saves Time** - It saves time through workflows that automate processes. Some frequently used workflows are:
	- IP address repetition control
	- Hash query
	- Scanning an acquired file in a sandbox environment
- **Centralization** - It enables the operation of various security tool sin your environment(Sandbox, Log Management, 3rd party tools, etc) from one point. These tools are integrated into the SOAR solution and can be used on the same platform.
![[Pasted image 20220512212123.png]]
- **Playbook** - We can easily investigate SIEM alerts using playbooks created for various scenarios within SOAR. These playbooks help us conduct an analysis becuase we can follow the instructions even though we don't know or remember all the steps of the analysis.

Additionally, these playbooks help the whole SOC team to conduct their analyses on the same plane. For example, if one team member is not checking IP reputation and the others are, then this is an undesirable situation, we want all team members to check IP reputation. We can prevent this situation by adding this step to the playbook.

### Threat Inteligence Feed
A SOC team should know about the latest threats immediately and take appropriate precautions. Threat Intelligence Feeds are formed to fulfill this need. We can utilize these sources as SOC analysts when we are performing an investigation.

A Threat Intelligence Feed is data (such as malware hashes, C2 domain/IP addresses etc.) provided by a third party company.

If we look at LetsDefend’s “Threat Intel” page we can see numerous kinds of data (hash, IP etc.)
![[Pasted image 20220512213311.png]]

The data here is made up of artifacts from previous malicious activities. It could be the hash of malware or the IP address of a command and control center. As a SOC analyst, we can search threat intelligence feeds to determine whether a hash file we have in hand was ever used in a malicious scenario in the past.

**Here are some free and popular sources you could use:**
-   https://www.virustotal.com/
-   https://talosintelligence.com/

***Points We Should Pay Attention to:***

**Data that we run through feeds that does not show up**
Let’s say we ran a hash that belonged to an .exe in VirusTotal and could not find anything suspicious about it in the past. We should not suppose that the file is clean, this would be a mistake. Still, we should be diligent about performing the required file analyses (static/dynamic).

**We shouldn’t forget that IP addresses can change hands.**
For example, let’s say an attacker created a server over AWS and used it as a command and control center. Then various threat intelligence feeds recorded this IP address on their lists as a malicious address.  
   
After 2 months had passed the attacker closed the server and someone else moved their personal blog to this server. This doesn’t mean that people who visited the blog were exposed to malicious content. The fact that this IP address had been used for malicious reasons in the past does not mean that it contains malicious content.

## Frequent mistakes that SOC Analysts make
---
**If You Want To Become a SOC Analyst**
If becoming a SOC Analyst is your career goal, we advise that you especially focus on SOC tools (SIEM, Log management, EDR, etc.) and take notes.  
After you complete the training you may continue with more technically advanced trainings. But it is important that you begin here.


---
**If You Already Are a SOC Analyst**

If you work as a SOC Analyst and you are here to speed up your professional development, there are sections labeled “Quick Tips” just for you and also numerous examples of mistakes that are made. You can study these topics and focus on applying best practices in order to avoid making mistakes.

Like any person, SOC analysts also make mistakes. In this section we will mention mistakes that are frequently made by SOC analysts and discuss how we can avoid making these mistakes ourselves.
-   Overly Depending on VirusTotal Results
-   Hasty Analysis of Malware in a Sandbox
-   Insufficient Log Analysis
-   Overlooking VirusTotal Dates

We advise that you review this section after completing the other sections of this training.

**Overly Depending on VirusTotal Results**

Sometimes we can rely on the result displayed on VirusTotal’s green screen after analyzing a file’s URL and seeing that the address is harmless. But there is a new malicious software developed using an AV Bypass technique that may not be detected by VT. For this reason we should accept VirusTotal as a supportive tool and conduct our analyses with this in mind.

Here’s a detailed blog post related to the subject for further reading:  
https://medium.com/maverislabs/virustotal-is-not-an-incident-responder-80a6bb687eb9
  
**Hasty Analysis of Malware in a Sandbox**
A 3 to 4 minute analysis in a sandbox environment may not always produce accurate results. Here are the reasons:

1. Malware that detects a sandbox environment and does not activate itself  
2. Malware that do not activate until 10-15 minutes after the operation
3. For this reason, the duration of analysis should be kept as long as possible and it should take place in a real environment if possible.

**Insufficient Log Analysis**
From time to time we see that log analyses are not performed correctly. For example, let’s say that a piece of malware has detected a device with the hostname “LetsDefend” and this malware is secretly sending data to the address “letsdefend.io”. As a SOC analyst we should utilize “Log Management” solutions to determine whether any other device is trying to connect to this address.

**Overlooking VirusTotal Dates**
If the search you have performed in VirusTotal has been queried before, a result from the cache will be displayed. For example: We searched the address “letsdefend.io” on VirusTotal and the result is below.
![[Pasted image 20220512214004.png]]

If I were an attacker I could search for a clean URL address in VirusTotal and then replace the content with malicious content. This is why we should not just look at the search cache, we should start a new search.