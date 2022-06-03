# Subnetting
## IPv4 Address Classes
| **Class** | **First Octet(Binary)** | **First Octet range(decimal)** | **Address Range** |
| --- | --- | --- | --- |
| A | 0xxxxxxx | 0-127 | 0.0.0.0~127.255.255.255 |
| B | 10xxxxxx | 128-191 | 128.0.0.0~191.255.255.255 |
| C | 110xxxxx | 192-223 | 192.0.0.0~223.255.255.255 |
| D | 1110xxxx | 224-239 | 224.0.0.0~239.255.255.255 |
| E | 1111xxxx | 240-255 | 240.0.0.0~255.255.255.255 |

IP addresses are assigned to companies and organizations by an International comapany called **IANA**

The **IANA(Internet Assigned Numbers Authority)** assigns IPv4 addresses/networks to companies based on their size.
For example, a very larg company might receive a **Class A** or **Class B** network, while a small company might receive a **Class C** network.
 - However, this led to many IPs wasted, so they divsed a solution for this problem.

With CIDR(Classless Inter-Domain Routing), the requirements of:
**Class A = /8**
**Class B = 16**
**Class C = /24**
...were removed.
This allowed larger networks to be split into smaller networks, allowing greater efficiency. These smaller networks are called **subnetworks** or **subnets**.

###### Formula to get the number of usable addresses:
2^***n*** - 2 = 254 usable addresses. The ***n*** is the number of hosts bits left. 
**CIDR Notation**
| **Dotted Decimal** | **CIDR Notation** |
| --- | --- |
| 255.255.255.128 | /25 |
| 255.255.255.192 | /26 |
| 255.255.255.224 | /27 |
| 255.255.255.240 | /28 |
| 255.255.255.248 | /29 |
| 255.255.255.252 | /30 |
| 255.255.255.254 | /31 |
| 255.255.255.255 | /32 |
