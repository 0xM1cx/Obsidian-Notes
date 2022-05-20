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

---
In programming, a loop is used t repeat a block of code until the speceified condition is met.

## for loop
Syntax:
```c
for (initializationStatement; testExpression; updateStatement)
{
    // statements inside the body of loop
}
```
### How for loop works?
- The initialization statement is exeecuted only onnce.
- Then the test expression is evaluated. If the test expression is evaluated to false, the loop is terminated
- However, if the test expression is evaluated to true, statements inside the body of the for loop are executed, and the update expression is updated.
- Again the test expression is evaluated.

This process goes until the test expression is false. When the test expression is false, the loop terminates.
![[Pasted image 20220520090838.png]]

Example of for loop:
```c
#include <stdio.h>

int main() {
	int i;
	for (i = 1; i<11; ++i){
		printf("%d ", i);
	}
	return 0;
}
```
**Output**: `1 2 3 4 5 6 7 8 9 10`
1. `i` is initialized to 1.
2. The test expression `i < 11` is evaluated. Since 1 less than 11 is true, the body of `for` loop is executed. This will print 1(value of `i`) on the screen.
3. The update statement `++i` is executed. Now, the value of `i` will be 2. Again, the test expression is evaluated to true, and the body of `for` loop is executed. This will print 2(value of `i`) on the screen.
4. Again, the update statement `++i` is executed and the test expression `i < 11` is evaluated. This process goes on until `i` becomes 11.
5. When `i` becomes 11, `i < 11` will be false, and the `for` loop terminates.