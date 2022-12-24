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
   If we have not defined a constructor in a class, then C# will automatically create a default constructor with an empty code and no parameters.
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