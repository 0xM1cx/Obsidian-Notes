## What is Threat Intelligence
**Threat Intelligence** is the analysis of data and information using tools and techniques to generate meaningful patterns on how to mitigate against potential risks associated with existing or emerging threats targeting organizations, industries, sectors or governments.

To mitigate against risk, we can start by trying to answer a few simple questions.
- Who's attacking you?
- What's their motivation?
- What are their capabilities?
- What artifacts and indicators of compromise should you look out for?

## Threat Intelligence Classifications
Threat Intel is geared towards <u>understanding the relationship between your operational environment and your adversary</u>.

- **Strategic Intel**. This is a high-level intel that looks into the organization's threat landscape and maps out the risk areas based on trends, patters and emerging threats that may impact business decisions.
- **Technical Intel**. This looks into evidence and artifacts of attack used by an adversary. IR teams can use this intel to create a baseline attack surface to analyze and develop mechanisms.
- **Tactical Intel**. Assesses adversaries' tactics, techniques, and procedures(TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.
- **Operational Intel**. This looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organization(people, process, and technologies) that may be targeted.
---

# Threat Intelligence Tools

## Urlscan.io
This is a free service developed to assist in **scanning analyzing websites**. It is used to automate the process of browsing and crawling through websites to record activities and interactions.

When a URL is submitted, the information recorded includes the domains and IP addresses contacted, resources requested from the domains, a snapshot of the web page, technologies utilized and other metadata about the website. The site provides two views, the first on showing the most recent scans performed and the second one showing current live scans.

### Scan Results
URL scan results provide ample information, with the following key areas being essential to look at:

-   **Summary:** Provides general information about the URL, ranging from the identified IP address, domain registration details, page history and a screenshot of the site.
-   **HTTP:** Provides information on the HTTP connections made by the scanner to the site, with details about the data fetched and the file types received.
-   **Redirects:** Shows information on any identified HTTP and client-side redirects on the site.
-   **Links:** Shows all the identified links outgoing from the site's homepage.
-   **Behavior:** Provides details of the variables and cookies found on the site. These may be useful in identifying the frameworks used in developing the site.
-   **Indicators:** Lists all IPs, domains and hashes associated with the site. These indicators do not imply malicious activity related to the site.

## Abuse.ch
[Abuse.ch](https://abuse.ch/) is a research project hosted by the Institute for Cybersecurity and Engineering at the Bern University of Applied Sciences in Switzerland.

It was developed to identify and track malware and botnets through several operational platforms developed under the project.

**These platforms are**:
- **Malware Bazaar:** A resource for sharing malware samples.
- **Feodo Tracker:** A resource used to track botnet C2 infrastructure linked with Emotet, Dridex and Trickbot.
- **SSL Blacklist:** A resource for collecting and providing for malicious SSL certificates and JA3/JA3s fingerprints.
- **URL Haus:** A resource for sharing malware distribution sites.
- **Threat Fox:** A resource for sharing IOCs.

### Malware Bazaar
[Malware Bazaar.abuse.ch](https://bazaar.abuse.ch/)
This is a malware collection and analysis database. This has the following features:
- **Malware Samples Upload:** Analysts can upload their malware samples for analysis and build the intelligence database. This can be done through the browser or an API.
- **Malware Hunting:** Hunting for malware samples is possible through setting up alerts to match various elements such as *tags*, *signatures*, *YARA rules*, *ClamAV* *signatures* and *vendor detection.*


### Feodo Tracker
[FeodoTracker.abuse.ch](https://feodotracker.abuse.ch/)
The purpose of this project is to share intelligence on botnet C2 servers associated with Dridexx, Emotet(aka Heodo), TrickBot, QakBot and BazarLoader/BazarBackdoor.

This is done by providing a database of the C&C servers that security analysts can search through and investigate any suspicious IP addresses they have come across. Furthermore, they provide various IP and IOC blocklist and mitigation information used to prevent botnet infections.

### SSL Blacklist
[SSL Blacklist](https://sslbl.abuse.ch/)
This was developed to identify and detect malicious SSL connections. From these connections, [SSL certificate](https://www.websecurity.digicert.com/security-topics/what-is-ssl-tls-https) used by botnet C2 servers would be identified and update on a deny-list that is provided for use.

### URLhaus
[URLhaus](https://urlhaus.abuse.ch/)
This tool focuses on sharing malicious URLs used for malware distribution. As an analyst, you can search through the database for domains, URLs, hashes and filetypes that are suspected to be malicious and validate your investigations.

### ThreatFox
[ThreatFox](https://threatfox.abuse.ch/)
With this tool security analysts can search for, share and export indicators of compromise associated with malware. IOCs can be exported in various formats such as MISP events, Sucricata IDS Ruleset, Domain Host files, DNS Response Policy Zone, JSON files and CSV files.
