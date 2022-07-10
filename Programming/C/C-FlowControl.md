```toc
```
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
In programming, a loop is used t repeat a block of code until the specified condition is met.

## for loop
Syntax:
```c
for (initializationStatement; testExpression; updateStatement)
{
    // statements inside the body of loop
}
```

### How the for loop works?
- The initialization statement is executed only once.
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

## While Loop
```c
while (testExpression){
	// the body of the loop
}
```

### How the while loop works?
- The `while` loop evaluates the `testExpression` inside the parentheses.
- If the `testExpression` is true, the statements inside the body of the `while` loop are executed. Then, `testExpression` is evaluated again.
- The process goes on until `testExpression` is evaluated to false.
- If `testExpression` is false, the loop terminates.
![[Pasted image 20220710165405.png]]

Example while loop:
```c
#include <stdio.h>
int main() {
	int i = 1;

	while (i<=5) {
		printf("%d\n", i);
		++i;	
	}
return 0;
}

/*OUTPUT
1
2
3
4
5
*/
```
Here, we have initialized `i` to 1.
1. when `i = 1`, the test expression `i <= 5` is **true**. Hence, the body of the `while` loop is executed. This prints `1` on the screen and the value `i` is increased to `2`.
2. Now, `i=2`, the test expression `i<=5` is again **true**. The body of the `while` loop is executed again. This prints `2` on the screen and the value of `i` is increased to `3`.
3. This process repeats until `i` becomes 6. Then, the test expression `i<=5` will be **false** and the loop terminates.

## do...while loop
This is similar to the while loop, but the do...while loop is executed at least once. Only then, the test expression is evaluated.
Syntax:
```c
do {
	// body of the loop
} while (testExpression);
```