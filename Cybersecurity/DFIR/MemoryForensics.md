## Types of Memory
**Computer Memory** -> is storage for data, programs and information. RAM, ROM, Harddisk are some examples of computer memory.
![[Pasted image 20220421114430.png]]
**Primary Memory** -> <u>The internal memory of the computer that is directly accessed by the CPU is known as primary memory.</u> It is the main memory of the compter that is directly attached to the motherboard. It holds only those data and instructions which the computer is currently woking on.
	***Random Access Memory*** => Is a primary memory. When we boot a computer, its starts to ,load the system file of the OS into the RAM. It holds those data or instructions temporarily for the CPU to execute those data or instrcutions. This kind of memory is volatile because if power is lost then the data is also lost.
	***Read-only Memory*** => Is a primary memory. The data program stored on the ROM is permanent and non-volatile. The data or program stored on ROM is called *Firmware*. The data remains the same when the computer is turned off. We are only able to read the data but unable to write on it.

**Secondary Memory** -> <u>The external memory of the computer that stores data permanently is known as secondary memory.</u> This kind of memory is permanent and has a large storage capacity. It is alsu known as [auxiliary](https://www.google.com/search?channel=fs&client=ubuntu&q=auxiliary+memory+meaning) memory. It uses magnetic technology or integrated circuit assemblies to store data. *E.g. Hard disk, CD, DVD, SSD*
	***Hard disk drive*** => This is an electromechanical data storage device that stores and retrieves digital data using magnetic storage and one or more rigid rapidlyy rotating platters coated with magnetic material. These are non-volatile storage that retain information even if the power is turned off.
	***CD ROM*** => Stands for Compact Disc Read-only Memory. It secondary memory in a form of a compact disc tha is read by optical means. It can store 600 to 750 MB of data. The data may be in different types of file types. It is of two types: *C[D-R(Compact Disc Recordable)](https://en.wikipedia.org/wiki/CD-R)* and *[CD-RW(Compact Disc-Rewritable)](https://en.wikipedia.org/wiki/CD-RW)*.
	***DVD*** => Stands for Digital Video Disk. It's similar to CD but can store much more data. It has a capacity of 4.7GB to 28.5GB. This medium can store any kind of digital data and be widely used for software and other computer files as well as video programs.

**Cache Memory** -> is a very high-speed semiconductor memory that can speed up the CPU. It acts as a buffer between the CPU and the Main memory. It is used to hold frequently used data and programs by the CPU. The parts of data and programs are transferred from the disk to cache memory by the OS, from where the CPU can access them.


## Physical Organization
The main board within this type of system, the *motherboard*, provides the connections that enable the components of the system to communicate. These communication channels are typically referred to as *computer busses*. 

---
The two most  important components on the motherboard are the processor, which executes programs, and the main memory, which temporarily stores the executed programs and their associated data.
![[Pasted image 20220427222226.png]]
Reading from main memory is often slower than reading from the CPU’s own memory. As a result, modern systems leverage multiple layers of fast memory, called *caches*. Each cache level(L1, L2, etc.) is relatively slower and larger than its predecessor.

The CPU relies on its *memory management unit (MMU)* to help find where the data is stored. The MMU is the hardware unit that translates the address that the processor requests to its corresponding address in main memory.  

Because a given translation can require multiple memory read operations, the processor uses a special cache, known as the *[translation lookaside buffer (TLB)](https://en.wikipedia.org/wiki/Translation_lookaside_buffer)*, for the MMU translation table. Prior to each memory access, the TLB is consulted before asking the MMU to perform a costly address translation operation.

#### North and Sourthbridge
The CPU relies on the *memory controller* to manage communication with main memory. The *memory controller* is responsible for mediating potentially concurrent request for system memory from the processors(s) and devices.
#### Direct Memory Access (DMA)