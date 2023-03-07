```toc
```
## Arrays
An **array** is an object that can store multiple values at once.
```js
const students = ["Shawn", "Crystal", "Jason", "Ruffa", "Zyra"];
```

### Add an Element to an Array
You can use the build-in method `push()` and `unshift()` to add elements to an array.

The `push()` method adds an element at the end of the array.
```js
let ages = [18, 19];
ages.push(20) // [18, 19, 20]
```

The `unshift()` method adds an element at the beginning of the array.
```js
let ages = [18, 19];
ages.unshift(20); // [20, 18, 19]
```

### Remove an Element from an Array
You can use the `pop()` method to remove the last element from an array. This method also returns the values.
```js
let ages = [18, 19];
const myage = ages.pop() // 19
```

If you need to remove the first element, you can use the `shift()` method. The shift method removes the first element and also return it.
```js
let ages = [18, 19]
const myage = ages.shift(); // 18
```

### Array length 
You can find the length of an element(the number of elements in an array) using the `length` property. 
```js
const ages = [18, 19, 20];
console.log(ages.length) // 3
```

### Array Methods
There are various array methods available that makes it easier to perform useful calculation.
| **METHODS**   | **DESCRIPTION**                                                                        |
| ------------- | -------------------------------------------------------------------------------------- |
| `concat()`    | joins two or more arrays and returns a result                                          |
| `indexOf()`   | searches an element of an array and returns its position                               |
| `find()`      | returns the first value of an array element that passes a test                         |
| `findIndex()` | returns the first index of an array element that passes a test                         |
| `forEach()`   | calls a function for each element                                                      |
| `includes()`  | checks if an array contains a specified element                                        |
| `push()`      | adds a new element to the end of an array and returns the new length of an array       |
| `unshift()`   | adds a new element at the beginning of an array and returns the new length of an array |
| `pop()`       | removes the last element of an array and returns the removed element                   |
| `shift()`     | removes the first element of an array and returns the removed element                  |
| `sort()`      | sorts the elements alphabetically in strings and in ascending order                    |
| `slice()`     | selects the part of an array and returns the new array                                 |
| `splice()`    | removes or replaces existing elements and/or adds new element.                         |
                                                                                       |
## Multidimensional Arrays
A **Multidimensional Array** is an array that contains another array.
```js
const numbers = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
```

### Adding an element to the multidimensional array
```js
const numbers = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
numbers.push([12, 31, 155]);
```

### Adding an element to the inner array
```js
const numbers = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
numbers[0][0] = 15;
```

## Strings
### Multiline Strings
```js
// using the + operator
const message1 = 'This is a long message ' +
    'that spans across multiple lines' + 
    'in the code.'

// using the \ operator
const message2 = 'This is a long message \
that spans across multiple lines \
in the code.'
```
### String Methods
| **METHOD**              | **DESCRIPTION**                                         |
| ----------------------- | ------------------------------------------------------- |
| `charAt()`              | returns the character at the specified index            |
| `concat()`              | joins two or more strings                               |
| `replace()`             | replaces a string with another strings                  |
| `split()`               | converts the string to an array of strings              |
| `substr(start, length)` | returns a part of a string                              |
| `substring(start, end)` | returns a part of a string                              |
| `slice(start, end)`     | returns a part of a string                              |
| `toLowerCase()`         | returns the passed string in lowercase                  |
| `toUpperCase()`         | returns the passed string in uppercase                  |
| `trim()`                | removes whitespaces from the string                     |
| `includes()`            | searches for a string and returns a boolean value       |
| `search()`              | searches for a string and returns a position of a match |


### String() Function
This function is used to convert data types to strings.
```js
const age = 18;
console.log(String(age)); // "18"
```

## for...in loop
In each iteration of the loop, a key is assigned to the `key` variables. The  loop continues for all object properties.
```js
for(key in object){
	// statements
}```
>Once you get the keys above, you can easily find their corresponding values


### for...in string
You can use `for...in` loop to iterate over string values.
```js
let name = "Shawn";
for(let char in name){
	console.log(name[char]);
}
```

## Number
Numbers in JS are primitive data types. Unlike other languages, you don't have to specifically declare for integer or floating values using *int*, *float*, etc.

You can use exponential notation **e** to include too large or too small numbers.
```js
const a = 5e9; // 500000000
const b = 5e-5; // 0.00005

```

Numbers can also be denoted in hex notation
```js
const a = 0xff; // 255
```

### NaN
**NaN(Not a Number)** is a keyword that indicates that the value is not a number.
```js
const a = isNan(9) // false because 9 is a number
const name = isNaN("Shawn") // true
const test = isNaN(4 - name); // true because the output is not a number
```

### Infinity
When calculation is done that exceeds the largest(or smallest) possible number, `Infinity`(for -Infinity) is return

### BigInt
A number type can only represent numbers less than(2^53 - 1) and more than -(2^53-1). However, if you need to use larger than that, you can use the BigInt data type. A **BigInt** number is created by appending **n** to the end of an integer.
```js
const value = 900719925124740998n;
// Adding two big integers
const value2 = value + 1n;
console.log(value2); // 900719925124740999
```

### Number Methods
| **METHOD**                      | **DESCRIPTION**                                               |
| ------------------------------- | ------------------------------------------------------------- |
| `isNaN()`                       | determines whether the passed value is Nan                    |
| `isFinite()`                    | determines whether the passed value is a finite number        |
| `isInteger()`                   | determines whether the passed value is an integer             |
| `isSageInteger()`               | determines whether the passed value is a safe integer         |
| `parseFloat(string)`            | converts the numeric floating string to floating-point number |
| `parseInt(string, [radix])`     | converts the numeric string to integer                        |
| `toExponential(fractionDigits)` | returns a string value for a number in exponential notation   |
| `toFixed(digits)`               | returns a string value for a number in fixed-point notation   |
| `toPrecision()`                 | returns a string value for a number to a specified precision  |
| `toString([radix])`             | returns a string value in a specified radix(base)             |
| `valueof()`                     | return the numbers value                                      |
| `toLocaleString()`              | returns a string with a language sensitive representation of number                                                              |
