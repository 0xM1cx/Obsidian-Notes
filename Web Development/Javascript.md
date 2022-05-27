## Rules for Naming Variables 
We know how to create variables, using the `var` and `let` keyword, naming the variable and assigning it a value. 

### Naming Convention
Given below are few general rules for naming a variable in JavaScript:

-   A variable name cannot start with a number. For example, `var 1n;` will lead to error.
-   JavaScript keywords cannot be used as the name of the variable. For example, `var new = 5;` will lead to an error, because `new` is a reserved keyword in JavaScript.
-   JavaScript is case-sensitive in nature. For example, `age=15;` and `AGE=15;` both are different variables.
-   The name of the variable must start either with a letter or an **underscore** `_`, or with a **dollar sign** `$`.
---
## Data types in JS
When we create a variable in JS, we create it to assign some value. The value that is assigned to a variable or the value that is stored in the variable is some data, which is of some type, it can be a number, a text, etc. this is know as **Datatype**

In JavaScript, we have some standard pre-defined datatypes. There are **seven types** of data types that can be divided into two main categories, which are given below:
-   Primitive
-   Non-primitive

### Primitive Data Types
Primitive means **basic**. Primitive data types are simple data types like a number or some text value. There are six data types in primitive type. These are: ***Numbers, String, Boolean, Null, Undefined***.

### Non-Primitive Data Types
The non-primitive data types has only one member which is the **Object**.

## Undefined and Null
When we create a new variable and do not assign any value to it, then the variable has **undefined** as its value.

On the other hand, we can assign a Null value to any variable using `null` keyword.

Hence, we can say that **undefined** is the default value of every variable until they are assigned any value. Whereas, **Null** value means none or void value, and we use the `null` keyword to assign Null value to any variable.

## Const keyword
The `const` keyword is used to assign a value that will never change. When it comes to **block scope** then the `const` variable behaves just like the `let` variables. It simply means that a variable declared using the `const` keyword within a block it **only available for use within that block.** Syntax:
```js
const var_name = "value";
```

## JavaScript Type Conversion
There are two types of type conversion in JavaScript.
-   **Implicit Conversion** - automatic type conversion
-   **Explicit Conversion** - manual type conversion

### Implicit Conversion
In certain situations, Javascript automatically converts one data type to another(to the right type)
```js
// numeric string used with + gives string type
let result;

result = '3' + 2; 
console.log(result) // "32"

result = '3' + true; 
console.log(result); // "3true"

result = '3' + undefined; 
console.log(result); // "3undefined"

result = '3' + null; 
console.log(result); // "3null"
```
```js
// numeric string used with - , / , * results number type

let result;

result = '4' - '2'; 
console.log(result); // 2

result = '4' - 2;
console.log(result); // 2

result = '4' * 2;
console.log(result); // 8

result = '4' / 2;
console.log(result); // 2
```
### Explicit Conversion
You can also convert one data type to another as per your needs. The type conversion that you do manually is known as explicit type conversion.

1. Convert to Number Explicitly
```js
let result;

// string to number
result = Number('324');
console.log(result); // 324

result = Number('324e-1')  
console.log(result); // 32.4

// boolean to number
result = Number(true);
console.log(result); // 1

result = Number(false);
console.log(result); // 0
```
In JS, empty strings and `null` values return **0**. E.g.
```js
let result;
result = Number(null);
console.log(result);  // 0

let result = Number(' ')
console.log(result);  // 0
```

If a string is an invalid number, the result will be `NaN`. E.g.
```js
let result;
result = Number('hello');
console.log(result); // NaN

result = Number(undefined);
console.log(result); // NaN

result = Number(NaN);
console.log(result); // NaN
```
2. To convert other data types to strings, you can use either `String()` or `toString()`. For example,
```js
//number to string
let result;
result = String(324);
console.log(result);  // "324"

result = String(2 + 4);
console.log(result); // "6"

//other data types to string
result = String(null);
console.log(result); // "null"

result = String(undefined);
console.log(result); // "undefined"

result = String(NaN);
console.log(result); // "NaN"

result = String(true);
console.log(result); // "true"

result = String(false);
console.log(result); // "false"

// using toString()
result = (324).toString();
console.log(result); // "324"

result = true.toString();
console.log(result); // "true"
```

> `String()` takes `null` and `undefined` and converts them to string. However, `toString()` gives error when `null is passed`

3. To convert other data types to a boolean, you can use `Boolean()`
In Javascript, `undefined`, `null`, `0`, `NaN`, `''` converts to `false`. Example:
```js
let result;
result = Boolean('');
console.log(result); // false

result = Boolean(0);
console.log(result); // false

result = Boolean(undefined);
console.log(result); // false

result = Boolean(null);
console.log(result); // false

result = Boolean(NaN);
console.log(result); // false

// Other examples give true.
result = Boolean(324);
console.log(result);

result = Boolean('hello');
console.log(result);

result = Boolean(' ');
console.log(result);
```
### Type Conversion Table
| **Value** | **String Conversion** | **Number Conversion** | **Boolean Conversion** |
| --- | --- | --- | --- |
| 1 | "1" | 1 | true |
| 0 | "0" | 0 | false |
| "1" | "1" | 1 | true |
| "0" | "0" | 0 | true |
| "ten" | "ten" | NaN | true |
| true | "true" | 1 | true |
| false | "false" | 0 | false |
| null | "null" | 0 | false |
| undefined | "undefined" | NaN | false |
| '' | "" | 0 | false |
| ' ' | " " | 0 | true |

## JS Comparison Operator
![[Pasted image 20220525101128.png]]
![[Pasted image 20220525101146.png]]

## Logical Operators
![[Pasted image 20220525101224.png]]

# Loops
Loops are helpful if you want to do a task repeatedly.

## for loops
For loop Syntax:
```js
for (initialExpression; condition; updateExpression){
	// for loop body
}
```
What's happening
1. The **initialExpression** initializes and/or declares variables and executes only once.
2. The **condition** is evaluated
	- If the condition is `false`, the for loop is terminated.
	- If the condition is `true`, the block of code inside of the `for`  loop is executed.
3. The **updateExpression** updates the value of **initialExpression** when the condition is `true`
4. The **condition** is evaluated again. This process continues until the condition is `false`
![[Pasted image 20220526203732.png]]

##### Example 1: Display a Text Five Times
```js
const n = 5;
for (let i = 1; i <= n; i++) {
	console.log("Hello there");
}
```

## while and do...while loop
Syntax for while loop
```js
while (condition) {
	// body of loop
}
```
Here,
1. A `while` loop evaluates the **condition** inside the parenthesis `()`.
2. If the **condition** evaluates to `true`, the code inside the `while` loop is executed.
3. The **condition** is evaluated again.
4. This process continues until the **condition** is `false`.
5. When the **condition** evaluates to `false`, the loop stops.
![[Pasted image 20220526210629.png]]

Syntax to do...while loop
```js
do {
	// body of loop
} while(condition)
```
Here, 
1.  The body of the loop is executed at first. Then the **condition** is evaluated.
2.  If the **condition** evaluates to `true`, the body of the loop inside the `do` statement is executed again.
3.  The **condition** is evaluated once again.
4.  If the **condition** evaluates to `true`, the body of the loop inside the `do` statement is executed again.
5.  This process continues until the **condition** evaluates to `false`. Then the loop stops.

`do...while` loop is similar to the `while` loop. The only difference is that in `do...while` loop, the body of loop is executed at least once.

![[Pasted image 20220527082937.png]]

## Break Statement
The `break` statement is used to terminate the loop immediately when it is encountered.

The syntax is:
```js
// note label is optional and rarely used.
break [label];
```
![[Pasted image 20220527083249.png]]

**Break inside nested loop**
```js
// nested for loops

// fist loop
for (let i = 1; i <= 3; i++){

	// second loop
	for (let j = 1; j <= 3; j++){
		if (i == 2) {
			break;
		}
		console.log(`i = ${i}, j = ${j}`);
	}
}
```

In the above program, when `i == 2`, `break` statement executes. It terminates the inner loop and control flow of the program moves to the outer loop.

Hence, the value of i = 2 is never displayed in the output.

## continue statement
The `continue` statement is used to skip the current iteration of the loop and the control flow of the program goes to the next iteration.

The syntax is:
```js
continue;
```

![[Pasted image 20220527085000.png]]

**Example: Calculate Positive Number**
```js
// program to calculate positive numbers only
// if the user enters a negative number, that number is skipped from calculation

// negative number -> loop terminate
// non-numeric character -> skip iteration

let sum = 0;
let number = 0;

while (number >= 0) {

    // add all positive numbers
    sum += number;

    // take input from the user
    number = parseInt(prompt('Enter a number: '));

    // continue condition
    if (isNaN(number)) {
        console.log('You entered a string.');
        number = 0; // the value of number is made 0 again
        continue;
    }

}

// display the sum
console.log(`The sum is ${sum}.`);
```

--- 
## Switch Statements
The JavaScript `switch` statement is used in decision making.

The `switch` statement evaluates an expression and executes the corresponding body that matches the expression's result.

The syntax of the `swtich` is:
```js
switch(variable/expression) {
    case value1:  
        // body of case 1
        break;

    case value2:  
        // body of case 2
        break;

    case valueN:
        // body of case N
        break;

    default:
        // body of default
}
```

The `switch` statement evaluates a variable/expression inside parentheses `()`.
- If the result of the expression is equal to `value1`, its body is executed.
- If the result of the expression is equal to `value2`, its body is executed.
- This process goes on. If there is no matching case, the `default` body executes.
![[Pasted image 20220527104314.png]]

**Example**
```js
// program using switch statement
let a = 2;

switch (a) {

    case 1:
        a = 'one';
        break;
    case 2:
        a = 'two';
        break;
    default:
        a = 'not found';
        break;
}
console.log(`The value is ${a}`);
```