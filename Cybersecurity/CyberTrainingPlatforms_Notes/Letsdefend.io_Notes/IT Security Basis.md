## Inventory
Protecting your infrastructure required knowing:
- What devices are connected to your network
- What applications are being used
- Who has access to them
- What security measures are in place


### What should your inventory contain and why?
With all IT security issues, you will need a complete inventory. This should at least contain the following:
- the hardware of each workstation and server
- the software installed with the exact version
- the date of the last report


### End-of-life Equipment of assets in inventory 
Equipment(hardware and software) that is not longer maintained is equipment that will no longer receive security patches. It is then necessary to exclude from your network all the equipment that cannot be maintained. 

In the case of extreme necessity, a risk acceptance by the CISO(Chief Information Security Officer) must be performed and traced in your inventory. This analysis must be reviewed at regular intervals, ideally at each new vulnerability. 

### Secure Boot on assets
Secure boot must be enabled on all compatible devices. This feature ensures that the computer *boots using only manufacturer-approved software*. This is a feature that has been available for 10 years, so it is unlikely that a problem will occur if you have standard usage. 

### Software list in Inventory
To reduce the attack surface, companies must have a strict policy regarding authorized and unauthorized softwares

#### Allowed Softwares
Using Group Policy Object(GPO) or Intune allows you to provide users with a quickly available software library without the need for administrative rights to its stations. This avoid the need for users to have to download the installation file themselves and therefore limit the risk of downloading a malicious program

#### Forbidden Softwares
In the same way, whether via Intune or AppLocker, it is necessary to block software identified as forbidden (either because you do not legitimize the application or because its version is subject to a CVE that is dangerous for you). Each use of a prohibited application must be reported to your company's IT team.

### Security Hardening
Organizations must rely on proven hardening guides to define the configuration of their devices. These hardening guidelines can cover different levels such as:
- Station handover procedures with prerequisite checklist
- Audit of the secure configuration of the devices
- Alert in case of configuration modification

This hardening can be done in several ways, such as Ansible, GPO, or Intune.

### Antivirus/EDR
Make sure that your company deploys an antivirus solution, or even an EDR on the entire fleet, starting with the devices that are critical to you business. Do not forget to set up a follow-up of the generated alerts. 

## Backups
Backups are not a mechanism for fighting Ransomware but they are your last line of defense. A non-operational backup system following an attack could jeopardize the survival of your business.
### Rule 3-2-1
As a basic rule and the minimum expected for an infrastructure, the 3-2-1 rule states that you must:
- Have at least three copies of your data
- Store on two different media
- One of which must be an offsite external backup
## Phishing Prevention
### Antispam and Email Protection
- Put all emails by employees pass through a spam filter. 
- AV software must analyze the email attachment
- Security solution configuration must be reviewed and kept up to date with the new threats.
- When one of the employees receives an email and has doubt, he/she should have the possibility to contact someone to perform an analysis of the email
- Phishing drills must be conducted to ensure that the staff are properly aware of these kinds of threats
## Internet Browsing Protection
### DNS Filtering 
Block dangerous sites and filter unwanted content through your firewalls. In addition to "unprofessional" categories like +18 adult content, there is one category that is rarely blocked, URL shorteners. This service is massively used, especially for phishing. Once the blocking is configured, it is necessary to control the blocked sites that your employees have tried to visit.
### Centralized Management of Browsers
Updating browser security can make it harder for malware to install. for example, to reduce the ability to install plug-ins or disable the automatic execution of certain types of content
## Patching
## Access Control
## Risk Analysis
## Network
## Incident Response for IT Security









