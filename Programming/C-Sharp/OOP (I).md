C# is an object-oriented programming language. In OOP, we solve complex problems by dividing them into objects.
## Class
A **Class** is a like a prototype or blueprint of a house. It contains all the details about the floors, doors, windows, etc. We can build a house based on these descriptions. The house is the object.

Creating a Class:
```cs
class ClassName{
	// fields
	var product;
	string name;
	int age;

	// method
	public void bark(){
		// statements
	}
}
```
A class can contain:
- **fields** - variables to store data
- **methods** - functions to perform specific tasks

## Objects
An **Object** is an instance of a class. To create an instance of a class you use the `new` keyword.
```cs
ClassName obj = new ClassName();
```

#### Accessing class members using object
Using the `.` operator lets you access members of the class.
```cs 
using System;

namespace ClassObject {

  class Dog {
    string breed;

    public void bark() {
      Console.WriteLine("Bark Bark !!");
      
    }

    static void Main(string[] args) {

      // create Dog object 
      Dog bullDog = new Dog(); // the new keyword is used to create an object of the class and bullDog is the name of the object.

      // access breed of the Dog 
      bullDog.breed = "Bull Dog";
      Console.WriteLine(bullDog.breed);

      // access method of the Dog
      bullDog.bark();   

      Console.ReadLine();
    }
  }
}
```
### Why Objects and Classes?
Objects and classes help us to divide a large project into smaller sub-problems. Suppose you want to create a game that has hundreds of enemies and each of them has fields like `health`, `amo`, and methods like `shoot` and `run`.

With Object Oriented Programming we can create a single `Enemy` class with required fields and methods. Then, we can create multiple enemy objects from it. Instead of thinking of projects in terms of variables and methods, we can think of them in terms of objects.

### Method Overloading
Create two methods with the same name is called name is known as method overloading. In a class there might be two or more methods with the same name but different numbers, types, and order of parameters, it is called **method overloading**. Overloaded methods may have the same or different return types, but they must have different parameters.
```cs
using System;

namespace MethodOverload {

  class Program {  

    // method with one parameter
    void display(int a) {
      Console.WriteLine("Arguments: " + a);
    }
 
    // method with two parameters
    void display(int a, int b) {
      Console.WriteLine("Arguments: " + a + " and " + b);
    } 
    static void Main(string[] args) {

      Program p1 = new Program();
      p1.display(100);
      p1.display(100, 200);
      Console.ReadLine();
    }
  }
}
```

In the program above, we have overloaded the `display()` method. It is possible because:
- one method has one parameter
- another has two parameters

### Performing method overloading
1. By Changing the number of Parameters
   We can overload the method if the number of parameters in the method is different.
2. By changing the data type of the parameters
3. By changing the Order of the parameters

## Access Modifiers
**Access Modifiers** specify the accessibility of types(class, interface, etc) and type members (fields, methods, etc)
```cs
class Student{
	public string name;
	private int num;
}
```
Here, 
- `name` - public field that can be accessed from anywhere
- `num` - private field can only be accessed within the `Student` class

**Types of Access Modifiers**
In C#, there are 4 basic types of access modifiers
- **public** - When we declare a type or type member public, it can be accessed from anywhere.
- **private** - When we declare a type member private, it can only be accessed within the same `class` or `struct`
- **protected** - When the type is declared as `protected`, it can only be accessed from the same class and its derived classes.
- **internal** - When we declare a type or type member as `internal`, it can be accessed only within the same assembly.
  An *assembly* is a collection of types(classes, interfaces, etc) and resources(data). They are build to work together and form a logical unit of functionality.
- **protected internal** - This is a combination of `protected` and `internal` access modifiers. Using this, a member can be accessed form the same assembly and the derived class of the containing class from another assembly.
- **private protected** - This is a combination of `private` and `protected`. It can only be accessed within the same class, and its derived class within the same assembly.


## Variable Scope
A **variable scope** refers to the availability of variables in certain parts of the code.

### Class Level Variable Scope
- When we declare a variable inside a class, the variable can be accessed within the class. This is known as **class level variable scope**. Class level variables are also known as *fields* and they are declared outside of methods, constructors, and blocks of the class.

### Method Level Variable Scope
- When we declare a variable inside a method, the variable canned be accessed outside the method. This is **method level variable scope**.

### Block Level Variable Scope
- When we declare a variable inside a block(for loop, while loop, if...else), the variable can only be accessed within the block. This is known as **block level variable scope**


## Constructors
A **constructor** is similar to a method that is invoked when an object of the class is created. However, unlike methods, a constructor:
- has the name as that of the class
- does not have any return type

```cs
class Car{
	// constructor
	Car(){
	// statements
	}
}
```
Here, `Car()` is a constructor. It has the same name as its class.

### Call a constructor
Once we create a constructor, we can call it using the `new` keyword.
```cs
new Car();
```
In C#, a constructor is called when we try to create an object of a class.
```cs
Car car1 = new Car();
```

### Types of Constructors
1. **Parameterless Constructor**
   When we create a constructor without parameters, it is known as a parameterless constructor.
```cs
using System;

namespace Constructor {

  class Car {   

    // parameterless constructor
    Car() {
      Console.WriteLine("Car Constructor");
    }
 
    static void Main(string[] args) {

      // call constructor
      new Car();
      Console.ReadLine();
     
    }
  }
}
```
2. **Parameterized Constructor**
   In contrast, this type of constructor takes in parameters.
   ```cs
   using System;

namespace Constructor {

  class Car {   

    string brand;
    int price;

    // parameterized constructor
    Car(string theBrand, int thePrice) {

      brand = theBrand;
      price = thePrice;
    }
  
    static void Main(string[] args) {

      // call parameterized constructor
      Car car1 = new Car("Bugatti", 50000);

      Console.WriteLine("Brand: " + car1.brand);
      Console.WriteLine("Price: " + car1.price);
      Console.ReadLine();
     
    }
  }
}
```
3. **Default Constructor**
   If we have not defined a constructor in a class, then C# will automatically create a default constructor with an empty code and no parameters. **NOTE:** <u>In the default constructor, all the numeric fields are initialized to 0, whereas string and object are initialized as null.</u>
   ```cs
   using System;

namespace Constructor {

  class Program {  

    int a;

    static void Main(string[] args) {

      // call default constructor
      Program p1 = new Program();

      Console.WriteLine("Default value of a: " + p1.a);
      Console.ReadLine();
    }
  }
}
```
4. **Copy Constructor**
   We use this constructor to create an object by copying data from another object.
   ```cs
   using System;

namespace Constructor {

  class Car {  
    string brand;

    // constructor
    Car (string theBrand) {
      brand = theBrand;
    }

    // copy constructor
    Car(Car c1) {
      brand = c1.brand;
    }

    static void Main(string[] args) {
      // call constructor
      Car car1 = new Car("Bugatti");

      Console.WriteLine("Brand of car1: " + car1.brand);

      // call the copy constructor
      Car car2 = new Car(car1);
      Console.WriteLine("Brand of car2: " + car2.brand);

      Console.ReadLine();
     
    }
  }
}
```
5. **Private Constructor**
   Once a constructor is declared private, we cannot create objects of the class in other classes.
   ```cs
   using System;

namespace Constructor {

  class Car {  
  
   // private constructor
   private Car () {
    Console.WriteLine("Private Constructor");    
    }
  }
    
    class CarDrive {

      static void Main(string[] args) {

      // call private constructor
      Car car1 = new Car(); // In this example we get an error
      Console.ReadLine();
    }
  }
}
```
6. **Static Constructor**
   We cannot call a static constructor directly. However, when we call a regular constructor, the static constructor gets called automatically. The **static constructor** is called only once during the execution of the program. That's why when we call the constructor again, only the regular constructor is called. The purpose of this constructor s to initialize static data, or perform a particular action that needs to be performed only once.
```cs
using System;

namespace Constructor {

  class Car {  
  
   // static constructor
   static Car () {
    Console.WriteLine("Static Constructor");    
   }

    // parameterless constructor
    Car() {
     Console.WriteLine("Default Constructor");
   } 

    static void Main(string[] args) {

      // call parameterless constructor
      Car car1 = new Car();

      // call parameterless constructor again
      Car car2 = new Car();

      Console.ReadLine();
    }
  }
}
```
**OUTPUT**
```cs
Static Constructor
Default Constructor
Default Constructor
```
>**NOTE**: WE can have only one static constructor in a class. It cannot have any parameters or access modifiers.

### Constructor Overloading
Creating two or more constructor in a class is known as **constructor overloading**. For this there must be two or more constructors with same name but different
- number of parameters
- types of parameters
- order of parameters

## this Keyword
`this` keyword refers to the current instance of a class.

### Invoke Constructor of the Same Class Using this
While working with constructor overloading, we might have to invoke one constructor from another constructor. In this case, we can use `this` keyword. Example:
```cs
using System;
 
namespace ThisKeyword {
  class Test {
    
    Test(int num1, int num2) {

      Console.WriteLine("Constructor with two parameter");
    }
    
    // invokes the constructor with 2 parameters
    Test(int num) : this(33, 22) {

      Console.WriteLine("Constructor with one parameter");
    }

    public static void Main(String[] args) {

      Test t1 = new Test(11); 
      Console.ReadLine();   
    }
  }
}
```
> Calling one constructor from another constructor is known as **constructor chaining**

## static keyword
Using this keyword with class members will result in having a single copy of the type member and all objects of the class share a single copy instead of creating individual copies.

If a variables is declared `static`, we can access the variable using the class name.
```c#
using System;

namespace StaticKeyword {

  class Student {

    // static variable
    public static string department = "Computer Science";
  }

  class Program {
    static void Main(string[] argos) {
    
      // access static variable
      Console.WriteLine("Department: " + Student.department);
     
      Console.ReadLine();
    }
  }
}
```

### static variables vs instance variables
Every object of a class will have its own copy of instance variables.
```cs
class Student {
	public string studentName;
	public static string university = "Eastern Visayas State University";
}

class Program {
	static void Main(string[] args){
		Student s1 = new Student();
		Student s2 = new Student();

		s1.studentName = "Shawn";
		s2.studentName = "Jade";

		Console.WriteLine($"Student 1: {s1.studentName}");
		Console.writeLine($"Student 2: {s2.studentName}");

		// No matter the object, all of them have the same value for the university variable

		Console.WriteLine(Student.university);
		
	}
}
```
Here, both the objects s1 and s2 will have different copies of the variable `studentName` but since the `university` variable is static then all the object will share the same copy.


### static methods
Just like static variables, we can call the static methods using the class name.
```cs
class Test 
{
	public static void display(){
		// statements
	}
}

class Program
{
	static void Main(string[] args){
		Test.display();
	}
}
```

>**NOTE:** In C#, the `Main` methods is static. So, we can call it without creating the object



### static class
When we create a static class, we cannot create objects of the class.
```cs
using System;

namespace StaticKeyword {

  static class Test {
    static int a = 5;
    static void display() {

      Console.WriteLine("Static method");
    }
  
    static void Main(string[] args) {

      // creating object of Test
      // this will return an error
      Test t1 = new Test();
      Console.WriteLine(a);
      display();
    }
  }
}
```
Notice the field and method of the static class are also static because we can only have static members inside the static class.

If we are accessing the static variables and methods inside the same class, we can directly access them without using the class name.
```cs
using System;
 
namespace StaticKeyword {
 
  class Test {
 
    static int age = 25;
    public static void display() {
 
      Console.WriteLine("Static method");
    }
   
    static void Main(string[] args) {
 
      Console.WriteLine(age);
      display();
      Console.ReadLine();
    }
  }
}
```