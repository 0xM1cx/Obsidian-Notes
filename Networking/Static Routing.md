# Static Routing
**Routing table** -> Each router will keep a routing table which stores the list of destinations and how to reach those destinations. ^31d0f4
Example of an entry in the routing table:
	![[Pasted image 20220418170401.png]]
	<u>*Destination IP Address*</u> ***Next Hop Address*** **Exit Interface** 

**Static Route** -> This is a route that an engineer manually configures. ^fde65a

***Two Types of Routes***
	**Connected Route** -> the network the interface is connected to. In this example the device is connected to the 192.168.1.0/24 Network.
	**Local Route** -> The actual IP Address configured on the interface (with a /32 mask). The /32 notation is used to identify a single specific address.
![[Pasted image 20220505115620.png]]
The line at the top highlighted in yellow isn't a route, it lists the classfull address .

---
#### Process that takes place if the destination host is not on the same network
**The device will send the packet to the default gateway => After the default gateway received the packet it will compare the packet's destination IP address to its** [[#^31d0f4|Routing Table]]

---
#### Configuring a `Default Route`
To configure the **default gateway/gateway of last resort** on a Cisco router, you must configure a **default route**; this is a route that matches ***ALL*** possible destinations. It is used only if a more specific route match isn't found in the routing table. The default route is the least specific route possible:
	IP Address: 0.0.0.0
	Mask: 0.0.0.0
So now that the address has a subnet mask of 0s then there will be no network portion, no fixed value in the address and thus the address has a range of 0.0.0.0 -> 255.255.255.255
> **Setting the default route**
> To set the default route/gateway of last resort, configure a route to 0.0.0.0/0 -- This range includes 0.0.0.0 -> 255.255.255.255

**Command to Configure [[#^fde65a | Static Route]]**
`ip route <destination-address> <mask> [<next-hop> | <exit-interface>]`
![[Pasted image 20220505122143.png]]
The S** means that the route configured is statis or it was manually configured. The _*_ means that it is a candidate for a default route.

>Switches **Flood** frames with unkown destinations(destinations not in the MAC table.) Routers **Drop** packets with unkown destinations.

