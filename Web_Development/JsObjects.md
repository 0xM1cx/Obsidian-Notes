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

### Accessing Object Properties
You can access the **value** of a property by using a **key**.
1. Using dot Notation
Syntax:
```js
objectName.key
```
```js
//Example
const person = {
	name: 'john',
	age: 20
};

//accessing property
console.log(person.name); // output: john

```
2. Using bracket Notation
Syntax:
```js
objectName["propertyName"]
```
```js
//Example
const person = {
	name: 'john',
	age: 20
};

// accessing property
console.log(person['name']);
```
---
### Nested Objects
An object can also contain another object. Example:
```js
// nested object
const student = {
	name: 'john',
	age: 20,
	marks: {
		science: 96,
		math: 94
	}
};

// accessing property of student object.
console.log(student.marks);
// accessing property of marks object.
console.log(student.marks.science);
```
In the above example, an object `student` contains an object value in the `marks` property.

---
### Object Methods
An object can also contain function. Example
```js
const person = {
	name: 'Shawn',
	age: 17,
	// using a function as value
	welcome_user: function () { console.log(`welcome ${person.name}`)}
};

person.welcome_user();
```

A JS **method** is a property containing a function declaration.