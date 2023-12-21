## Module 3
- What are the difference between user-level threads and kernel-level threads? Under what conditions is one type better than the other?
	- User level threads and kernel level threads differ in how they are managed and how mych overhead they produce. Because ULTs are lightweight and wholly controlled by a user-level thread library, context switching is faster and frequently more scalable. However, ULTs have parallelism constraints, and if one thread fails, it can disrupt the entire operation. KLTs, on the other hand, are maintained by the operating system kernel, allowing for more parallelism and isolation. While KLTs are bulkier and require slower context switching, they provide benefits in resource-rich environments and applications with complicated thread interactions. 
- Describe the actions a kernel takes to context switch between processes.
	- Context switching is the process by which the operating system kernel saves and restores the state of a process so that it can execute multiple processes concurrently.

1. **Save Current Process State:**
    
    - The kernel saves the current state of the CPU registers, program counter, and other relevant information for the currently running process. This information is crucial for later resuming the execution of the process.
2. **Update Process Control Block (PCB):**
    
    - The kernel updates the Process Control Block (PCB) of the current process with its latest state. The PCB contains information about the process, including its register values, program counter, stack pointer, and other details.
3. **Select a New Process:**
    
    - The kernel selects a new process to run. This decision can be based on various scheduling algorithms that determine which process should be given CPU time next. The selected process may be from the ready queue or based on priority.
4. **Retrieve Process State:**
    
    - The kernel retrieves the saved state from the PCB of the new process. This includes loading the CPU registers, program counter, and other relevant information.
5. **Update Memory Management:**
    
    - If the new process has a different memory space (as in the case of processes in a multitasking environment), the kernel updates the Memory Management Unit (MMU) to ensure that the virtual memory mapping is correct for the new process.
6. **Update CPU Status:**
    
    - The kernel updates the CPU status to reflect the new process as the currently running one.
7. **Restore New Process State:**
    
    - The kernel restores the saved state of the new process, allowing it to resume execution from where it was previously interrupted.
8. **Control Transferred to New Process:**
    
    - The control of the CPU is transferred to the new process, and it begins execution from the point where it was last interrupted.
- Explain the difference between preemptive and non-preemptive scheduling. State why strict non-preemptive scheduling is unlikely to be used in a computer center. 
	- Preemptive scheduling allows the operating system to interrupt and switch tasks for better responsiveness and prevents any single task from monopolizing the CPU. In contrast, non-preemptive scheduling relies on tasks voluntarily yielding control and is less likely to be used in a computer center due to the risk of a single task causing resource monopolization, leading to poor responsiveness and potential instability. Preemptive scheduling, with its control over task execution and fairness in resource allocation, is a more practical choice for managing diverse workloads in such environments.


d. In all the schedules used, the one with the least average waiting time was the Shortest Job First algorithm, with an average waiting time of 3.2 miliseconds


## Module 4: Deadlock
- In the traffic deadlock example give, explain why deadlock exists  using the four conditions of deadlock.
	- In the traffic deadlock example at a four-way intersection, deadlock arises due to the combination of mutual exclusion (only one vehicle can occupy a lane at a time), hold and wait (vehicles holding lanes and waiting for others), no preemption (lanes cannot be taken away from vehicles), and circular wait (vehicles forming a circular dependency, each waiting for the lane held by the next). This results in a situation where no vehicle can advance, leading to a standstill in traffic flow unless deadlock avoidance or resolution measures are implemented, such as adjusting traffic light timings or introducing additional rules.
- What is the main problem in deadlock prevention?
	- 
- Explain the reasons why the Banker's algorithm is not a good alternative in handling deadlocks?
- What is an unsafe state?
	- An unsafe state is a system state in which processes hold resources while waiting for others, which are simultaneously held by other processes, resulting in a cyclical wait condition. An unsafe state arises when all these conditions are met, and if no precautions are taken to avoid deadlocks, the system may enter into a deadlock situation



