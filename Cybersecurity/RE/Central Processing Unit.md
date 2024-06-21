## Fetch-Decode-Execute Cycle
The **instruction cycle** is the cycle that the CPU follows from boot-up until the computer has shut down in order to process instructions. It is composed of three main stages: the fetch stage, the decode stage, and the execute stage.

### Role of Components
- **Program Counter(PC)** - this is a special register that holds the memory address of the next instruction to be executed. Gets incremented after each instruction fetch.
- **Instruction Register(IR)** - Holds the current fetched instruction for decoding and execution
- **Control Unit** - Coordinates and manages the execution of instruction. Controls the flow of data between the CPU and other components.
- **Arithmetic Logic Unit(ALU)** - Performs arithmetic and logical operations as directed by the executed instruction.
- **Registers** - Temporary storage locations used for holding during the execution of instructions. Examples include the accumulator, data registers, and address registers
- **Memory** - Stores both data and instructions that the CPU uses during execution.


## Registers
- Registers are small memory storage areas built into the processor and are volatile
![[Pasted image 20240205210832.png]]
![[Pasted image 20240205210931.png]]
### General Purpose Registers
- **AX** - used to store values in arithmetic and logic operations
- **BX** - often used to hold the base address for memory operations 
## System Calls
A **system call**, or **syscall**, is when a program requests a service from the kernel. System calls will differ by operating system because different operating systems use different kernels. 

All syscalls have an ID associated with them (a number)

Syscalls also take **arguments**, meaning, a list of inputs

### System Call Inputs by Register
| Arguemtns | Registers |
| ---- | ---- |
| ID | rax |
| 1 | rdi |
| 2 | rsi |
| 3 | rdx |
| 4 | r10 |
| 5 | r8 |
| 6 | r9<br> |

Reference code:
```c
section .data
	text db "Shawn Gwapo",10

section .text
	global _start

_start:
	mov rax, 1
	mov rdi, 1
	mov rsi, text
	mov rdx, 12
	syscall

	mov rax, 60
	mov rdi, 0
	syscall
```
## Sections & Labels
### .data
The data section is where all data is defined before compilation

### .bss
The bss section is where data is allocated for future use

### .text
The text section is where the actual code goes


### labels
A label is used to label part of code.

Upon compilation, the compiler will calculate the location in which the label will sit in memory. Anytime the name of the label is used afterwards, the name is replaced by the location in memory by compiler. 
#### Start label
The _start label is essential for all programs. When you program is compiled and later executed, it is executed first at the location of _start. If the linker cannot find _start, it will throw an error.

#### Global
The world **global** is used when you want the linker to be able to know the address of some label. The object(name.o) file generated will contain a link to every label declared "global". In this case, we have to declare "_start" as global since it is required for the code to be properly linked. 
