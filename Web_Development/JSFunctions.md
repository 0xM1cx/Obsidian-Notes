```toc
```
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

> Note: When a value is passed when declaring a function, it is called **parameter**. And when the function is called, the value is passed is called **argument**.

#### Function return
The `return` statement can be used to return the value to a function call.

The `return` statement denotes that the function has ended. Any code after `return` is not executed.

If nothing is returned, the function returns an `undefined` value.

#### Benefits of Using a Function
- Function makes the code reusable. You can declare it once and use it multiple times.
- Function makes the program easier as each small task is divided into a function.
- Function increases readability.
---
### Function Expressions
In js, functions can also be defined as expressions.
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
1. **Global Scope**
2. **Local Scope**

---
### Global Scope
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

> **Note**: It is good practice to avoid using global variables because the value of a global variable can change in different areas in the program. It can introduce unknown results in the program.

---
In Javascript, a variable can also be used without declaring it. If a variable is used without declaring it, that variable automatically becomes a global variable.
Example: 
```js
function greet() {
    a = "hello"
}

greet();

console.log(a); // hello
```

> **Note:** In JS, there is `"strict mode"`; in which a variable cannot be used without declaring it.

### Local Scope
A variable can also have a local scope, it can only be accessed within a function.
```js
// program showing local scope of a variable
let a = "hello";

function greet() {
    let b = "World"
    console.log(a + b);
}

greet();
console.log(a + b); // error
```
In the above program, variable `a` is a global variable and variable `b` is a local variable. The variable `b` can be accessed only inside the function greet. Hence, when we try to access variable `b` outside of the function, <u>an error occurs</u>.

---
##### let keyword is Blocked Scoped
The `let` keyword is block-scoped (variable can be accessed only in the immediate block).
```js
// program showing block-scoped concept
// global variable
let a = 'Hello';

function greet() {

    // local variable
    let b = 'World';

    console.log(a + ' ' + b);

    if (b == 'World') {

        // block-scoped variable
        let c = 'hello';

        console.log(a + ' ' + b + ' ' + c);
    }

    // variable c cannot be accessed here
    console.log(a + ' ' + b + ' ' + c);
}

greet();
```
In the above program, variable
-   `a` is a global variable. It can be accessed anywhere in the program.
-   `b` is a local variable. It can be accessed only inside the function `greet`.
-   `c` is a block-scoped variable. It can be accessed only inside the `if` statement block.

Hence, in the above program, the first two `console.log()` work without any issue.

However, we are trying to access the block-scoped variable c outside of the block in the third `console.log()`. This will throw an error.
> **Note:** `var` is function scoped and `let` is block-scoped. If you try to use `var c = 'hello';` inside the `if` statement in the above program, the whole programwords, as `c` is treated as a local variable.

## Hoisting
**Hoisting** is a behavior in which a function or a variable can be used before declaration. E.g.
```js
// using name variable before declaring it.
console.log(name); // undefined
var name; 
```

The above program works and the output will be `undefined`. 
### Variable Hoisting
In terms of variables and constants, keywords `var` is hoisted and `let` and `const` does not allow hoisting. For Example:
```js
// program to display value
a = 5;
console.log(a);
var a; //5
```
In the above example, variable `a` is used before declaring it. And the program works and displays the output `5`. The program behaves as:
```js
// program to display value
var a;
a = 5;
console.log(a); // 5
```

However, in JS initialization are not hosted only variable declarations are hoisted.

Also, when the variable is used inside the function, the variable is hoisted only to the top of the function. For example, 
```js
var a = 4;

function greet() {
	b = "hello";
	console.log(b); // hello
	var b;
}

greet();
console.log(b);
```

In the above example, variable `b` is hoisted to the top of the function `greet` and becomes local variable. Hence `b` is only accessible inside the function. `b` does not become a global variable.

> **NOTE**: In hoisting, the variable declaration is only accessible to the immediate scope.

### Function Hoisting
A function can be called before declaring it. For example:
```js
// program to print the text
greet();

function greet() {
	console.log('Hi, there.');
}
```

In the above program, then function `greet` is called before declaring it and the program shows the output. This is due to hoisting.

--- 
However, when a function is used as an **expression**, an error occurs because only declarations are hoisted. For example:
```js
// Program to print text
greet();

let greet = function(){
	console.log("hello");
}
```

## Recursion
**Recursion** is a process of calling itself. A function that calls itself is called a **recursive function**.

Example:
```js
function recurse(){
	// function code
	recurse();
}

recurse();
```

Here the `recurse()` function is a recursive function. It is calling itself inside the function.
![[Pasted image 20220601143912.png]]

A recursive function must have a condition to stop calling itself. Otherwise, the function is called **indefinitely**. Once the condition is met, the function stops calling itself. This is called a **base condition**. To prevent infinite recursion, you can use `if...else` statement(or similar approach) where one branch makes the recursive call, and the other doesn't

So, it generally looks like this.
```js
function recurse(){
	if(condition) {
		recurse();
	}
	else {
		// stop callling recurse()
	}
}

recurse();
```

Example of a program that uses this function is at `~Documents/Javascript-Study/Day7.js`

## Lessons to Review/practice
- [ ] Hoisting
- [ ] Recursion
- [ ] [Practice with these questions](https://www.w3resource.com/javascript-exercises/javascript-basic-exercises.php)