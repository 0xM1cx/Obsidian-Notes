### NMAP
Also known as <u>Network Mapper</u>. When a computer runs a network service, it opens a networking construct called a *port* to receive the connection. Ports are necessary for making multiple network requests or having multiple services available. For example, when you load several webpages at once in a web browser, the program must have some way of determining which tab is loading which web page. This is done by establishing connections to the remote webservers using different ports on your local machine. Equally, if you want a server to be able to run more than one service (for example, perhaps you want your webserver to run both HTTP and HTTPS versions of the site), then you need some way to direct the traffic to the appropriate service. Once again, ports are the solution to this. Network connections are made between two ports – an open port listening on the server and a randomly selected port on your own computer. For example, when you connect to a web page, your computer may open port 49534 to connect to the server’s port 443.
![[Pasted image 20220423172528.png]]
The basic theory of how nmap works is that it will connect to each port of the target in turn. Depending on how the ports responds, it can be determined as being *open*, *closed*, *filtered(usually by a firewall)*.

## Nmap Switches
**-A**  to enable OS and verion detection, script scanning and traceroute. 
**-T4** for faster execution; and then hostname.

### Target Specification
When a hostname is given as a target, it is _resolved_ via the Domain Name System (DNS) to determine the IP address to scan. If the name resolves to more than one IP address, only the first one will be scanned. To make Nmap scan all the resolved addresses instead of only the first one, use the `--resolve-all` option.

**`iL <inputfilename>`** -> Read targets specification from `<inputfilename>` passing a huge list of hosts is often awkward on the command line, yet it is a common desire.
**`iR <num hosts>`** -> (Choose random targets). For internet-wide surveys and other research, you may want to choose targets at random. The argumet `0` can be specified for a never-ending scan. *If you find yourself really bored one rainy afternoon, try command `nmap -Pn -sS -p 80 -iR 0 --open` to locate random web servers from browsing*
**`exclude <host1>[, <host2>[,...]]`** -> (Exclude host/networkds). Specifies a comma-separated list of target to be excluded fromthe scan even if they are part of the overall network range you specify.