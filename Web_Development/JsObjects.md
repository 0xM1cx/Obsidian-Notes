# Javascript Objects
```toc
```
**JS object** is a non-primitive data type that allows you to store multiple collections of data.

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
Here, an object `object_name` is defined. Each member of an object is a **key: value** pair separated by commas and enclosed in curly braces `{}`

You can also define an object in a single line.
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

#### "this" keyword for accessing a property in a constructor 
To access a property of an object from within a method of the same object, you need to use the `this` keyword. Let's consider an example.
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

---
### JS Constructor Function
In JS, a constructor function is used to create objects. For example, 
```js
// constructor function
function Person (){
	this.name = 'Shawn',
	this.age = 23
}

const person = new Person();
```
In the above example, `function Person()` is an object constructor function.

To create an object from a constructor function, we use the `new` keyword.

> **NOTE**: It is considered a good practice to capitalize the first letter of your constructor function.

#### Create Multiple Objects with Constructors Function
You can create multiple objects from a constructor function. For example,
``` js
// Below is the constructor function
function Person() {
	this.name = "Shawn",
	this.age = 17,
	this.greet = function(){
		console.log('hello');
	}
}

// create objects
const person1 = new Person();
const person2 = new Person();

//access properties
console.log(person1.name); // Shawn
console.log(person2.name); // Shawn
```
In the above program, two objects are created using the same constructor function.

#### JS "this" Keyword
The `this` keyword is used in a constructor function, `this` refers to the objects when the object is created. In the program above when the object accesses the properties, it can directly access the property as `person1.name`  

#### Constructor Function Parameters
You can create a constructor function with parameters.
```js
// Below is the constructor function
function Person(person_name, person_age, person_gender){
	
	// assigning parameter values to the calling object
	this.name = person_name,
	this.age = person_age,
	this.gender = person_gender,
	this.greet = function(){
		return (`Hi ${this.name}`);
	}
}

// creating objects
const Person1 = new Person("Shawn", 17, "Male");

// accessing properties
console.log(Person1.name); // Shawn
console.log(Person1.age); // 17
```

#### Constructor Function vs Object Literal
In the previous topics you have seen two ways to create an object is JS, although there are more ways, the two discussed are the most used.

- **Object Literal** is generally used to create a single object. The **Constructor Function** is useful if you want to create multiple objects. 
```js
// Using object Literal
let Student = {
	Name: "Shawn", 
	Age: 17,
	Course: "BSIT"
};

// Using constructor function
function Student(StudentName){
	this.Name = StudentName,
	this.Age = 17,
	this.Course = "BSIT"
}

let StudentA = new Student("Shawn");
let StudentB = new Student("Martin");

```
Each object created from the constructor function is unique. You can have some similar properties or add a new property to one particular object.
```js
// Using constructor function
function Student(StudentName){
	this.Name = StudentName,
	this.Age = 17,
	this.Course = "BSIT"
}

// creating an object and setting the name
let StudentA = new Student("Shawn");
let StudentB = new Student("Martin");

// adding a new property to StudentA
StudentA.year = "1st";
```

However, if an object is created with an object literal, and if a variable is defined with that object value, any changes in variable value will change the original object.
```js
// Using object literal
let Student = {name:"Shawn"}
console.log(person.name); // Shawn

let studentA = Student;

// this changes the property of an object
studentA.name = "Martin";

// changes the origins object property
console.log(studentA.name); // Martin
```

Essentially, when an object is crated with an object literal, any object variable derived from that object will act as a clone of the original object. Hence, any change you make in one object will also reflect in the other object.