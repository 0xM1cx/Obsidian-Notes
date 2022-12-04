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
      Dog bullDog = new Dog();

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