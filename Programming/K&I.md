# C Keywords and Identifiers
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