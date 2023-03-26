```toc
```

## Basics
- `print()` - The word print is the function name. This is a function that is used to print an output in the terminal. This is a **built-in** function

>To distinguish ordinary words from function names, place **a pair of empty parentheses**

The function name(e.g. print) along with the parentheses and argument(s), forms the **function invocation**

What happens when Python encounters an invocation like below?
```python
function_name(argument)
```

-   First, Python checks if the name specified is **legal** (it browses its internal data in order to find an existing function of the name; if this search fails, Python aborts the code);
-   second, Python checks if the function's requirements for the number of arguments **allows you to invoke** the function in this way (e.g., if a specific function demands exactly two arguments, any invocation delivering only one argument will be considered erroneous, and will abort the code's execution);
-   third, Python **leaves your code for a moment** and jumps into the function you want to invoke; of course, it takes your argument(s) too and passes it/them to the function;
-   fourth, the function **executes its code**, causes the desired effect (if any), evaluates the desired result(s) (if any) and finishes its task;
-   finally, Python **returns to your code** (to the place just after the invocation) and resumes its execution.

### TL;DR ha basics
- **Built-in functions**, contrary to user-defined functions, are always available and don't have to be imported. Python 3.8 comes with 69 built-in functions.
- To call a function(this process is known as **function invocation or function call**), you need to use the function name followed by parentheses.
- Python strings are delimited with **quotes**.
- Computer programs are collections of **instructions**
- In Python strings the backslash (`\`) is a special character which announces that the next character has a different meaning.
- **Positional arguments** are the ones whose meaning is dictated by their position.
- **Keyword arguments** are the ones whose meaning is not dictated by their location, but by a special work(keyword) used to identify them

## Literals
A **Literal** is data whose values are determined by the literal itself. You use literals *to encode data and to put them into your code*

### TL;DR han Literals
- A **Literal** are notations for representing some fixed values in code. Python has various types of literals - for example, a literal can be a number(`123`) or a string (`"Shun"`)
- The **Binary System** is a system of number that employs 2 as the base. Therefore, a binary number is made up of 0s and 1s only. **Octal** and **Hexadecimal** numeration systems, similarly, employ 8 and 16 as their bases respectively. The hexadecimal system uses the decimal numbers and six extra letters.
- **Integers** are one of the numerical types supported by Python. They are numbers written without fractional component. 
- **Floating-point** numbers are another one of the numerical types supported by python. They are numbers that contain(or are able to contain) a fractional component.
- **Boolean** values are two constant objects `True` and `False` used to represent truth values(in numeric context) `1` is `True` and `0` is `False` 
- `None` is a literal. This literal is a so-called `NoneType` object, and it is used to represent the absence of a value.

## Arithmetic operators and the hierarchy of priorities
An **Operator** is a symbol of the programming language, which is able to operate on the values.

### TL;DR hne na section
- An **expression** is a combination of values(or variables, operators, calls to functions) which evaluates to a certain value.
- **Operators** are special symbols or keywords which are able to operate on the values and perform operations.
- **Arithmetic operators** in Python: `+` (addition), `-` (subtraction), `*` (multiplication), `/` (classic division ‒ always returns a float), `%` (modulus ‒ divides left operand by right operand and returns the remainder of the operation, e.g., `5 % 2 = 1`), `**` (exponentiation ‒ left operand raised to the power of right operand, e.g., `2 ** 3 = 2 * 2 * 2 = 8`), `//` (floor/integer division ‒ returns a number resulting from division, but rounded down to the nearest whole number, e.g., `3 // 2.0 = 1.0`)
- A **unary** operator is an operator with only one operand, e.g., `-1`, or `+3`
- A **binary** operator is an operator with two operands, e.g., `4+5`, or `12 % 5`
- Some operators act before others – **the hierarchy of priorities**:
	-   the `**` operator (exponentiation) has the highest priority;
	-   then the unary `+` and `-` (note: a unary operator to the right of the exponentiation operator binds more strongly, for example: `4 ** -1` equals `0.25`)
	-   then `*`, `/`, `//`, and `%`;
	-   and, finally, the lowest priority: the binary `+` and `-`.
- Subexpressions in **parentheses** are always calculated first, e.g., `15 - 1 * (5 * (1 + 2)) = 0`.
- The **exponentiation** operator uses **right-sided binding**, e.g., `2 ** 2 ** 3 = 256`.


## Variables
A **Variable** is a container for data, as the name suggests; the data that it can contain varies in (almost) any way. Every python python variable has
- a name;
- a value(content of the container)

#### Rules in naming variables
-   the name of the variable must be composed of upper-case or lower-case letters, digits, and the character `_` (underscore)
-   the name of the variable must begin with a letter;
-   the underscore character is a letter;
-   upper- and lower-case letters are treated as different (a little differently than in the real world - _Alice_ and _ALICE_ are the same first names, but in Python they are two different variable names, and consequently, two different variables);
-   the name of the variable must not be any of Python's reserved words (the keywords - we'll explain more about this soon).

### TL;DR
- A **Variable** is a named location reserved to store values in the memory. A variable is created or initialized automatically when you assign a value to it for the first time.
- Each variable must have an **identifier**; a unique name for which the variable can be called. That name must be a non-empty sequence of characters, must being with the underscore, or a letter, and it cannot be a keyword. Python identifiers are case sensitive.
- Python is a **dynamically-typed** language, which means you don't need to _declare_ variables in it. (2.1.4.3) To assign values to variables, you can use a simple assignment operator in the form of the equal (`=`) sign, i.e., `var = 1`.
- You can also use **compound assignment operators** (shortcut operators) to modify values assigned to variables, e.g., `var += 1`, or `var /= 5 * 2`. (2.1.4.8)
- You can assign new values to already existing variables using the assignment operator or one of the compound operators, e.g.: (2.1.4.5)
```python
var = 2
print(var)

var = 3
print(var)

var += 1
print(var)
```
- You can combine text and variables using the `+` operator, and use the `print()` function to output strings and variables, e.g.: (2.1.4.4)
```python
var = "Sudaria"
print("Agent " + var)
```
## Comments
**Comments** are remarks inserted into the program, which are *omitted at runtime*

They are used to leave additional information in code for other programmers to read. In python, comments begin with a `#` symbol.
## Input function and string operators
The `input()` function **gets data from the console**. This built-in function comes with an optional parameter: *the prompt string*. It allows you to write a message before the user input.


```md
Notes By: Shawn Michael Sudaria
Software Used: Obsidian Notes
```
