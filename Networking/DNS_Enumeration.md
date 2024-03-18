Python DNS Enumaration Program

> [!NOTE] Resources
> - https://academy.hackthebox.com/course/preview/dns-enumeration-using-python/dns-structure


DNS is also known as the **"phone book of the Internet."** Like searching a phone book for a name to get the phone number, DNS looks for a computer name (domain name) to get its IP address. The IP address is needed to connect to a server where only the computer name is known. The system makes it easier for the end-user to reach a web server or a host. DNS is generally used to resolve computer names into IP addresses and reversed them. The components of a DNS service consist of:

-   Name servers
-   Zones
-   Domain names
-   IP addresses

The name servers contain so-called `zones` or `zone files`. In simple terms, zone files are lists of entries for the corresponding domain. We can think of it like a telephone book for a specific city. These zone files contain `IP addresses` to the specific `domains` and `hosts`. Such a zone file exists on every system, whether Linux or Windows and is called the "hosts" file. We can find them on the Pwnbox under "`/etc/hosts`." This file is our local zone file.

## Domain Structure

Let us take the following **fully qualified domain name** (`FQDN`) as an example:

-   `www.domain-A.com`

A domain is used to give real names to computer's IP addresses and, at the same time, to divide them into a hierarchical structure. This hierarchical structure looks like a directory tree of an operating system.

![[Pasted image 20220520153809.png]]

Each domain consists of at least two parts:
1.  `Top-Level Domain` (`TLD`)
2.  `Domain Name`

From the last example, the domain name would be `inlanefreight` and the TLD then "`com`".  If we look at the "`inlanefreight`", we see that its contains some so-called `subdomains`(dev, www, mail). These subdomains can represent a single host or virtual hosts(vHosts). The DNS servers are divided into four different types:
- Recursive resolvers (DNS Recursor)
- Root name server
- TLD name server
- Authoritative name servers.

#### Recursive resolvers
The recursive resolver acts as an agent between the client and the name server. After the recursive resolver receives a DNS query from a web client, it responds to this query with cached data, or it sends a query to a root name server, followed by a query to a TLD name server and finally a final query to an authoritative name server. Once it has received a response from the authoritative name server with the requested IP address, the recursive resolver sends the client's response.

During this process, the recursive resolver stores the received information from authoritative name servers in its cache. When a client requests the IP address of a domain name that was recently requested by another client, the resolver can skip communication with the name servers and retrieve the requested entry from its cache and send it to the client.

#### Root Name Server
Thirteen root name servers can be reached under IPv4 and IPv6 addresses. An international non-profit organization maintains these root name servers called the **Internet Corporation for Assigned Names and Numbers** (`ICANN`). The zone files of these contain all domain names and IP addresses of the TLDs. Every recursive resolver knows these 13 root name servers. These are the first stations in the search for DNS entries for each recursive resolver. Each of these root name servers accepts a recursive resolver query that contains a domain name. The domains' extension answers the query and forwards the recursive resolver to the corresponding TLD name server. We find the 13 root name servers on the domain `root-servers.net` with the corresponding letter as a subdomain.
Run the command `dig ns` to see the 13 root servers.

#### TLD Name Server
A TLD name server manages the information on all domain names that have the same TLD. These TLD name servers are the responsibility of the **Internet Assigned Numbers Authority** (`IANA`) and are managed by it. This means that all domains under the TLD "`.com`" are managed by the corresponding TLD name server. When we look for a domain registered under this TLD, the recursive resolver, after receiving a response from a root name server, sends a query to a TLD name server responsible for that TLD.

#### Authoritative Name Server
Authoritative name servers store DNS record information for domains. These servers are responsible for providing answers to requests from name servers with the IP address and other DNS entries for a web page so the web page can be addressed and accessed by the client. When a recursive resolver receives a TLD name server response, the response refers it to an authoritative name server. The authoritative name server is the last step to get an IP address.

### Other DNS Terms to Know
- **DNS Zone Transfer**: The process of transferring DNS zone updates from a primary DNS server to a secondary DNS server.
- **Internal DNS Server**: A DNS server only accessible by internal clients
- **External DNS Server**: A DNS server accessible by external clients.

## DNS Records
| **Record Type** | **Description**                                                                                                                                                                                               |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A               | An address record is used to map hostname to an IPv4 address                                                                                                                                                  |
| AAAA            | A record that maps domains to IPv6 addresses.                                                                                                                                                                 |
| CNAME           | A canonical name record is an alias of an existing record. Thus allowing multiple DNS records to map to the same IP address.                                                                                  |
| MX              | A mail exchange record maps a domain anme to an e-mail(or message transfer agent) server for that domain.                                                                                                     |
| PTR             | A pointer record points to a canonical name. Used commonly for performing reverse DNS lookup.                                                                                                                 |
| SOA             | A start of authority record provides authoritative information about a DNS zone, such as e-mail contact information for the zone's administrator, the zone's primary name server, and various refresh timers. |
