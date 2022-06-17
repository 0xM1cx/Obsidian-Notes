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

#### Formula to get the number of usable addresses:
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
#### Example 1: Finding the subnet is belongs to
What subnet does host **172.21.111.201/20** belong to?
**Steps to solve this kind of problem**
1. Write out the address in Binary
![[Pasted image 20220617123644.png]]
2. Change all of the host bits to 0 and convert the address back to dotted decimal
![[Pasted image 20220617123757.png]]

#### Example 2: Find the broadcast address of a subnet
What is the <u>broadcast address</u> of the network **192.168.91.78/26** belongs to?
1. Write out the address into Binary
2. Then change all the host bits to 1s and convert the address back to dotted decimal
![[Pasted image 20220617124210.png]]

#### Example 3: Dividing subnets of equal size.
You divide the **172.16.0.0/16** network into 4 subnets of equal size. Identify the **network** and **broadcast** addresses of the second subnet.
1. Determine the prefix length to use, given the table above having a prefix length of /18 will give us 4 subnets.
![[Pasted image 20220617125432.png]]
![[Pasted image 20220617125528.png]]
2. Turn the last network bit to 1 and convert it back to dotted decimal. This will be the second subnet and the network address for this subnet. The first was **172.16.0.0**![[Pasted image 20220617125544.png]]
3. To find the broadcast address of the second subnet, change all the host bits to 1s and convert it back to dotted decimal.![[Pasted image 20220617125738.png]]
#### Example 4: Getting the number of subnets given the number of hosts.
You divide the **172.30.0.0/16** network into subnets of 1000 hosts each. How many subnets are you able to make?
- To know how many subnets we are able to make we have to know how many bits we can borrow.
- In order to know how many bits we can borrow, we need to find how many host bits we need for 1000 hosts.

1. In our case we will 10 hosts bits to get more than 1000 hosts.
![[Pasted image 20220617131449.png]]
2. That will get us with **6** borrowed bits.![[Pasted image 20220617131829.png]]
3. The 6 borrowed bits will get us 64 subnets.
![[Pasted image 20220617132046.png]]

#### Example 5: Subnetting Class A Networks
You have been given the **10.0.0.0/8** network. You must create 2000 subnets which will be distributed to various enterprises.
- What prefix length must you use? Answer: **/19**
- How many host addresses (usable addresses) will be in each subnet? Answer: **8190**

**How I solved this problem**
1. First convert the address to binary format and determine what prefix length to use using the formula 2^n where **n** is the number of bits you must borrow, in this case the answer must be 2000 or greater.
2. In this case the number of borrowed bits are 11 which will give us 2,048 subnets(**2^11 = 2,048 subnets**). 
3. In the binary format of the **10.0.0.0** address we determined, with the 11 borrowed bits, that the prefix length for there to have 2,048 subnets must be /19.
4. In order to get the number of host per subnet we use this formula **2 ^ n - 2**. Where **n** is the number of host bits minus 2 for the network and broadcast addresses. We get **8,190** hosts per subnet. 

#### Example 6: Subnetting Class 6 Networks
PC1 has an IP address of **10.217.182.223/11**
Identify the following for PC1's subnet:
- Network address: **10.192.0.0**
- Broadcast address: **10.192.0.1**
- First usable address: **10.223.255.255**
- Last usable address: **10.223.255.254**
- Number of host(usable) addresses: **2,097,150** hosts per subnet

1.  First convert the address to binary to determine where the network portion ends and where the host portion starts, as well as the number of borrowed bits.  In this problem there were 3 borrowed bits. ![[Pasted image 20220617135239.png]]
2. To find the **network address**, change all the host address to 0.![[Pasted image 20220617135338.png]]
3. Add 1 to the determined network address above to find the **first usable address**. ![[Pasted image 20220617135543.png]]
4. To get the **broadcast address** change all of the host bits to 1. ![[Pasted image 20220617135703.png]]
5. To get the **last usable address**, just subtract 1 from the broadcast address. ![[Pasted image 20220617135841.png]]
6. Lastly, to get the number of host per subnet, count the number of host bits and use this formula **2^n - 2**. ![[Pasted image 20220617140034.png]]

---
## Subnetting Part 3 
### Variable-Length Subnet Masks
