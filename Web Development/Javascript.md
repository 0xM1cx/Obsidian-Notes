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
