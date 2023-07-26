## Ethernet
- Ethernet is a collection of network protocols/standards

## Bits and Bytes
- Bits are either 0 or 1
- A byte is a combination of 8 bits. 
- **Speed** is measured in *bits per second(Kbps, Mbps, Gbps)*, not bytes per second. 

## Size Equivalence
- 1 kilobit (Kb) = 1,000 bits
- 1 megabit (Mg) = 1, 000, 000 bits
- 1 gigabit (Gb) = 1, 000, 000, 000 bits
- 1 terabit (Tb) = 1, 000, 000, 000, 000 bits. 

## Ethernet Standards
- Defined in the IEEE 802.3 standard in 1983
- **IEEE** = Institute of Electrical and Electronics Engineers


### Ethernet Standards(Copper)

| Speed    | Common Name      | IEEE Standard | Informal Name | Max Length |
| -------- | ---------------- | ------------- | ------------- | ---------- |
| 10 Mbps  | Ethernet         | 802.3i        | 10BASE-T      | 100m       |
| 100 Mbps | Fast Ethernet    | 802.3u        | 100BASE-T     | 100m       |
| 1 Gbps   | Gigabit Ethernet | 802.3ab       | 1000BASE-T    | 100m       |
| 10 Gbps  | 10 Gig Ethernet  | 802.3an       | 10GBASE-T     | 100m           |

## UTP Cables
- The twisting of the Unshielded Twisted Pair(UTP) cable is used to protect against *Electro Magnetic Interference*.

| UTP CABLE   | Wires             |
| ----------- | ----------------- |
| 10 BASE-T   | 2 pairs (4 wires) |
| 100 BASE-T  | 2 pairs (4 wires) |
| 1000 BASE-T | 4 pairs (8 wires) |
| 10G BASE-T  | 4 pairs (8 wires) |

#### Full Duplex (10BASE-T, 100BASE-T)
- This is a straight-through cable because the pins connect on the same pin number on the other end.
- This is for Client, server, router w/ switch
![[Pasted image 20230726162228.png]]

![[Pasted image 20230726162818.png]]

- **Auto Media Independent Interface with Crossover or Auto MDIX** are on ports of network devices. This allows devices to automatically detect with pins their neighbor is transmitting on and adjust which pins to TX and RX data on. 

| Device Type | Transmit (TX) Pins | Receive(Rx) Pins |
| ----------- | ------------------ | ---------------- |
| Router      | 1 and 2            | 3 and 6          |
| Firewall    | 1 and 2            | 3 and 6          |
| PC          | 1 and 2            | 3 and 6          |
| Switch      | 3 and 6            | 1 and 2          | 


#### Full Duplex (1000BASE-T, 10GBASE-T)
![[Pasted image 20230726164950.png]]


## Fiber Optic Connections
- **SFP Transceiver (Small Form-Factor Pluggable)** it is used to connect fiber optic cables to 

![[Pasted image 20230726165607.png]]

1. The fiberglass core itself
2. cladding that reflects light
3. a protective buffer
4. the outer jacket of the cable

#### Two Types of Fiber Cables
- **Multimode**
	- Core diameter is wider than single-mode fiber
	- Allows multiple angles (modes) of light waves to enter the fiberglass core
	- Allows longer cables than UTP, but shorter cables than single-mode fiber
	- Cheaper than single-mode fiber(due to cheaper LED-based SFP transmitters)
	![[Pasted image 20230726165934.png]]

- **Single-mode**
	- Core diameter is narrower than multimode fiber
	- Light enters at a single angle (mode) from a laser-based transmitter
	- Allows longer cables than both UTP and multimode fiber
	- More expensive than multimode fiber (due to more expensive laser-based SFP transmitter)
	![[Pasted image 20230726170204.png]]


##### Fiber-optic cable standards

| Informal Name | IEEE Standard | Speed  | Cable Type               | Maximum Length      |
| ------------- | ------------- | ------ | ------------------------ | ------------------- |
| 1000BASE-LX   | 802.3z        | 1Gbps  | Multimode or Single-Mode | 500 m(MM) 5 km (SM) |
| 10GBASE-SR    | 802.3ae       | 10Gbps | Multimode                | 400 m               |
| 10GBASE-LR    | 802.3ae       | 10Gbps | Single-Mode              | 10 km               |
| 10GBASE-ER    | 802.3ae       | 10Gbps | Single-Mode              | 30 km               |


## UTP vs Fiber-Optic

| UTP                                                                                          | Fiber-Optic                                                                                |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Lower cost than fiber-optic                                                                  | Higher cost than UTP                                                                       |
| Shorter maximum distance than fiber-optic(~100)                                              | Longer maximum distance than UTP                                                           |
| Can be vulnerable to EMI                                                                     | No vulnerability to EMI                                                                    |
| RJ45 ports used with UTP are cheaper than SFP                                                | SFP ports are more expensive than RJ45 ports(single-mode is more expensive than multimode) |
| Emit(leak) a faint signal outside of the cable, which can be copied and pose a security risk | Does not emit any signal outside the cable and does not pose a security risk                                                                                           |
