```toc
```
## What is an Operating System
- An **Operating System** is a program that manages the computer hardware.
- It also provides a basis for Application Programs and acts as an *intermediary* between computer User and computer Hardware
- The OS is a type of system software, that is designed to run/communicate with the device's hardware.

#### Examples of operating systems
- Linux
- Windows
- Mac
- Android

---
## Computer System Architecture

### Types of Computer systems based on number of General Purpose Processors
They are categorized based on the number of general-purpose processors  used.
1. Single Processor Systems
2. Multiprocessor Systems
3. Clustered Systems

### Single Processor Systems
- There is one main CPU capable of executing a general-purpose instruction set, including from user processes. 
- They have other special purpose processors as well.

### Multiprocessor Systems
- Has two or more processors in close communication, sharing the computer bus and sometimes the clock, memory, and peripheral devices.
- Many processes can run simultaneously

#### Advantages
- **Increased Throughput** - Do work in less time; by increasing the number of processors -- we expect to get more work done in less time. 
- **Economy of scale** -  cost less than equivalent multiple single-processor systems, because they share peripherals, mass storage, and power supplies. 
- **Increased reliability**  - If functions can be distributed properly among several processors, then the failure of one processors will not halt the system, only slow it down. Unlike the single processor system that will halt.

#### Disadvantages
- More Complex
- Large main memory

![[12.png]]
1. **Symmetric Multiprocessing** - most common system used, in which each processor performs all tasks within the OS. The processors are at the same level and can do the same task.
2. **Asymmetric Multiprocessing** - each processor is assigned a specific task

### Clustered Systems

![[13.png]]

- They share storage and are linked via LAN or faster interconnect.
- Each node may be a *single processor system or a multicore system*. 