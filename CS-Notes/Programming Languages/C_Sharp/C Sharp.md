#### Data Structure Questions

##### Difference between a Stack vs Heap? 
- These are memory types in an application
- Stack memory stores data types such as int, double, float, Boolean
- Heap memory stores data types such as strings and objects

- Data stored on a stack must have a fixed size
- Data with an unknown size that might change should be stored on a heap

##### What is Casting? Implicit and Explicit 
- Casting is where you convert one type of data to another type
- Implicit casting is when you move from a lower to higher data type
Ex. 
```csharp
int a = 5;

double b = a; // casting (implicit casting)
```

- Explicit casting is when you move from a higher to lower data type
Ex. 
```csharp
double a = 10;

int b = (int)a; // casting (explicit casting)
```

##### Difference between Array and ArrayList?
- Array is fixed in size so the size cannot be changed. So if you need more/less space you would have to create a new array and manually copy the elements over. 
- ArrayList is dynamic in size, so it can grow or shrink as you can add/remove elements. 

##### Difference between Abstract class and Interface?
- Abstract class is a half defined parent class while the interface is a contract. Abstract classes are inherited while interfaces are implemented. 
- Interfaces force a structure into a class. 

##### How can you handle exceptions in C Sharp?
- Use try catch blocks to handle exceptions
Ex. 
```csharp
try {
	int y = 0;
	int z = 1 / y; // Divide by 0
} catch(Exception ex) {
	Console.WriteLine("Divide by zero error!");
}
```

#### Object Oriented Principles

What is a class?
- It is a blueprint for an object that contains variables for storing data and functions for performing methods on the data. 

```csharp
class Car 
{
  string color = "red";

  static void Main(string[] args)
  {
    Car myObj = new Car();
    Console.WriteLine(myObj.color);
  }
}
// Output
Red
```

What is an object?
- An object is an instance of a class. Data methods can't be used directly so you create an object (or instance) of the class to use them. In simple terms, they are the actual world entities that have a state and behavior.

```cs
using System;

// defining class
public class Student {
    public string name;
}

public class GFG {
    static public void Main()
    {
        // creating object
        Student student1 = new Student();

        student1.name = "Rahul";
        Console.WriteLine("student1.name: " + student1.name);
    }
}
```

What is an interface?
- It is a completely "abstract class", which only contains abstract methods and properties

```csharp
using System;

namespace MyApplication
{
  // Interface
  interface IAnimal 
  {
    void animalSound(); // interface method (does not have a body)
  }

  // Pig "implements" the IAnimal interface
  class Pig : IAnimal 
  {
    public void animalSound() 
    {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program 
  {
    static void Main(string[] args) 
    {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
    }
  }
}
//Output 
The pig says: wee wee
```

What is a constructor? 
- It is a special method that is used to initialize objects. 
- The advantage of a constructor, is that it is called when an object of a class is created. It can be used to set initial values for fields

```csharp
// Create a Car class
class Car
{
  public string model;  // Create a field

  // Create a class constructor for the Car class
  public Car()
  {
    model = "Mustang"; // Set the initial value for model
  }

  static void Main(string[] args)
  {
    Car Ford = new Car();  // Create an object of the Car Class (this will call the constructor)
    Console.WriteLine(Ford.model);  // Print the value of model
  }
}

// Outputs "Mustang"
```
#### Four fundamental Principles in C Sharp

##### Encapsulation
- The binding of data and methods that manipulate them into a single unit so sensitive data is hidden from users
- Uses **Data Hiding** to restrict access to members in an object. Example, using private or protected members. 
Ex.
```cs
// C# program to illustrate encapsulation
using System;
 
public class DemoEncap {
 
    // private variables declared
    // these can only be accessed by
    // public methods of class
    private String studentName;
    private int studentAge;
 
    // using accessors to get and
    // set the value of studentName
    public String Name
    {
 
        get { return studentName; }
 
        set { studentName = value; }
    }
 
    // using accessors to get and
    // set the value of studentAge
    public int Age
    {
 
        get { return studentAge; }
 
        set { studentAge = value; }
    }
}

// Driver Class
class GFG {
 
    // Main Method
    static public void Main()
    {
 
        // creating object
        DemoEncap obj = new DemoEncap();
 
        // calls set accessor of the property Name,
        // and pass "Ankita" as value of the
        // standard field 'value'
        obj.Name = "
        Ankita& quot;
        ;
 
        // calls set accessor of the property Age,
        // and pass "21" as value of the
        // standard field 'value'
        obj.Age = 21;
 
        // Displaying values of the variables
        Console.WriteLine(" Name : " + obj.Name);
        Console.WriteLine(" Age : " + obj.Age);
    }
}
```

##### Inheritance
- When a class is derived from another class and uses data and implementation of that other class. 
- The class which is derived is called a child or subclass and the class from which the child/subclass is derived from is called the parent or superclass

```csharp
class Vehicle  // base class (parent) 
{
  public string brand = "Ford";  // Vehicle field
  public void honk()             // Vehicle method 
  {                    
    Console.WriteLine("Tuut, tuut!");
  }
}

class Car : Vehicle  // derived class (child)
{
  public string modelName = "Mustang";  // Car field
}

class Program
{
  static void Main(string[] args)
  {
    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (From the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
    Console.WriteLine(myCar.brand + " " + myCar.modelName);
  }
}

Tuut, tuut!  
Ford Mustang
```

##### Abstraction 
- Only the required information is visible to the user and the rest of the information is hidden. 

```cs
// C# program to calculate the area 
// of a square using the concept of
// data abstraction
using System;

namespace Demoabstraction {
	
// abstract class
abstract class Shape {

	// abstract method
	public abstract int area();
}

// square class inheriting
// the Shape class
class Square : Shape {

	// private data member
	private int side;

	// method of square class
	public Square(int x = 0)
	{
		side = x;
	}
	
	// overriding of the abstract method of Shape
	// class using the override keyword
	public override int area()
	{
		Console.Write("Area of Square: ");
		return (side * side);
	}
}

// Driver Class
class GFG {
	
	// Main Method
	static void Main(string[] args)
	{
		
		// creating reference of Shape class
		// which refer to Square class instance
		Shape sh = new Square(4);
		
		// calling the method
		double result = sh.area();
		
		Console.Write("{0}", result);

	}
}
}
```

##### Polymorphism
- When there are multiple classes that are related to each other by inheritance. 
- Inheritance lets us inherit fields and methods from another class. **Polymorphism** uses those methods to perform different tasks


```csharp
class Animal  // Base class (parent) 
{
  public void animalSound() 
  {
    Console.WriteLine("The animal makes a sound");
  }
}

class Pig : Animal  // Derived class (child) 
{
  public void animalSound() 
  {
    Console.WriteLine("The pig says: wee wee");
  }
}

class Dog : Animal  // Derived class (child) 
{
  public void animalSound() 
  {
    Console.WriteLine("The dog says: bow wow");
  }
}

class Program 
{
  static void Main(string[] args) 
  {
    Animal myAnimal = new Animal();  // Create a Animal object
    Animal myPig = new Pig();  // Create a Pig object
    Animal myDog = new Dog();  // Create a Dog object

    myAnimal.animalSound();
    myPig.animalSound();
    myDog.animalSound();
  }
}

// Output
The animal makes a sound  
The animal makes a sound  
The animal makes a sound
```


