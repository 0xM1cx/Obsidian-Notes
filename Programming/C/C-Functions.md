```toc
```
A function is a block of code that performs a specific task.

Suppose, you need to create a program to create a circle and color it. You can create two functions to solve this problem:
- circle functions
- color function

This way you can divide a complex problem into smaller chunks and makes our program easy to understand and reuse.

## Types of function
There are two types of function in C programming:
- **Standard library functions**
- **User-defined functions**

### Standard library functions
These are built-in functions in C. These functions are defined in header files. E.g.
- The `prinf()` is a standard library function to send formatted output to the screen(display output on the screen). This function is defined in the `#include <stdio.h>` header file.

### User-defined function
These are function that the user/programmer creates as per their need. E.g.
```c
#include <stdio.h>

void exerciseOne(){
	for(int i = 0; i <= 10; ++i){
		for(int b = 1; b <=i; ++b){
			printf("*");
		}
		printf("\n");
	}
}
int main(){
	exerciseOne();
}
```
In the above program when the compiler encounters `exerciseOne()`, control of the program jumps to that function. After the function is executed, control of the program jumps back to the `main()` function.

### Advantages of user-defined functions
1. The program will be easier to understand, maintain and debug.
2. Reusable codes that can be used in other programs
3. A large program can be divided into smaller modules. Hence, a large project can be divided among many programmers.

## User-defined functions

### Function prototype
A **function prototype** is simply the declaration of a function that specifies function's name, parameters and return type. It doesn't contain a function body.  This function gives information to the compiler that the function may later be used in the program.

#### Syntax of function prototype
```c
returnType functionName(type1 argument1, type argument2, ...);
```

An example would be:
```c
int userAge(int currentYear, int userBirthYear);
```
In the above example, it is a function prototype which provides the following to the compiler:
1. name of the function is `addNumbers()`
2. return type of the function is `int`
3. two arguments of type `int` are passed to the function

> The function prototype is not needed if the user-defined function is defined before the `main()` function.

### Function definition
Function definition contains the block of code to perform a specific task. 
#### Syntax of function definition
```c
returnType functionName(type argument){
	// body of the function
}
```
When a function is called, the control of the program is transferred to the function definition. And, the compiler starts executing the codes inside the body of the function.

### Return Statement
The **return statement** terminates the execution of a function and returns a value to the calling function. The program control is transferred to the calling function after the return statement.


#### Examples
```c
#include <stdio.h>
int addNumbers(int a, int b);         // function prototype

int main()
{
    int n1,n2,sum;

    printf("Enters two numbers: ");
    scanf("%d %d",&n1,&n2);

    sum = addNumbers(n1, n2);        // function call
    printf("sum = %d",sum);

    return 0;
}

int addNumbers(int a, int b)         // function definition   
{
    int result;
    result = a+b;
    return result;                  // return statement
}
```

[Revisit this page](https://www.programiz.com/c-programming/types-user-defined-functions)

## Recursion
A **recursive function** is a function that calls itself.


## Storage Class
Every variable in C programming has two properties: **Type** and **Storage class**

Types refers to the data type of a variable. And, storage class determines the scope, visibility and lifetime of a variable.

There are 4 types of storage class:
1. Automatic
2. External
3. Static
4. Register


### Local Variable
These are variable that are declared inside a block and are also called automatic variables. The local variable exist only inside the block in which it is declared.
**Example**
```c
#include <stdio.h>
int main(void){
	
	for(int i = 0; i<5; ++i){
		printf("Hello C");
	}

	// Error: i is not declared at this point
	printf("%d", i);
	return 0;
}
```
When you run the above program, you will get an error `undelcared identifier i`. It's because `i` is declared inside the `for` loop block. Outside of the block, it's undeclared.`

### Global Variable
These are variables declared outside of all functions and are known as external or global variables. They can be accessed from any function inside the program.
**Example**
```c
#include <stdio.h>
void display();

int n = 5;

int main(){
	++n;
	display();
	return 0;
}

void display(){
	++n;
	printf("n = %d", n);
}
```

Suppose, a global variable is declared in `file1`. If you try to use that variable in a different file `file2`, the compiler will complain. To solve this problem, keyword `extern` is used in `file2` to indicate that the external variable is declared in another file.