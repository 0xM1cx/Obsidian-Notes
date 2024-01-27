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

