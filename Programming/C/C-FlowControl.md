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

Example of do...while loop:
```c
#include <stdio.h>
int main() {
	double number, sum = 0;

	//body of the loop is executed at least once
	do {
		printf("Enter a number: ");
		scanf("%lf", &number);
		sum += number;
	}
	while(number != 0.0);
	prinf("Sum = %.2lf", sum);
	return 0;
}

/* 
Output
Enter a number: 1.5
Enter a number: 2.4
Enter a number: -3.4
Enter a number: 4.2
Enter a number: 0
Sum = 4.70
*/
```

Here, we used the `do...while` loop to prompt the user to enter a number. The loop works as long as the input number is not `0` .

## break and continue
The **Break** statement ends the loop immediately when it is encountered. Its syntax is:
```c
break;
```
The break statement is almost always used with `if...else` statement inside the loop.

Example of using the break statement:
```c
// Program to calculate the sum of numbers (10 numbers max)
// If the user enters a negative number, the loop terminates

#include <stdio.h>

int main() {
   int i;
   double number, sum = 0.0;

   for (i = 1; i <= 10; ++i) {
      printf("Enter n%d: ", i);
      scanf("%lf", &number);

      // if the user enters a negative number, break the loop
      if (number < 0.0) {
         break;
      }

      sum += number; // sum = sum + number;
   }

   printf("Sum = %.2lf", sum);

   return 0;
}

/*
OUTPUT:
Enter n1: 2.4
Enter n2: 4.5
Enter n3: 3.4
Enter n4: -3
Sum = 10.30
*/
```

The `continue` statement skips the current iteration of the loop and continues with the next iteration. Its syntax is: 
```c
continue;
```
The `continue` statement is almost always used with the `if...else` statement.

Example of continue statement:
```c
// Program to calculate the sum of numbers (10 numbers max)
// If the user enters a negative number, it's not added to the result

#include <stdio.h>
int main() {
   int i;
   double number, sum = 0.0;

   for (i = 1; i <= 10; ++i) {
      printf("Enter a n%d: ", i);
      scanf("%lf", &number);

      if (number < 0.0) {
         continue;
      }

      sum += number; // sum = sum + number;
   }

   printf("Sum = %.2lf", sum);

   return 0;
}
/*
OUTPUT:
Enter n1: 1.1
Enter n2: 2.2
Enter n3: 5.5
Enter n4: 4.4
Enter n5: -3.4
Enter n6: -45.5
Enter n7: 34.5
Enter n8: -4.2
Enter n9: -1000
Enter n10: 12
Sum = 59.70
*/
```
 In this program, when the user enters a positive number, the sum is calculated using `sum += number;` statement.

When the user enters a negative number, the `continue` statement is executed and it skips the negative number from the calculation.

## Switch case
The switch statement allows us to execute one code block among many alternatives.

You can do the same thing with the `if...else...if` ladder. However, the syntax of the `switch` statement is much easier to read and write.

Syntax of switch...case
```c
switch (expression){
	case constant1:
		// statements
		break;

	case constant2:
		// statements
		break;

	case constant3:
		//statements
		break;

	default:
		// default statements
}
```

**How does the switch statement work?**
- The `expression` is evaluated once and compared with the values of each `case` label.
- if there is a match, the corresponding statements after the matching label are executed. For example, if the value of the expression is equal to `constant2` statements after `case constant2:` are executed until break is encountered.
- If there is not match, the default statements are executed. The `default` clause inside the `switch` statement is optional.

## goto Statement
The `goto` statement allows us to transfer control of the program to a specified `label`.

The `label` is an identifier. When the `goto` statement is encountered, the control of the program jumps to `label:` and starts executing the code.
![[Pasted image 20220731120126.png]]


Example:
```c
// Program to calculate the sum and average of positive numbers
// If the user enters a negative number, the sum and average are displayed.

#include <stdio.h>

int main() {

   const int maxInput = 100;
   int i;
   double number, average, sum = 0.0;

   for (i = 1; i <= maxInput; ++i) {
      printf("%d. Enter a number: ", i);
      scanf("%lf", &number);
      
      // go to jump if the user enters a negative number
      if (number < 0.0) {
         goto jump;
      }
      sum += number;
   }

jump:
   average = sum / (i - 1);
   printf("Sum = %.2f\n", sum);
   printf("Average = %.2f", average);

   return 0;
}
```

### Reasons to avoid goto
- The use of `goto` statement may lead to code that is buggy and hard to follow. 
- The `goto` statement allows you to do bad stuff such as jump out of the scope

`goto` can be useful sometimes. For example: to break from nested loops.

### Should you use goto?
If you think the use of `goto` simplifies your program. you can use it. That being said, `goto` is rarely useful and you can create any C program without using it.
## Lessons to practice/review


