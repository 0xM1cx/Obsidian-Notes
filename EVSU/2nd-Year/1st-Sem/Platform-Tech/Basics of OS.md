## Basic Structure of a Computer System
![[3.png]]
### System vs Applications software/programs
> **Software vs Programs**
> A **program** is a set of instructions that is used as a process of creating a software program by using a programming language. E.g. Malware, Web Browsers, etc.
> A **software** is a collection of many programs used to perform tasks. Its basically a complete set of programs, that have been compiled, tested E.g. VLC media, MS Word, Excel, etc.

- **System Software** - These are used to directly modify or give commands to the computer hardware. One example is the *Operating System*.
- **Application software** -  These are used to perform a specific task and that can be directly used by the user.

## Computer System Operation
![[4.png]]
- **Disk Controller** - this is a circuit which is the interface that allows the computer to access and communicate with the Disks. When the computer wants to transfer data to or from the disk, it tells the disk controller.
- **USB Controller** - This is a chip or device that allows the computer to communicate with the USB device. This is often referred to as a host controller interface, the host being you computer.
- **Memory Controller** - This is a digital circuit that manages the flow of data going to and from the computer's main memory. They also have the task of reading, writing and refreshing the RAM. Lastly, the memory controller has the task of ensuring orderly access to the shared memory, it is its function to synchronize access to the memory.

### Important term in OS
1. Bootstrap Program
	- The Initial program that runs when a computer is powered up or rebooted.
	- It is stored in the ROM
	- It must know how to load the OS and start executing that system
	- It must locate and load into memory the OS kernel
2. Interrupt
	- 
![[5.png]]

![[6.png]]
- **Service Routine/Interrupt Service Routine(ISR)** - is a process invoked by an interrupt request from a hardware device. It handles the request and sends it to the CPU, interrupting the active process. When the ISR is complete, the process is resumed. [More Information Here](https://techterms.com/definition/isr)

## Storage Structure
![[7.png]]
- **Registers**. These are the smallest storage structure. These are a small set of data holding places that are part of the processor. They can hold instructions, storage address,  or other small data like bit sequences.
- **Cache**. This is a temporary memory, this is used to store commonly used data for faster processing in the future.
- **Main Memory**. This the Random-Access Memory. This is where processes are stored temporarily for execution when you execute them.
### Volatile vs Non-Volatile
- **Volatile** - It means that it loses its content when power is removed, examples of this are RAM, Cache, Registers.
- **Non-Volatile** -  It means that even if the there is no power it still retains its contents. Examples of this are Secondary Storage like hard disks, external storage like external HDD, DVD, flash drive.
![[8.png]]

![[9.png]]
	