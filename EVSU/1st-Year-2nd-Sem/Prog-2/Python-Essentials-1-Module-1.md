```toc
```
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

## Python Goals
In 1999, Guido van Rossum defined his goals for Python:
-   an **easy and intuitive** language just as powerful as those of the major competitors;
-   **open source**, so anyone can contribute to its development;
-   code that is as **understandable** as plain English;
-   **suitable for everyday tasks**, allowing for short development times.

#### Reasons why a lot of people use python
-   it's **easy to learn** - the time needed to learn Python is shorter than for many other languages; this means that it's possible to start the actual programming faster;
-   it's **easy to teach** - the teaching workload is smaller than that needed by other languages; this means that the teacher can put more emphasis on general (language-independent) programming techniques, not wasting energy on exotic tricks, strange exceptions and incomprehensible rules;
-   it's **easy to use** for writing new software - it's often possible to write code faster when using Python;
-   it's **easy to understand** - it's also often easier to understand someone else's code faster if it is written in Python;
-   it's **easy to obtain, install and deploy** - Python is free, open and multi-platform; not all languages can boast that.

#### python drawbacks
-   **it's not a speed demon** - Python does not deliver exceptional performance;
-   **in some cases it may be resistant to some simpler testing techniques** - this may mean that debugging Python's code can be more difficult than with other languages; fortunately, making mistakes is always harder in Python.

## Python Rivals
- **Perl** - a scripting language originally authored by *Larry Wall*;
- **Ruby** - a scripting language originally authored by *Yukihiro Matsumoto*

#### Why not Python?
-   **low-level programming** (sometimes called "close to metal" programming): if you want to implement an extremely effective driver or graphical engine, you wouldn't use Python;
-   **applications for mobile devices**: although this territory is still waiting to be conquered by Python, it will most likely happen someday.


## CPython
In addition to Python 2 and Python 3, there is more than one version of each.  There are Pythons which are maintained by the people around  PSF(Python Software Foundation), this is a community that aims to develop, improve, expand, and popularize python and its environment. The PSF's president is Pyhton's creator.

These Pythons are called **canonical**. They are also considered to be **reference Pythons**, as any other implementation of the language should follow all standards established by the PSF.

Guido van Rossum used the "C" programming language to implement the very first version of his language and this decision is still in force. All Pythons coming from the PSF are written in the "C" language. There are many reasons for this approach and it has many consequences. One of them (probably the most important) is that thanks to it, Python may be easily ported and migrated to all platforms with the ability to compile and run "C" language programs (virtually all platforms have this feature, which opens up many expansion opportunities for Python).

This is why the PSF implementation is often referred to as **CPython**. This is the most influential Python among all the Pythons in the world.

## Cython
Another python family member is **Cython** -- is on of a possible number of solutions to the most painful of Python's trait, lack of efficiency, large and complex math computations and time-consuming execution. 

This is what Cython is intended to do -- to automatically translate python code(clean and clear, but not to swift) into C code(complicated and talkative, but agile)

## Jython
Another version of Python is called Jython. This is Python written in Java instead of C. This is useful, for example, if you develop large and complex systems written entirely in java and want to add some Python flexibility to them.  Jython can communicate with existing Java infrastructure more effectively. 


## PyPy and RPython
PyPy represents a python environment written in Python-like language named *RPythone(Restricted Python)*. It's a subset of Python. The source code of PyPy is translated into C then executed separately.

This is useful because if you want to test any new feature that may be (but doesn't have to be) introduced into mainstream Python implementation, it's easier to check it with PyPy than with CPython. This is why PyPy is rather a tool for people developing Python than for the rest of the users.



```ts
let notesBy:string = "Shawn Michael Sudaria";
let dateCreated:number = 032523;
let noteSoftware:string = "Obsidian Notes";
```