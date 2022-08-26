```toc
```
> [!NOTE] Check Your Progress.
> a. What is an algorithm?
> 	An algorithm is a sequence of instructions design in such a way to complete a task or solve a problem.
> b. What is a flowchart?
> 	A flowchart is a visual representations of the step by step process the program will execute.
> c. What are the types of flowcharts?
> 	The two types of flowcharts are Program Flowcharts and System Flowcharts.
> d. List any two steps involved in problem solving
> 	Detailed study of the problem and Problem redefinition.

## Introduction
Computers are capable of handling various complex problems which are tedious and routine in nature. In order that a computer solve a problem, a method for the solution and a detailed procedure has to be prepared by the programmer. The problem solving Involves :
- Detailed study of the problem
- Problem redefinition
- Identification of input data, output requirements and conditions and limitations
- Alternative methods of solution
- Selection of the most suitable method
- Preparation of a list of procedures and steps to obtain the solution
- Generating the output

An **algorithm** is a sequence of instructinos designed in such a way that if the instructions are executed in a specific sequence the desried result will be obtained.
These instructions should be  precise and concise and the result should be obtained after a finite execution of steps. ***I.e. an algorithm should not repeat one or more instructions infinitely.***

*An algorithm should posses the following characteristics:*
- Each and every inst should be precise and clear.
- Each instructions should be performed a finite number of times.
- The algorithm should ultimately terminate.
- When the algorithm terminates the desired result should be obtained.
---
### Flowcharts
Before you start coding a program it is necessary to plan the step by step solution to the  task you program will carry out. Such a plan can be symbolically developed using a diagram. This diagram is called a *flowchart*. **Flowcharting** is a tool that can help us to develop and represent graphically program logic sequence. It also enables us to trace and detect any logical or other errors before the programs are written.

---
### Types of Flowcharts
- **Program Flowcharts** 
- **System Flowcharts**

**Program Flowcharts**. These are used by programmers. A program flowchart shows the program structure, logic flow and operations performed.  It also forms an important part of the documentation of the system. The emphasis in this type of flowchart is on the *logic*.It includes the ff.
- Program Structure
- Program Logic
- Data Inputs at various stages
- Data Processing
- Computations and Calculations
- Conditions on which decisions are based
- Branching & Looping Sequences
- Results
- Various Options

**System Flowcharts**. System flowcharts are used by system analyst to show various processes, sub systems, outputs and operations on data in a system. This is used for a way to display how data flows in a system and how decisions are made to control events.

---
###### Flowchart Symbols
Flowcharts use boxes of different shapes to denote different types of instructions. The actual instructions is written in the boxes.

The boxes which are used in flowcharts are standardized to have specific meanings. These flowchart symbols have been standardized by the American National Standard Institute.

*While using the flowchart symbols following points have to be kept in mind*: 
- The shape of the symbol is important and must not be changed
- The size can be changed as required.
- The symbol must be immediately recognizable.
- The details inside the symbol must be clearly legible. 
- The flow lines, as far as possible, must not cross.

### The symbols used in flowcharts
![[Pasted image 20220809134756.png]]

- **Start** - This is used to start or end a process
- **Preparation** - This is often used for declaration, like variable declaration, etc.
- **Process** - This box represents the arithmetic instructions or how the data(input) is processed.
- **Input or Output** - This represents the Input data taken from the user or program and output data, after the input data has been processed.
- **Decision** - This box represents a conditional statement. This is used for determining the different possibilities and routes the program will take.

---
### More information about the symbols
**Terminal Symbol**
Every flowchart has a unique *starting point* and an *ending point*. The flowchart <u>begins at the start terminator</u> and <u>ends at the stop terminator</u>. The *Starting Point* is indicated with the word ***START*** inside the terminator symbol. The *Ending Point* is indicated with the word ***STOP*** inside the terminator symbol. In case a program logic involves a pause, it is also indicated with the terminal symbol. Nonetheless, ***There can be only one START and STOP terminator in the entire flowchart***. 

##### I/O Symbol
This is used to denote any input/output function in the program. Like when an input is present such as a keyboard or an output is present such as printers or monitors.

##### Process Symbol
This is used to represent arithmetic and data movement instrcutions. The logical process of data movement form one memory location to another is also represented in the process box. If there are more than one process instructions to be executed sequentially, they can be placed in the same process box, one below the other in the sequence in which they are to be executed.

##### Decision Symbol
This is used to indicate the point where a decision is to be made and branching done upon the result of the decision to one or more alternative paths. The criteria or condition for decision making is written in the decision box.

##### Flowlines
These are solid lines with arrowheads which indicate the flow of operation. they show the exact sequence in which the instructions are to be executed. The normal flow of the flowchart is depicted from top to bottom and left to right.

##### Connectors
When flowcharts get big the flowlines start to cross each other and cause confusion. Thus whenever the flowchart  becomes complex and spreads over a number of pages, connectors are used. The *connector* represents the entry from or exit to another part of the flowchart.

A connector symbol is indicated by a circle and a letter or a digit is placed in the circle. This letter or digit indicates a link. A pair of such identically labelled connectors are used to indicate a continued flow.
