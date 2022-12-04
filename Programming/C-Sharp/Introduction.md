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
## I/O
### Output
In order to output something in C#, use the 
```cs
System.Console.WriteLine(); // OR
System.Console.Write();
```
The difference between them is that in `System.Console.WriteLine()` is goes to the next line. In contrast to `System.Console.Write()` it prints without going to the next line.

The `System` is a namespace, `Console` is a class within the `System` namespace and `WriteLine()` or `Write()` are methods of the class `Console`. 

You can use the `using` keyword to call the `system` namespace. So that you only need to use `Console.Write()` or `Console.WriteLine()` without the `System` prefix.

### Input
The simplest way for getting user input is by using the `ReadLine()` method of the `Console` class. Nonetheless, `Read()` and `ReadKey()` are also available for getting input for the user.

The Difference between `ReadLine()`, `Read()`, and `ReadKey()` is:

- `ReadLine()` method reads the next line of input from the standard input stream. It returns the same string.
- `Read()` methods reads the next character from the standard input stream. It returns the ascii value of the character.
- `ReadKey()` method obtains the next key pressed by user. This method is usually used to hold the screen until user press a key.
## Arrays
**Array** is a collection of similar types of data.

Declaring and allocating memory to an array
```cs
int[] scores = new int[10];
```

Initializing an array
```cs
float[] scores = {1.4, 2.1, 4.3, 1.1, 1.0};
```
### Multidimensional Array
In a **multidimensional Array** each element of the array is also an array.
```cs
int[,] x = { {1, 2, 3}, {3, 4, 5} };
```

#### Two dimentional array
Syntax:
```cs
// datatype[,] identifier = { {1, 2, 3}, {4, 5, 6} };
int[,] arr = { {1, 2, 3}, {4, 5, 6} };
```
In the example above the the array is composed of elements which are also arrays. The array `{1, 2, 3}` and `{4, 5, 6}` are the rows which each element in that array being the columns.
- Accessing Elements from 2D Array
```cs
// identifier[row, column];
arr[1, 0]; // returns 4
```

#### Jagged Array
A **Jagged Array** consists of multiple arrays as its element. However, unlike multidimensional arrays, each array inside a jagged array can be of different sizes. 
```cs
// dataType[][] identifier = new dataType[rows][];
int[][] arr = new int[2][];
```

## Collections
**Collections**, unlike arrays, provide a more flexible way to work with group of objects. The group of objects you work with can grow and shrink dynamically as the needs of the application change. For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.

A **Collection** is a class, so you must declare an instance of the class before you can add elements to that collection.