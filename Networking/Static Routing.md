# Static Routing
####### **Routing table** -> Each router will keep a routing table which stores the list of destinations and how to reach those destinations. ^31d0f4
Example of an entry in the routing table:
	![[Pasted image 20220418170401.png]]
	*Destination IP Address* ***Next Hop Address*** **Exit Interface** 

**Static Route** -> This is a route that an engineer manually configures. ^fde65a

***Two Types of Routes***
	**Connected Route** -> the network the interface is connected to.
	**Local Route** -> The actual IP Address on the interface (with a /32 mask)

---
#### Process that takes place if the destination host is not on the same network
*The device will send the packet to the default gateway* => *After the default gateway received the packet it will compare the packet's destination IP address to its* [[#^31d0f4|Routing Table]]  =>  

---
###### Configuring a `Default Route`
To configure the **default gateway/gateway of last resort** on a Cisco router, you must configure a **default route**; this is a route that matches ***ALL*** possible destinations. It is used only if a more specific route match isn't found in the routing table. The default route is the least specific route possible:
	IP Address: 0.0.0.0
	Mask: 0.0.0.0
> [!NOTE] Setting the default route
> To set the default route/gateway of last resort, configure a route to 0.0.0.0/0 -- This range includes 0.0.0.0 -> 255.255.255.255

*Command to Configure [[#^fde65a | Static Route]]*
`ip route <destination-address> <mask> <next-hop>`