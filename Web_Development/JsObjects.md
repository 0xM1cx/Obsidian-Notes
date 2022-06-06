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

A JS **method** is a property containing a function declaration. Here the JS method is an object property that has a function value.

#### Accessing Object Methods
You can access an object method using a dot notation:
```js
objectname.methodKey();
```
```js
// accessing method and property
const person = {
    name: 'John',
    greet: function() { console.log('hello'); }
};

// accessing property
person.name; // John

// accessing method
person.greet(); // hello
```
Here, the `greet` method is accessed as `person.greet()` instead of `person.greet`. If you try to access the method with only `person.greet`, it will give you a function definition. Example:
```js
person.greet; //f () {console.log('hello'); }
```

#### Adding a Method to a Javascript Object
You can also add a method in an object.
```js
// creating an object
let student = { };

// adding a property
student.name = 'John';

// adding a method
student.greet = function() {
    console.log('hello');
}

// accessing a method
student.greet(); // hello
```
In the above example, an empty `student` object is created. Then, the `name` property is added. Similarly, the `greet` method is also added. In this way, you can add a method as well as property to an object.

#### JS this Keyword
To access a property of an object from within a method of the same object, you need to use the `this` keyword. Let's cosider an example.
```js
const person = {
    name: 'John',
    age: 30,

    // accessing name property by using this.name
    greet: function() { console.log('The name is' + ' ' + this.name); }
};

person.greet();
```
In the above example, a `person` object is created. It contains properties (`name` and `age`) and a method `greet`.

In the method `greet`, while accessing a property of an object, `this` keyword is used.

In order to access the **properties** of an object, `this` keyword is used following the `.` and **key**

>**Note**: In JS, `this` keyword when used with the object's method refers to the objec. `this` is bound to an object.

However, the function inside of an object can access its variable in a similar way as a normal function would. For example:
```js
const person = {
    name: 'John',
    age: 30,
    greet: function() {
        let surname = 'Doe';
        console.log('The name is' + ' ' + this.name + ' ' + surname); }
};

person.greet();

```