# Javascript Objects
JS object is a non-primitive data type that allows you to store multiple collections of data.

> **NOTE**: Unlike other programming languages, Javascript objects are a bit different in which you do not need to create classes in order to create objects.

Example of an JS Objects:
```js
const student = {
	firstName: 'ram',
	class: 10
};
```

Here, `student` is an object that stores values such as strings and numbers.

In JS, **key: value** pairs are called ***Properties***.

---
### Object Declaration
Syntax for object declaration:
```js
const object_name = {
	key1: value1,
	key2: value2
};
```
Here, an object `object_name` is defined. Each member of an object is a **key:value** pari separated by commas and enclosed in curly braces `{}`

You can also define an object in a signle line.
```js
const person = {name: 'john', age: 20};
```

In the above example, `name` and `age` are keys, and `john` and `20` are values respectively.