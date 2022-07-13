```toc
```
## What is a LAN?
A common definition of LAN is that it is a group of devices(PCs, Servers, Routers, Switches, etc.) in a single location (home, office, etc.)

A more specific definition: A LAN is a single **Broadcast domain**, including all devices in that broadcast domain. A **Broadcast domain** is the group of devices which will receive a broadcast frame (destination MAC of FFFF.FFFF.FFFF) sent by any one of the members.

## What are VLANs?
It is a logical LAN, a logical grouping of devices in the same broadcast domain. VLANs are usually configures on switches by placing some interfaces into one broadcast domain and some interfaces into another. Each VLAN acts as a subgroup of the switch ports in an Ethernet LAN.

## Why do we need VLANs?
![[Pasted image 20220712233352.png]]
Say we have a switch of three departments: Engineering, Sales, and HR. These departments are connected via a switch. This is a problem because if one client on the engineering department will send a broadcast message intended for all other engineering hosts it will not only send it to other engineering hosts it will also broadcast this on other departments.

**In terms of Performance**. This will cause bottlenecks and performance issues in the network.

**In terms of Security**. Even within the same office, you want to limit who has access to what data. You can apply security policies on a router/firewall. Because this is one LAN, PCs can reach each other directly, without traffic passing through the router. So, even if you configure security policies, they won't have any effect.

**The solution, VLANs**
When we set up a VLAN it will have its own logical subnet in which it will be separated from other VLANs and can only send broadcast frames to its local VLAN. VLANs will function like different switches on a single router but logically separated. This reduces cost of buying more hardware.

 