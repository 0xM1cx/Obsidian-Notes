## Basic Structure of a C# Program
```cs
using system;

namespace HelloWorld
{
	class Hello{
		static void Main(string[] args){
			Console.WriteLine("Hello, World!");
		}
	}
}
```

### How it works
1. The *namespace* keyword is used to define our own namespace. Namespaces are used in  C# to organize and provide a level of separation of codes. They can be considered as a container which consists of other namespaces, classes, etc.  
```cs
namespace HelloWorld
```
- Possible members of a namespace
	- Namespaces(Nested Namespaces)
	- Classes
	- Interfaces
	- Structures
	- Delegates
>**Namespaces are not mandatory in a C# program.** But play a important role in writing cleaner code and managing larger projects.

Namespaces also help with **naming conflict**. Two or more classes when put into different namespaces can have the same name.

To access the members of a namespace use the dot(.) operator. Syntax:
```cs
// Namespace-Name.Member-Name
// Creating an object of Hello Class
HelloWorld.Hello hello = new MyNamespace.Hello();
```

2. `Main()` is a method of class Hello. The execution of every C# program starts from the `Main()` method. So it is mandatory for a C# program to have a `Main()` method.
```cs
static void Main(string[] args)
{

}
```

## Arrays
### Multidimensional Array
In a **multidimensional Array** each element of the array is also an array.
```cs
int[,] x = { {1, 2, 3}, {3, 4, 5} };
```

### Jagged Array
A **Jagged Array** consists of multiple arrays as its element. However, unlike multidimensional arrays, each array inside a jagged array can be of different sizes. 