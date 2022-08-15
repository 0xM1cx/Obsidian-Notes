## What is Threat Intelligence
**Threat Intelligence** is the analysis of data and information using tools and techniques to generate meaningful patterns on how to mitigate against potential risks associated with existing or emerging threats targeting organizations, industries, sectors or governments.

To mitigate against risk, we can start by trying to answer a few simple questions.
- Who's attacking you?
- What's their motivation?
- What are their capabilities?
- What artifacts and indicators of compromise should you look out for?

## Threat Intelligence Classifications
Threat Intel is geared towards understanding the relationship between your operational environment and your adversary.
- **Strategic Intel**. This is a high-level intel that looks into the organization's threat landscape and maps out the risk areas based on trends, patters and emerging threats that may impact business decisions.
- **Technical Intel**. This looks into evidence and artifacts of attack used by an adversary. IR teams can use this intel to create a baseline attack surface to analyze and develop mechanisms.
- **Tactical Intel**. Assesses adversaries' tactics, techniques, and procedures(TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.
- **Operational Intel**. This looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organization(people, process, and technologies) that may be targeted.

## Urlscan.io
This is a free service developed to assist in scanning analyzing websites. It is used to automate the process of browsing and crawling through websites to record activities and interactions.

When a URL is submitted, the information recorded includes the domains and IP addresses contacted, resources requested from the domains, a snapshot of the web page, technologies utilized and other metadata about the website. The site provides two views, the first on showing the most recent scans performed and the second one showing current live scans.

### Scan Results
URL scan results provide ample information, with the following key areas being essential to look at:

-   **Summary:** Provides general information about the URL, ranging from the identified IP address, domain registration details, page history and a screenshot of the site.
-   **HTTP:** Provides information on the HTTP connections made by the scanner to the site, with details about the data fetched and the file types received.
-   **Redirects:** Shows information on any identified HTTP and client-side redirects on the site.
-   **Links:** Shows all the identified links outgoing from the site's homepage.
-   **Behavior:** Provides details of the variables and cookies found on the site. These may be useful in identifying the frameworks used in developing the site.
-   **Indicators:** Lists all IPs, domains and hashes associated with the site. These indicators do not imply malicious activity related to the site.