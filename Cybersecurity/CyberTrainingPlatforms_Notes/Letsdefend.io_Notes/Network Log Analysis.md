```toc
```
In this note, I wrote notes on the different logs I would have to analyze to investigate a incident or just monitor the network
## Generic Log Analysis with Netflow
**Netflow** is a network protocol that collects IP traffic information. Although it was developed by Cisco, it supports Netflow from different manufacturers. 

- It works in a stateful structure and monitors and reports all IP traffic passing over the monitored interface. Every IP communication here is defined as a flow. **Flow** is the set of packets that make up the communication between the source and destination. The information collected for the formation of flow are as follows:
	- Source IP Address
	- Destination IP Address
	- Source Port(Only for UDP and TCP protocols)
	- Destination Port(Only for UDP and TCP protocols)
	- IP Protocol
	- Interface Information
	- IP Version Information

Example of netflow data that was converted by an application to make it more readable:
![[generic-1.png]]

With Netflow we can detect:
- Abnormal traffic volume increases
- Data leaks
- Access to private systems
- New IPs in the network
- System accessed for the first time as well as analyze related issues

## Firewall Log Analysis
Firewalls are physical or virtual devices that control incoming and outgoing packets on the network according to rules created depending on the network's cyber policies. 

Each system, host, or server may have its own firewall application or public facing firewall device may be placed for central management of the network in large organizations.

They are the most important security component as it controls network access in organization. Therefore, it is extremely important for the SOC analyst to be able to analyze the logs produced by the firewall devices.

When performing log analysis, the very first thing we need to check is the IP and port information. After that we should check whether this traffic reaches the target or not under the "action" section in the logs.  The action flags:
- **accept** - indicates that the packet passed successfully
- **deny** - packet transmission is blocked, information is returned back to the packet sender
- **drop** - packet transmission is blocked, no information is returned back to the packet sender
- **close** - indicates that the communication is mutually terminated
- **client-rst** - indicates that the communication was terminated by the client
- **server-rst** - indicates that the communication was terminated by the server

Firewall logs are one of the most important resource for the SOC Analyst to refer tow hen investigating incidents, cases, sus activities. For example, it will be very important to find details like below:

- Is there a accept request at different times from the IP address that was detected as attacking and denied by the IPS on firewall logs?
- Checking the firewall logs, you will be able to find whether there is access to/from the suspicious IPs/Domains obtained as a result of the analysis of the malicious content in the antivirus logs.
- Firewall traffic logs are also good resources to detect which different systems an infected system is communicating within the network.
- An analyst can determine port scan activities, communication detection with IoCs and lateral(lan-lan) or vertical(lan-wan, wan-lan) unauthorizes access can be detected.

## VPN Log Analysis

VPN is the technology that allows you to connect to a local network that you are not physically connected to. Generally, organizations prefer this technology to access their internal systems remotely. Today, it is known as a technology to access sites that are not accessible. 


VPNs are generally used over the organization's existing firewall(firewall that supports VPN). In addition, it is possible to see products that provide dedicated services only for VPNs in some networks. VPN logs may be obtained from Firewall devices as well as other devices that provide VPN service. 

- The most important information to review in the VPN log is the IPI address that makes the connection, which user it connects to , and the result of this access request(success-failure status). 
- After a successful VPN connection, an IP is assigned to you for your access through the VPN system. 
- The log of the assigned IP information may be sent either in the same log record or in a different log. 


## Proxy Log Analysis
Proxy acts as a bridge between the endpoint and the internet. Organizations usually use proxy tech for purposes such as internet speed, centralized control and increasing level of security. Request made by the client reach the Proxy Server first and then the Internet. Proxies can basically work in 2 different types:
- **Transparent Proxy** - Target server that we access can see the real source IP address.
- **Anonymous Proxy** - Target server that we access cannot see the real source IP address. It sees the IP address of the proxy ad the source IP address. Thus, it cannot obtain any information about the system that actually made the request in background. 

Proxy logs are one of the most important log types when a SOC analyst needs to check which domain/URL a system(server, client, etc.) is making a request to our internal system and whether it was able to establish a successful connection. 

It is also important to be able to determine if the domain/URL is a risky category and if they were able to establish any successful connections before. 

We can detect the following suspicious activities through reviewing the proxy logs:
- Connections to/from suspicious URLs
- Infected system detection
- Detection of tunneling activities


## IDS/IPS Log Analysis
The IDS/IPS concept and solution are technologies developed at the point where only rule-based access controls of firewall devices are not sufficient in the security world.

Roughly, while the firewall works on a rule basis so that red apples shall and yellow not, IDS/IPS solutions can check whether there are worms in the apple or not. In other words, it has a decision-making mechanism by inspecting the packet content. In this way, it can prevent suspicious/malicious packets/request from reaching the target and prevents systems from being affected by this attack. 

Today, although IDS/IPS technology is provided  by many firewall manufacturers as an additional module/slices on firewall devices, it is only available in devices with IDS/IPS as core functions

### IDS vs IPS
- Intrusion Prevention System - Detects and prevents the suspicious activities
- Intrusion Detection System - Only detects the suspicious activities

Both have signature database. A signature is a set  of rules designed to detect known attacks. The structure that presents this set of rules centrally is called the **signature database**