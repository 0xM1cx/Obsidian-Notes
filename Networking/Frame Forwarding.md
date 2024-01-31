- **Ingress** - This is used to describe the port where a frame enters the device.
- **Egress** - This is used to describe the port that frames will use when leaving the device.


## Switch MAC Address Table
- A switch is made up of integrated circuits and the accompanying software that controls the data paths through the switch. 
- Switches use destination MAC addresses to direct network communications through the switch, out the appropriate port, toward the destination.
- For a switch to know which port to use to transmit a frame, it must first learn which devices exist on each port. As the switch learns the relationship of ports to devices, it builds a table called a **MAC address table.**
- This table is stored in content addressable memory (CAM) which is a special type of memory used in high-speed searching applications.
- A switch populates its MAC address table by recording the source MAC address of each device connected to each of its ports.


## Switching Forwarding Methods
**Application-specific-integrated circuits (ASICs)** reduce the frame-handling time within the device and allow the device to manage an increased number of frames without degrading performance.

Layer 2 switches use one of two methods to switch frames:
- **Store-and-forward switching** -  This methods makes a forwarding decision on a frame after it has received the entire frame and checked the frame for errors using a mathematical error-checking mechanism known ass **Cyclic redundancy check**. 
- **Cut-through switching** - This method begins the forwarding process after the destination MAC address of an incoming frame and the egress port have been determined.


### Store-and-forward switching



### Cut-through switching
