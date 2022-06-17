```toc
```
## Subnetting Part 1
### IPv4 Address Classes
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
2^***n*** - 2 usable addresse. The ***n*** is the number of hosts bits left. 
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

---
## Subnetting Part 2
Another technique to identify what the range of each subnet is, you can check the last borrows bit value and add it to the current value.

Example:
![[Pasted image 20220604164543.png]]

Notice that the last bit is 64. So in this case to find the next subnet you can just add 64. 

+ If you add 64 the address will be 192.168.1.64 which is the next subnet after 192.168.1.0 subnet above.
+ Add 64 again and you get 192.168.1.128 which is the next subnet after 192.168.1.64
+ Add 64 again and you get the 4th subnet, which is 192.168.1.128.

As you can see, a trick to finding the next subnet is to determine the value of the last borrowed bit and add it to the current subnet.

### Calculate for the number of subnets

**Example** 
![[Pasted image 20220604165506.png]]
As you can see there are 5 subnets in the network 192.168.255.0/24

Our goal is to divide the **192.168.255.0/24** network into five subnets of equal size. Identify the five subnets.

![[Pasted image 20220604170211.png]]

If we borrows 1 bit we get 2 subnets, 192.168.255.0 and 192.168.255.128. With the first subnet having 126 usable addresses.

#### The formula for the number of subnets
![[Pasted image 20220604170448.png]]

This is somewhat similar to calculating the number of hosts or usable addresses in a network, but the difference is that the value of the exponent is the **number of borrowed bits** and not the number of host bits. Another difference is that it doesn't subtract by 2.

##### Table of the different subnet sizes and hosts for class C networks
| **Prefix Length** | **Number of Subnets** | **Number of Hosts** |
| --- | --- | --- |
| /25 | 2 | 126 |
| /26 | 4 | 62 |
| /27 | 8 | 30 |
| /28 | 16 | 14 |
| /29 | 32 | 6 |
| /30 | 64 | 2 |
| /31 | 128 | 0(2 network and broadcast addresses only, cannot be used by hosts) |
| /32 | 256 | 0(1 You can use this address to assign a specific address to a host, like in the case of a local route) |

##### Table of different subnet sizes and hosts for class B networks
| **Prefix Length** | **No. of Subnets** | **No. of Hosts** |
| --- | --- | --- |
| /17 | 2 | 32766 |
| /18 | 4 | 16382 |
| /19 | 8 | 8190 |
| /20 | 16 | 4094 |
| /21 | 32 | 2044 |
| /22 | 64 | 1022 |
| /23 | 128 | 510 |
| /24 | 256 | 254 |
| /25 | 512 | 126 |
| /26 | 1024 | 62 |
| /27 | 2048 | 30 |
| /28 | 4096 | 14 |
| /29 | 8192 | 6 |
| /30 | 16384 | 2 |
| /31 | 32768 | 0(2) |
| /32 | 65536 | 0(1) |

### Example Problems and Solutions
#### Example 1:
What subnet does host **172.21.111.201/20** belong to?
**Steps to solve this kind of problem**
1. Write out the address in Binary
![[Pasted image 20220617123644.png]]
2. Change all of the host bits to 0 and convert the address back to dotted decimal
![[Pasted image 20220617123757.png]]

#### Example 2:
What is the <u>broadcast address</u> of the network **192.168.91.78/26** belongs to?
1. Write out the address into Binary
2. Then change all the host bits to 1s and convert the address back to dotted decimal
![[Pasted image 20220617124210.png]]

---
## Subnetting Part 3
