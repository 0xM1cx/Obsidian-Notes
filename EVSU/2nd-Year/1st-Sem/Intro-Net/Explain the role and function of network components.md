![[Cisco-switches-and-hubs-Design-elements.png]]

- **Computer Network** - is a digital telecommunications network which allows nodes to share resources. These  nodes are *routers*, *switches*, *firewall*, *server*, *client*.
- A **Client** is a device that accesses a service made available by a server.

## Routers

| Cisco Routers |     | 
| ------------- | --- |
| ISR 1000      |     |
| ISR 900       |     |
| ISR 4000      |     |
- Routers have fewer network interfaces that switches
- They are used to provide connectivity *between* LANs
- They are therefore used to send data over the Internet.

## Layer 2 and Layer 3 switches
- Switches have many network interfaces/ports for end hosts to connect to(usually 24+)
- They provide connectivity to hosts within the same LAN
- Layer 2 switches do no provide connectivity between LANs/ over the Internet

### Layer 3 Switch
- A layer 3 switch combines the functionality of a switch and a router. It acts as a switch to connected devices that are on the same subnet or VLAN at lightning speed and has IP routing Intelligence built into it to double up as a router. 
- It can support routing protocols, inspect incoming packets, and can even make routing decision based on the source and destination addresses. 

## Next-generation firewalls and IPS
### Firewalls
- **Firewalls** is a network security device or software that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules. 
- They monitor and control network traffic based on configured rules
- They can be placed *inside* the network or *outside* the network
- They are known as *Next-Generation Firewalls* when they include more modern and advanced filtering capabilities. 

#### Examples of firewalls
- ASA5500-X(next-gen)
- Firepower 2100(next-gen)

#### Kinds of firewalls
1. **Network Firewalls** are devices that filter traffic between networks.
2. **Host-based Firewalls** are software applications that filter ingress and egress traffic on a host machine. Like a PC or a server. 
### IPS
Intrusion Prevention System Technologies can detect or prevent network security attacks such as DOS, DDOS, Brute force attacks and Vulnerability Exploits. 

## Access Points
## Controllers (Cisco DNA Center and WLC)
## Endpoints
- This is any device that is physically an end point on a network. Laptops, desktops, mobile phones, tablets, servers, and virtual environments can all be considered endpoints. 
## Servers
- This is a device that provides functions or services for clients. 
- The client can also be a server, because they can also provide services to other nodes. 
## PoE
