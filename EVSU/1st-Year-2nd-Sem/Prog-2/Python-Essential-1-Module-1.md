
## Natural Languages vs Programming Languages
- A **language** is a means (and a tool) for expressing and recording thoughts.
- Computers have their own language called **Machine Language** which is very rudimentary.
- **Instruction List** - it is a complete set of known commands, sometimes abbreviated to **IL**
- **Natural Language** - This are languages that has developed naturally in use with Artificial Intelligence


### What makes a language?
A language, machine or natural, consists of the following elements:
- **Alphabet**
- **Lexis**
- **Syntax**
- **Semantics**

---
- **Source Code** is the name of a program written in a high-level programming language. In contrast to machine code executed by computers.
- **Source file** is the file containing the source code.

## Compilation vs Interpretation
- **Computer Programming** is the act of composing the selected programming language's elements in the order that will cause the desired effect. The composition has to be correct in many senses:

	-   **alphabetically** - a program needs to be written in a recognizable script, such as Roman, Cyrillic, etc.
	-   **lexically** - each programming language has its dictionary and you need to master it; thankfully, it's much simpler and smaller than the dictionary of any natural language;
	-   **syntactically** - each language has its rules and they must be obeyed;
	-   **semantically** - the program has to make sense.
---
There are two different ways of *transforming a program from a high-level programming language into machine language*:

**COMPILATION** - the source program is translated once (however, this act must be repeated each time you modify the source code) by getting a file (e.g., an .exe file if the code is intended to be run under MS Windows) containing the machine code; the program that performs this translation is called a *compiler* or *translator*;

**INTERPRETATION** - you (or any user of the code) can translate the source program each time it has to be run; the program performing this kind of transformation is called an interpreter, as it interprets the code every time it is intended to be executed; it also means that you cannot just distribute the source code as-is, because the end-user also needs the interpreter to execute it.


## What does the interpreter do?
The Interpreter reads the source code in a way that is common in Western Culture: from top to bottom and from left to right. There are some exceptions.

First, the interpreter checks if all subsequent lines are correct. If the interpreter finds an error, it finishes its work immediately. The interpreter will inform you where the error is located and what caused it.

If the line looks good, the interpreter tries to execute it (note: each line is usually executed separately, so the trio "read-check-execute" can be repeated many times - more times than the actual number of lines in the source file, as some parts of the code may be executed more than once).

It is also possible that a significant part of the code may be executed successfully before the interpreter finds an error. This is normal behavior in this execution model.


>  Due to historical reasons, languages designed to be utilized in the interpretation manner are often called **scripting languages**, while the source programs encoded using them are called **scripts**.


## What is Python?
**Python** is a widely-used, interpreted, object-oriented, and high-level programming language with dynamic semantics, used for general-purpose programming. The name came from the old BBC television comedy sketch series called *Monty Python's Flying Circus*

## Who Created Python?
Python was created by **[Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum)**, born in 1956 in Haarlem, the Netherlands. Of course, Guido van Rossum did not develop and evolve all the Python components himself.