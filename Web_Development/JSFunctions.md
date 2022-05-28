## Functions
A function is a block of code that performs a specific task.

Suppose you need to create a program to create a circle and color it. You can create two function to solve this problem:
- a function to draw this circle
- a function to color the circle

Dividing a complex problem into smaller chunks makes your program easy to understand and reusable.

JavaScript also has a huge number of inbuilt functions. For example, `Math.sqrt()` is a function to calculate the square root of a number.

In this tutorial, you will learn about user-defined functions.

---
### Declaring a function
The syntax to declare a function is:
```js
function nameOfFunction(){
	// function body
}
```

- A function is declared using the `function` keyword.
- The basic rules of naming a function are similar to naming a variable. It is better to write a descriptive name for your function. For example, if a function is used to add two numbers, you could name the function `add` or `addNumbers`.
- The body of function is written within `{}`.

#### Function Parameters
A function can also be declared with parameters. A parameter is a value that is passed when declaring.
![[Pasted image 20220528103758.png]]

```js
// program to print the text
// declaring a function
function greet(name) {
    console.log("Hello " + name + ":)");
}

// variable name can be different
let name = prompt("Enter a name: ");

// calling function
greet(name);
```

> Note: When a value is passed when declaring a function, it is called **parameter**. And when the function is called, the value is passed is called **arguemnt**.

#### Function return
The `return` statement can be used to return the value to a function call.

The `return` statement denotes that the function has ended. Any code after `return` is not executed.

If nothing is returned, the function returns an `undefined` value.

#### Benefits of Using a Function
- Function makes the code reusable. You can declare it once and use it multiple times.
- Function makes the program easier as each small task is divided into a function.
- Function increases readability.
---
#### Function Expressions
In js, functions can alsobe defined as expressions.
```js
// program to find the square of a number
// function is declared inside the variable
let x = function (num) { return num * num };
console.log(x(4));

// can be used as variable value for other variables
let y = x(3);
console.log(y);
```

> **NOTE:** in ES2015, Javascript expressions are written as arrow functions.

## JS Variable Scope
Scope referes to the availability of variables and functions in certain parts of the code.

In JS, a variable has two types of scope:
1. Global Scope
2. Local Scope

---
#### Global Scope
A variable declared at the top of a program or outside of a function is considered a global scope variable.
Example:
```js
let a = "hello";

function greet() {
	console.log(a);
}

greet();
```

In the above program, variable `a` is declared at the top and is a global variable. It means that this variable can be used anywhere in the program.