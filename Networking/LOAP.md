# Life of a Packet
Link for the tutorial: https://www.youtube.com/watch?v=4YrYV2io3as&list=PLxbwE86jKRgMpuZuLBivzlM8s2Dk5lXBQ&index=22

**Minor Point**
The Source IP is first followed by the destination IP address when looking at the data and the Destination Mac address will come first instead of the Source Mac. This is because in the packet the Source IP comes first followed by the destination IP and in the Ethernet Frame the Destination IPcomes first followed by the source Mac.![[Pasted image 20220528194740.png]]
#### Quiz
![[Pasted image 20220528201155.png]]

1. PC4 sends a pckaet to PC1. What is the destination MAC address when it is sent from PC4's network interface? **Answer:  FFFE**
2. PC4 send a packet to PC1. What is the source MAC address when it is received on R1's Gi0/0 interface? **Answer: CCCC**
3. PC4 sends a packet to PC1. What is the source MAC address when it is sent from SW1's Gi0/1 interface? **Answer: aaaa**
4. PC4 sends a packet to PC1. What is the destination IP address when it is sent from R4's Gi0/1 interface? **Answer: 192.168.1.1**
5. PC4 sends a packet to PC1. What is the source IP address when it is received on R1's Gi0/0 interface? **Answer:  192.168.4.1**