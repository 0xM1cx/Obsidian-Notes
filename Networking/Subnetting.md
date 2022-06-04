# Subnetting Part 1
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
2^***n*** - 2 usable addresses. The ***n*** is the number of hosts bits left. 
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

# Subnetting Part 2
Another technique to identify what the range of each subnet is, you can check the last borrows bit value and add it to the current value.

Example:
![[Pasted image 20220604164543.png]]

Notice that the last bit is 64. So in this case to find the next subnet you can just add 64. 

+ If you add 64 the address will be 192.168.1.64 which is the next subnet after 192.168.1.0 subnet above.
+ Add 64 again and you get 192.168.1.128 which is the next subnet after 192.168.1.64
+ Add 64 again and you get the 4th subnet, which is 192.168.1.128.

As you can see, a trick to finding the next subnet is to determine the value of the last borrowed bit and add it to the current subnet.

## Calculate for the number of subnets

**Example** 
![[Pasted image 20220604165506.png]]
As you can see there are 5 subnets in the network 192.168.255.0/24

Out goal is to divide the **192.168.255.0/24** network into five subnets of equal size. Identify the five subnets.

![[Pasted image 20220604170211.png]]

If we borrows 1 bit we get 2 subnets, 192.168.255.0 and 192.168.255.128. With the first subnet having 126 usable addresses.

#### The formula for the number of subnets
![[Pasted image 20220604170448.png]]

This is somewhat similar to calculating the number of hosts or usable addresses in a network, but the difference is that the value of the exponent is the **number of borrowed bits** and not the number of host bits. Another difference is that it doesn't subtract by 2.