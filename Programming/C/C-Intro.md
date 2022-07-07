 # C Intro
## Character set

A character set is a set of alphabets, letters and some special characters that are valid in C language.

### Alphabets
```c
Uppercase: A B C ................................... X Y Z
Lowercase: a b c ...................................... x y z
```

C accepts both lowercase and uppercase alphabets as variables and functions.

### Digits
```c
0 1 2 3 4 5 6 7 8 9
```

**White space Characters**
Blank space, newline, horizontal tab, carriage return and form feed.

### Keywords
These are predefined, reserved words used in programming that have special meanings to the compiler. Keywords are part of the syntax and they cannot be used as an identifier. E.g. `int`
### Identifiers
These refer to name given to entities such as variables, functions, structures etc.

Identifiers must be unique. They are created to give a unique name to an entity to identify it during the execution of the program. E.g. `money`
```c
int money
```

### Rules of naming identifiers
1.  A valid identifier can have letters (both uppercase and lowercase letters), digits and underscores.
2.  The character of an identifier should be either a letter or an underscore.
3.  You cannot use keywords like `int`, `while` etc. as identifiers.
4.  There is no rule on how long an identifier can be. However, you may run into problems in some compilers if the identifier is longer than 31 characters.

You can choose any name as an identifier if you follow the above rule, however, give meaningful names to identifiers that make sense.

# Variables
In programming, a variable is a container (storage area) to hold data.

To indicate the storage area, each variable should be given a unique name (identifier). Variable names are just the symbolic representation of a memory location. For example:
```c
int playerScore = 95; 
```

# Input Output (I/O)
In C programming, `printf()` is one of the main output function. The function sends formatted output to the screen. For example,
```c
#include <stdio.h>    
int main(){ 
    // Displays the string inside quotations
    printf("C Programming");
    return 0;
}
```

#### Input
In C programming, `scanf()` is one of the commonly used function to take input from the user. The `scanf()` function reads formatted input from the standard input such as keyboards.
```c
#include <stdio.h>
int main(){
    int testInteger;
    printf("Enter an integer: ");
    scanf("%d", &testInteger);  
    printf("Number = %d",testInteger);
    return 0;
}
```
Here, we have used `%d` format specifier inside the `scanf()` function to take `int` input from the user. When the user enters an integer, it is stored in the testInteger variable.

**Example for characters**
```c
#include <stdio.h>
int main()
{
    char chr;
    printf("Enter a character: ");
    scanf("%c",&chr);     
    printf("You entered %c.", chr);  
    return 0;
}   
```
When a character is entered by the user in the above program, the character itself is not stored. Instead, an integer value (ASCII value) is stored.

And when we display that value using `%c` text format, the entered character is displayed. If we use `%d` to display the character, it's ASCII value is printed.

# Comments
In programming, comments are hints that a programmer can add to make their code easier to read and understand. For example,
```c
#include <stdio.h>

int main() {

  // print Hello World to the screen
  printf("Hello World");
  return 0;
}
```

## Types of Comments
There are two ways to add comments in C:

1.  `//` - Single Line Comment
2.  `/*...*/` - Multi-line Comment

## Operators
An operator is a symbol that operates on a value or a variable. For example: + is an operator to perform addition.

C has a wide range of operators to perform various operations.
***Arithmetic Operators***
| **Operator** | **Meaning of Operator**                    |
| ------------ | ------------------------------------------ |
| +            | Addition or unary plus                     |
| -            | Subtraction or unary minus                 |
| *            | Multiplication                             |
| /            | Division                                   |
| %            | remainder after division (modulo division) |              |                                            |
 ***Increment and Decrement Operators***
 C programming has two operators increment `++` and decrement `--` to change the value of an operand (constant or variable) by 1.

Increment `++` increases the value by 1 whereas decrement `--` decreases the value by 1. These two operators are unary operators, meaning they only operate on a single operand.
**++ and -- operator as prefix and postfix
-   If you use the `++` operator as a prefix like: `++var`, the value of var is incremented by 1; then it returns the value.
-   If you use the `++` operator as a postfix like: `var++`, the original value of var is returned first; then var is incremented by 1.

***Assignment Operators***
| **Operator** | **Example** | **Same as**   |
| -------- | ------- | --------- |
| =        | a = b   | a = b     |
| +=       | a += b  | a = a+b   |
| -=       | a -= b  | a = a-b   |
| \*=      | a \*= b | a = a * b |
| /=       | a /= b  | a = a / b |
| %=       | a %= b  | a = a % b          |
An assignment operator is used for assigning a value to a variable. The most common assignment operator is `=`
```c
// Working of assignment operators
#include <stdio.h>
int main() {
    int a = 5, c;

    c = a;      // c is 5
    printf("c = %d\n", c);
    c += a;     // c is 10 
    printf("c = %d\n", c);
    c -= a;     // c is 5
    printf("c = %d\n", c);
    c *= a;     // c is 25
    printf("c = %d\n", c);
    c /= a;     // c is 5
    printf("c = %d\n", c);
    c %= a;     // c = 0
    printf("c = %d\n", c);

    return 0;
}
```

***Relational Operators***
A relational operator checks the relationship between two operands. If the relation is true, it returns 1; if the relation is false, it returns value 0.

Relational operators are used in [decision making](https://www.programiz.com/c-programming/c-if-else-statement "C if else") and [loops](https://www.programiz.com/c-programming/c-for-loop "C for loop").
| **Operator** | **Meaning of Operator**      | **Example**                  |
| -------- | ------------------------ | ------------------------ |
| ==       | Equal to                 | 5 == 3 is evaluated to 0 |
| >        | Greater Than             | 5 > 3 is evaluated to 1  |
| <        | Less Than                | 5 < 3 is evaluated to 0  |
| !=       | Not Equal to             | 5 != 3 is evaulated to 1 |
| >=       | Greater Than or Equal to | 5 >= 3 is evaluated to 1 |
| <=       | Less Than or Equal to    | 5 <= 3 is evaluated to 0                         |
```c
// Working of relational operators
#include <stdio.h>
int main()
{
    int a = 5, b = 5, c = 10;

    printf("%d == %d is %d \n", a, b, a == b); //True
    printf("%d == %d is %d \n", a, c, a == c); // False
    printf("%d > %d is %d \n", a, b, a > b); // False
    printf("%d > %d is %d \n", a, c, a > c); // False
    printf("%d < %d is %d \n", a, b, a < b); // False
    printf("%d < %d is %d \n", a, c, a < c); // True
    printf("%d != %d is %d \n", a, b, a != b); // False
    printf("%d != %d is %d \n", a, c, a != c); // True
    printf("%d >= %d is %d \n", a, b, a >= b); // True
    printf("%d >= %d is %d \n", a, c, a >= c); // False
    printf("%d <= %d is %d \n", a, b, a <= b); // True
    printf("%d <= %d is %d \n", a, c, a <= c); // True

    return 0;
}
```
 
 ***Logical Operators***
 An expression containing logical operator returns either 0 or 1 depending upon whether expression results true or false. Logical operators are commonly used in [decision making in C programming](https://www.programiz.com/c-programming/c-if-else-statement "C if else").
```c
// Working of logical operators

#include <stdio.h>
int main()
{
    int a = 5, b = 5, c = 10, result;

    result = (a == b) && (c > b);
    printf("(a == b) && (c > b) is %d \n", result);

    result = (a == b) && (c < b);
    printf("(a == b) && (c < b) is %d \n", result);

    result = (a == b) || (c < b);
    printf("(a == b) || (c < b) is %d \n", result);

    result = (a != b) || (c < b);
    printf("(a != b) || (c < b) is %d \n", result);

    result = !(a != b);
    printf("!(a != b) is %d \n", result);

    result = !(a == b);
    printf("!(a == b) is %d \n", result);

    return 0;
}

```

***Bitwise Operators***
During computation, mathematical operations like: addition, subtraction, multiplication, division, etc are converted to bit-level which makes processing faster and saves power.

Bitwise operators are used in C programming to perform bit-level operations.
| **Operator** | **Meaning of Operator** |
| ------------ | ----------------------- |
| &            | Bitwise AND             |
| \|           | Bitwise OR              |
| ^            | Bitwise exclusive OR    |
| ~            | Bitwise complement      |
| <<           | Shift left              |
| >>           | Shift right             | 

***Other Operators***

**Comma Operator**
Comma operators are used to link related expressions together. For example:
```c
int a, c = 5, d;
```

**sizeof Operator**
```c
#include <stdio.h>
int main()
{
    int a;
    float b;
    double c;
    char d;
    printf("Size of int=%lu bytes\n",sizeof(a)); // 4bytes
    printf("Size of float=%lu bytes\n",sizeof(b)); // 4bytes
    printf("Size of double=%lu bytes\n",sizeof(c));//8 bytes
    printf("Size of char=%lu byte\n",sizeof(d)); // 1 byte

    return 0;
}
```
