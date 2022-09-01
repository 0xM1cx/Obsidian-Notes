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
A **function prototype** is simply the declaration of a function that specifies function's name, parameters and return type. It doesn't contain a function body.