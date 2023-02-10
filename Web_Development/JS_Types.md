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