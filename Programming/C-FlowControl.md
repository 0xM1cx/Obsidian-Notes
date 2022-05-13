## if...else Statements
The syntax of the `if` statement in C programming is:
```c
if (test expression) 
{
   // code
}
```
### How if statement works?
The `if` statement evaluates the test expression inside the parenthesis `()`.
-   If the test expression is evaluated to true, statements inside the body of `if` are executed.
-   If the test expression is evaluated to false, statements inside the body of `if` are not executed.
**Example if statement**
```c
// Program to display a number if it is negative

#include <stdio.h>
int main() {
    int number;

    printf("Enter an integer: ");
    scanf("%d", &number);

    // true if number is less than 0
    if (number < 0) {
        printf("You entered %d.\n", number);
    }

    printf("The if statement is easy.");

    return 0;
}
```

**Example if...else statement**
```c
// Check whether an integer is odd or even

#include <stdio.h>
int main() {
    int number;
    printf("Enter an integer: ");
    scanf("%d", &number);

    // True if the remainder is 0
    if  (number%2 == 0) {
        printf("%d is an even integer.",number);
    }
    else {
        printf("%d is an odd integer.",number);
    }

    return 0;
}
```

