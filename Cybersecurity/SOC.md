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
## Frequent mistakes that SOC Analysts make
---
**If You Want To Become a SOC Analyst**
If becoming a SOC Analyst is your career goal, we advise that you especially focus on SOC tools (SIEM, Log management, EDR, etc.) and take notes.  
After you complete the training you may continue with more technically advanced trainings. But it is important that you begin here.

---
**If You Already Are a SOC Analyst**

If you work as a SOC Analyst and you are here to speed up your professional development, there are sections labeled “Quick Tips” just for you and also numerous examples of mistakes that are made. You can study these topics and focus on applying best practices in order to avoid making mistakes.