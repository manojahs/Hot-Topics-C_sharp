# Hot-Topics

1)Lazy Loading
------------------
Lazy Loading is a design pattern used to delay the initialization of an object or resource until it is actually needed. This helps improve performance, especially when working with resource-intensive operations or data that may not be required immediately.

Lazy<T> lazyObject = new Lazy<T>(() => new T()); // T is the type of object

Advantages of Lazy Loading:
--------------------------
Improved Performance: Resources are only created when needed, saving time and memory.
Efficiency: Reduces startup time and memory usage when some resources are not required during the program's execution.
Thread-Safety: The Lazy<T> class ensures safe and proper handling of concurrency when multiple threads access the lazy-loaded resource.


Polymorphism 
--------------------

Method overloading basically happens in compile time where it happens in same class where multiple methods having same method name with different parameter and it will get called based on the type of arguments that we pass

method overriding basically happens in atleast 2 different class where method name is both the class will be same and child class will be inheriting from base class and main thing is this is a technique where derived class method will get invoked through base class reference variable during run time 

<img width="661" alt="image" src="https://github.com/user-attachments/assets/69a14f56-d45f-4472-9aa3-55e981229c87" />
<img width="644" alt="image" src="https://github.com/user-attachments/assets/6565a3f1-dc2b-42d7-a12a-c1c4e223b873" />

Sealed class basically used to prevent the inheritance and struct are by default sealed so the struct and class cannot inhertic struct 

<img width="671" alt="image" src="https://github.com/user-attachments/assets/2cdb0017-12bb-49bf-8251-b157c089452f" />

<img width="686" alt="image" src="https://github.com/user-attachments/assets/a5dd67b6-c5b5-46bd-9060-3b3c46359a07" />

<img width="685" alt="image" src="https://github.com/user-attachments/assets/f9d6d4c1-e7f9-4107-90a0-b1ffa99801c5" />

<img width="675" alt="image" src="https://github.com/user-attachments/assets/b64c465d-fb08-4695-89ab-e5a82e87b4c8" />

<img width="655" alt="image" src="https://github.com/user-attachments/assets/289fc64f-d8e6-4b20-8819-da5645ffb8c6" />



Static Class
------------
A static class is a class that cannot be instantiated and is meant to contain only static members (methods, properties, fields, etc.).
Declared using the static keyword.
All members inside must also be static.
Cannot be instantiated with new.
Often used for utility/helper classes (like Math, File,Logging, etc.).
U can create a constructor only using static keyword and it cannot have parameter.
Static class by default its sealed class so that u can't inherit or u can't create a object of it

Static Value
-------------
A static value refers to a static field or property inside a class. It's a variable that belongs to the type itself, rather than to instances of the class.
Declared using the static keyword.
Shared across all instances of the class.
Only one copy exists in memory for the whole class.


Extension Method 
--------------------
1)It must be static.
2)It must be defined in a static class.
3)The first parameter of the method should specify the type it is extending, using the this keyword.

An extension method in C# allows you to "add" new methods to existing types without modifying their source code or creating a new derived type.

using System;

namespace ExtensionMethodDemo
{
    public static class IntExtensions
    {
        // This is the extension method
        public static bool IsEven(this int number)
        {
            return number % 2 == 0;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            int example = 42;
            // Using the extension method
            bool isEven = example.IsEven();
            Console.WriteLine(isEven);  // Output: True
        }
    }
}

Use of it
-----------
1. Callback Methods
2. Event Handling
3. Loose Coupling
4. Strategy Pattern
Delegates allow you to pass different strategies (methods) into a class or method to change behavior at runtime.

<img width="623" alt="image" src="https://github.com/user-attachments/assets/1e4b082c-d5f5-4e3b-b3ad-267f40ab31a8" />

<img width="674" alt="image" src="https://github.com/user-attachments/assets/44ec3d3e-5e6b-45e0-ad8d-6c4f5b4a78a7" />

<img width="679" alt="image" src="https://github.com/user-attachments/assets/0010205e-eebb-48ad-b5ac-17a68f56976e" />

<img width="695" alt="image" src="https://github.com/user-attachments/assets/31cdc03e-5911-4a76-bc7c-11dfcd9fe68d" />

<img width="656" alt="image" src="https://github.com/user-attachments/assets/fb6c281f-396c-47ae-904d-4911bdd6aac3" />

<img width="621" alt="image" src="https://github.com/user-attachments/assets/f2602760-3d3f-4091-a78d-8200eb141034" />

Indexers
--------
In C#, an indexer allows an object to be indexed like an array. Instead of accessing elements with methods like GetItem(), you can use the [] syntax directly on your class, making it more intuitive and clean.

public class SampleCollection<T>
{
    private T[] _items = new T[10];

    public T this[int index]
    {
        get => _items[index];
        set => _items[index] = value;
    }
}

Soap vs Rest API
----------------------

API is the application program interface which allows different software application to communicate each other.
It defines a set of rules and protocols for building and interacting with software.

SOAP- simple object access protocol (Message Protocol)
-----------------------
SOAP is a protocol, which means it has strict rules for messaging. It uses XML for all messages and supports complex operations and services.

REST - Representation State Transfer (Architectural Style)
----------------------
It’s an architectural style for designing networked applications. REST relies on standard HTTP methods to access resources.

| Feature            | **REST**                                   | **SOAP**                      |
| ------------------ | ------------------------------------------ | ----------------------------- |
| **Style**          | Architectural style                        | Protocol                      |
| **Message Format** | JSON, XML, HTML, plain text                | XML only                      |
| **Transport**      | HTTP (commonly)                            | HTTP, SMTP, TCP               |
| **Security**       | SSL/TLS, OAuth (customizable)              | Built-in WS-Security standard |
| **Speed**          | Fast, lightweight                          | Slower due to XML parsing     |
| **Flexibility**    | Highly flexible                            | Rigid (requires WSDL)         |
| **State**          | Stateless      
| Can be stateless or stateful  |
| **Error Handling** | HTTP status codes (200, 404, 500, etc.)    | SOAP faults (XML based)       |
| **Tooling**        | Easy to use with web tools (Postman, curl) | Needs SOAP clients or proxies |
Usage                  MObile ,Web, IOT                              Banking , Finance , Legacy system


What is Lock and whats the siginificance of it
----------------------------------------
In C#, the lock keyword is used to ensure thread safety when multiple threads access a shared resource at the same time. It's part of the synchronization mechanism in multithreaded applications.

Significance of lock in C#
---------------------------
✅ 1. Prevents Race Conditions
When two or more threads access and modify the same data concurrently, you can get unexpected results. lock ensures only one thread can access the code block at a time.

✅ 2. Protects Shared Resources
Common in situations involving:
--------------------------------
Shared variables
Collections (like lists or dictionaries)
Files or I/O operations

private static readonly object _lockObj = new object();
private static int counter = 0;

public void IncrementCounter()
{
    lock (_lockObj)
    {
        counter++;
    }
}

 Important Rules:
 ----------------------
Always lock on a private readonly object (object _lock = new object();)

❌ Never lock on this, typeof(SomeClass), or public objects — this can lead to deadlocks or unintended interference.
Keep the code inside the lock minimal — avoid long or slow operations.


Different type of constructor
----------------------------

In C#, a constructor is a special method that gets called automatically when an object is created. Constructors are used to initialize objects, and C# provides several types to support different scenarios.


| Type          | Purpose                         | Parameters?             | Called When                              |
| ------------- | ------------------------------- | ----------------------- | ---------------------------------------- |
| Default       | Initialize with default values  | No                      | Object created (if no other constructor) |
| Parameterized | Initialize with specific values | Yes                     | Manually with `new`                      |
| Copy          | Duplicate object values         | Yes (same class object) | Manually with `new`                      |
| Static        | Initialize static members       | No                      | Once, automatically                      |
| Private       | Restrict object creation        | No                      | Only inside the class                    |


What is the significance of this keyword
-----------------------------------------

The this keyword in C# has several important purposes — it's used to refer to the current instance of a class or struct.

1. Refer to Current Object's Members
   ---------------------------------
 private string name;

public Person(string name)
{
    this.name = name; // 'this' refers to the instance field
}

 2. Pass the Current Object as a Parameter
    ----------------------------------------

    public void Print()
{
    Logger.Log(this); // pass the current object
}

3. Invoke Other Constructors (Constructor Chaining)
   ------------------------------
   public Person() : this("Unknown", 0) {}

public Person(string name, int age)
{
    this.name = name;
    this.age = age;
}


| Feature        | `Parallel.For`                     | `Parallel.ForEach`                    |
| -------------- | ---------------------------------- | ------------------------------------- |
| Input          | Numeric range (`int from, int to`) | Collection (`IEnumerable<T>`)         |
| Iteration type | Index-based (`i`)                  | Element-based (`item`)                |
| Use case       | Known start/end values             | Iterating over arrays, lists, etc.    |
| Example        | `Parallel.For(0, 100, i => ...)`   | `Parallel.ForEach(list, item => ...)` |


| Feature           | Thread                                        | Task                                           |
| ----------------- | --------------------------------------------- | ---------------------------------------------- |
| **Level**         | Low-level (OS-managed)                        | High-level (TPL abstraction)                   |
| **Creation Cost** | Expensive                                     | Lightweight (uses ThreadPool)                  |
| **API Support**   | `System.Threading.Thread`                     | `System.Threading.Tasks.Task`                  |
| **Async Support** | Not directly                                  | Built-in (`async/await`)                       |
| **Use Case**      | Long-running background work                  | Parallel work, async operations, continuations |
| **Management**    | You must handle lifecycle (start, join, etc.) | Automatic scheduling, cancellation, exceptions |

 | Aspect                 | Normal Casting                                                | Generic Casting                                                                                            |
| ---------------------- | ------------------------------------------------------------- | -----------------------------------------------------------------
| **Compile-time info**  | Compiler knows the exact type                                 | Compiler doesn’t know `T` (unless constrained)                                                            
| **IL instruction**     | `castclass`, `box`, `unbox.any` depending on type             | Same instructions, but emitted for `T` at JIT time                                                        
| **Performance**        | Reference cast = cheap, Value cast = boxing/unboxing overhead | Same, but generic keeps it type-safe at runtime                                                           
| **Constraints effect** | Not applicable                                                | Constraints let compiler optimize IL (e.g., `where T : struct` → emits `unbox.any` instead of `castclass`)
| **Risk**               | Wrong cast → runtime `InvalidCastException`                   | Same risk, since runtime check still happens                                                               

```

