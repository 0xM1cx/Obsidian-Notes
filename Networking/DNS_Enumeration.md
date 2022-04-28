Python DNS Enumaration Program

> [!NOTE] Resources
> - https://academy.hackthebox.com/course/preview/dns-enumeration-using-python/dns-structure


DNS is also known as the "phone book of the Internet." Like searching a phone book for a name to get the phone number, DNS looks for a computer name (domain name) to get its IP address. The IP address is needed to connect to a server where only the computer name is known. The system makes it easier for the end-user to reach a web server or a host. DNS is generally used to resolve computer names into IP addresses and reversed them. The components of a DNS service consist of:

-   `Name servers`
-   `Zones`
-   `Domain names`
-   `IP addresses`

The name servers contain so-called `zones` or `zone files`. In simple terms, zone files are lists of entries for the corresponding domain. We can think of it like a telephone book for a specific city. These zone files contain `IP addresses` to the specific `domains` and `hosts`. Such a zone file exists on every system, whether Linux or Windows and is called the "hosts" file. We can find them on the Pwnbox under "`/etc/hosts`." This file is our local zone file.

## Domain Structure

Let us take the following fully qualified domain name (`FQDN`) as an example:

-   `www.domain-A.com`

A domain is used to give real names to computer's IP addresses and, at the same time, to divide them into a hierarchical structure. This hierarchical structure looks like a directory tree of an operating system.