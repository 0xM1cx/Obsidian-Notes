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