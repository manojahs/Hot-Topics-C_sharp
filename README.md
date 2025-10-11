# Hot-Topics

| Feature                     | **.NET Framework** 🧱                                               | **.NET Core / .NET (5+)** 🚀                                                          |
| --------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Platform Support**        | 🪟 **Windows only**                                                 | 🌍 **Cross-platform** (Windows, Linux, macOS)                                         |
| **Deployment**              | Installed as part of Windows OS (shared)                            | Can be **self-contained** (no need for system-wide installation)                      |
| **Open Source**             | Mostly closed source (some parts open)                              | Fully **open source** on GitHub                                                       |
| **Performance**             | Good, but limited optimization                                      | **Much faster** — built for high performance & scalability                            |
| **Application Types**       | Supports classic ASP.NET, WCF, Windows Forms, WPF, Windows Services | Supports **ASP.NET Core**, Blazor, Console, Worker services, MAUI (UI cross-platform) |
| **Updates & Future**        | ❌ No major new features (only security fixes)                       | ✅ Actively developed and improved (new versions every year)                           |
| **Hosting**                 | IIS only                                                            | IIS, Kestrel, Nginx, Apache, Docker, Cloud                                            |
| **Dependency Injection**    | Needs external libraries like Unity or Autofac                      | Built-in DI container 💪                                                              |
| **Command Line Tools**      | Limited                                                             | Powerful CLI (`dotnet CLI`) — great for DevOps & CI/CD                                |
| **Side-by-side Versioning** | Not supported easily (one version per machine)                      | ✅ Supported — multiple app versions can run on same machine                           |
| **Use Case**                | Legacy apps, Windows-only environments                              | Modern apps, Microservices, Cloud, Containers, Cross-platform apps                    |


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


```
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
```
Delegates allow you to pass different strategies (methods) into a class or method to change behavior at runtime.

<img width="623" alt="image" src="https://github.com/user-attachments/assets/1e4b082c-d5f5-4e3b-b3ad-267f40ab31a8" />

<img width="674" alt="image" src="https://github.com/user-attachments/assets/44ec3d3e-5e6b-45e0-ad8d-6c4f5b4a78a7" />

<img width="679" alt="image" src="https://github.com/user-attachments/assets/0010205e-eebb-48ad-b5ac-17a68f56976e" />

<img width="695" alt="image" src="https://github.com/user-attachments/assets/31cdc03e-5911-4a76-bc7c-11dfcd9fe68d" />

<img width="656" alt="image" src="https://github.com/user-attachments/assets/fb6c281f-396c-47ae-904d-4911bdd6aac3" />

<img width="621" alt="image" src="https://github.com/user-attachments/assets/f2602760-3d3f-4091-a78d-8200eb141034" />

```
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

| Feature           | Thread                                        | Task                                           |
| ----------------- | --------------------------------------------- | ---------------------------------------------- |
| **Level**         | Low-level (OS-managed)                        | High-level (TPL abstraction)                   |
| **Creation Cost** | Expensive                                     | Lightweight (uses ThreadPool)                  |
| **API Support**   | `System.Threading.Thread`                     | `System.Threading.Tasks.Task`                  |
| **Async Support** | Not directly                                  | Built-in (`async/await`)                       |
| **Use Case**      | Long-running background work                  | Parallel work, async operations, continuations |
| **Management**    | You must handle lifecycle (start, join, etc.) | Automatic scheduling, cancellation, exceptions |


| Feature        | `Parallel.For`                     | `Parallel.ForEach`                    |
| -------------- | ---------------------------------- | ------------------------------------- |
| Input          | Numeric range (`int from, int to`) | Collection (`IEnumerable<T>`)         |
| Iteration type | Index-based (`i`)                  | Element-based (`item`)                |
| Use case       | Known start/end values             | Iterating over arrays, lists, etc.    |
| Example        | `Parallel.For(0, 100, i => ...)`   | `Parallel.ForEach(list, item => ...)` |



 | Aspect                 | Normal Casting                                                | Generic Casting                                                                                            |
| ---------------------- | ------------------------------------------------------------- | -----------------------------------------------------------------
| **Compile-time info**  | Compiler knows the exact type                                 | Compiler doesn’t know `T` (unless constrained)                                                            
| **IL instruction**     | `castclass`, `box`, `unbox.any` depending on type             | Same instructions, but emitted for `T` at JIT time                                                        
| **Performance**        | Reference cast = cheap, Value cast = boxing/unboxing overhead | Same, but generic keeps it type-safe at runtime                                                           
| **Constraints effect** | Not applicable                                                | Constraints let compiler optimize IL (e.g., `where T : struct` → emits `unbox.any` instead of `castclass`)
| **Risk**               | Wrong cast → runtime `InvalidCastException`                   | Same risk, since runtime check still happens

| Feature         | **Synchronous**                           | **Asynchronous**                         |
| --------------- | ----------------------------------------- | ---------------------------------------- |
| **Execution**   | One after another (blocking)              | Can run independently (non-blocking)     |
| **Waiting**     | Caller must wait                          | Caller can continue doing other work     |
| **Return Type** | Normal return value (`void`, `int`, etc.) | `Task`, `Task<T>`, or `ValueTask`        |
| **Use Case**    | CPU-bound, quick operations               | I/O-bound, long-running operations       |
| **Performance** | Can cause UI freezing, slow response      | More responsive apps, better scalability |


Generic Type casting
-------------------------

Here we are using param as Object bcz we dont knw what is the data thats the reason. if you provide like int input then it works only for int if u provide string it works only for string if u provide like Object it works for any datatype 


class Example<T>
{
    public void CastTest(object input)
    {
        // Explicit cast
        T value = (T)input;
        Console.WriteLine(value);
    }
}

class Program
{
    static void Main()
    {
        Example<int> e1 = new Example<int>();
        e1.CastTest(42);   // works

        Example<string> e2 = new Example<string>();
        e2.CastTest("hello"); // works

        // e2.CastTest(42); // ❌ runtime InvalidCastException
    }
}

Normal Type casting
-------------------
Reference Type
----------------
object obj = "hello";
string s = (string)obj;   // explicit cast

Compiler inserts an IL (Intermediate Language) instruction like castclass.
At runtime, the CLR (Common Language Runtime) checks if the actual object (obj) is of type string.
✅ If yes → succeeds, no copy is made.

Value Type:
------------
object obj = 42;     // boxing
int x = (int)obj;    // unboxing

Boxing = wraps value type (42) into a heap object.
Unboxing = extracts back to a value type (with runtime check).
This is more expensive than reference casting


Quick Summary
----------------------
ref: must be initialized before passing, used to read+modify.
out: must be assigned inside method, used to return multiple values.


2nd highest based on deptwise
------------------------

var employees = new[]
{
    new { Name = "Alice", Salary = 5000, Dept = "IT" },
    new { Name = "Bob", Salary = 7000, Dept = "IT" },
    new { Name = "Charlie", Salary = 6000, Dept = "HR" },
    new { Name = "David", Salary = 9000, Dept = "HR" },
    new { Name = "Eve", Salary = 7000, Dept = "IT" },
    new { Name = "Frank", Salary = 4000, Dept = "HR" }
};


var result = employees.GroupBy(e => e.Dept).Select(g => new
{
    Dept = g.Key,
    SecondHighestSalary = g.OrderByDescending(e => e.Salary).Select(e => e.Salary).Distinct().Skip(1).FirstOrDefault()
});

foreach (var item in result)
{
    Console.WriteLine($"{item.Dept}: {item.SecondHighestSalary}");
}

output
IT: 5000
HR: 6000

Find the 2nd highest salary
----------------------------
var employees = new[]
{
    new { Name = "Alice", Salary = 5000},
    new { Name = "David", Salary = 9000 },
    new { Name = "Frank", Salary = 4000}
};


var res = employees.OrderByDescending(e => e.Salary).Select(e => e.Salary).Distinct().Skip(1).FirstOrDefault();
Console.WriteLine(res);

Delegate and Event
------------------------
Delegate
-----------
A delegate is a type-safe function pointer in C#.
It allows methods to be passed as parameters.
Supports callback methods and multicasting (multiple methods invoked).

using System;

public delegate void Notify(string message);  // delegate definition

class Program
{
    static void SendEmail(string msg) => Console.WriteLine("Email: " + msg);
    static void SendSMS(string msg) => Console.WriteLine("SMS: " + msg);

    static void Main()
    {
        Notify notifyHandler = SendEmail;   // assign method
        notifyHandler += SendSMS;           // multicast

        notifyHandler("Order placed");  
        // Output:
        // Email: Order placed
        // SMS: Order placed
    }
}

Types of Delegate
---------------------
1. Single-cast Delegate
---------------------

Refers to a single method.
Invoking the delegate calls exactly one method.

public delegate void MyDelegate(string message);
MyDelegate del = Method1;
del("Hello"); 

2. Multicast Delegate
------------------

Can reference multiple methods.
Invoking the delegate calls all the methods it references, in order.
Created by using += to add methods.

MyDelegate del = Method1;
del += Method2;
del("Hello");  // Calls Method1 and then Method2

3. Generic Delegates
----------------------
Provided by .NET, no need to define your own.
Two main types:

Action<>: returns void and can take 0 or more parameters.
Func<>: returns a value and can take 0 or more parameters.

Action<string> actionDel = message => Console.WriteLine(message);
Func<int, int, int> funcDel = (x, y) => x + y;

4. Lambda Expressions
-----------------------
MyDelegate lambdaDel = msg => Console.WriteLine(msg);



Event
-------
An event is a wrapper around a delegate.
It provides a publisher-subscriber model (Observer Pattern).
Ensures only += and -= (subscribe/unsubscribe) are allowed externally — preventing direct invocation outside the declaring class.

using System;

public class Order
{

    public delegate void OrderPlacedHandler(string item);

    // declare event using delegate
    public event OrderPlacedHandler OrderPlaced;

    public void PlaceOrder(string item)
    {
        Console.WriteLine($"Placing order for {item}");
        OrderPlaced?.Invoke(item); // raise event
    }
}

class Program
{
    static void OnEmail(string item) => Console.WriteLine($"Email sent for {item}");
    static void OnSMS(string item) => Console.WriteLine($"SMS sent for {item}");

    static void Main()
    {
        var order = new Order();

        // subscribe to event
        order.OrderPlaced += OnEmail;
        order.OrderPlaced += OnSMS;

        order.PlaceOrder("Laptop");
        // Output:
        // Placing order for Laptop
        // Email sent for Laptop
        // SMS sent for Laptop
    }
}
OrderPlaced event can be triggered only inside Order class.
Subscribers (OnEmail, OnSMS) react to the event.

| Feature          | Delegate                          | Event                                        |
| ---------------- | --------------------------------- | -------------------------------------------- |
| What is it?      | Type-safe function pointer        | Wrapper around delegate (pub-sub model)      |
| Who can invoke?  | Any code with delegate reference  | Only the declaring class can invoke          |
| Access modifiers | Methods can directly assign (`=`) | Only `+=` and `-=` allowed for safety        |
| Use Case         | Callback mechanism                | Notification system (publisher → subscriber) |

Shallow copy and Deep copy
----------------------------
Creates a new object but copies only the immediate fields.
If the field is a reference type, it just copies the reference (pointer), not the actual object.
Both objects point to the same referenced instance.

using System;

class Address
{
    public string City { get; set; }
}

class Person
{
    public string Name { get; set; }
    public Address Addr { get; set; }
}

class Program
{
    static void Main()
    {
        Person p1 = new Person
        {
            Name = "Alice",
            Addr = new Address { City = "New York" }
        };

        // Shallow copy using MemberwiseClone()
        Person p2 = (Person)p1.MemberwiseClone();

        p2.Name = "Bob";
        p2.Addr.City = "Los Angeles";  // shared reference!

        Console.WriteLine($"{p1.Name}, {p1.Addr.City}"); // Alice, Los Angeles
        Console.WriteLine($"{p2.Name}, {p2.Addr.City}"); // Bob, Los Angeles
    }
}


Deepcopy
------------
Creates a completely independent copy of the object and all nested objects.
Reference types are also cloned recursively, not just referenced.
Both objects are fully independent.

class Address
{
    public string City { get; set; }
}

class Person
{
    public string Name { get; set; }
    public Address Addr { get; set; }

    // Deep copy implementation
    public Person DeepCopy()
    {
        return new Person
        {
            Name = this.Name,                   // value copied
            Addr = new Address { City = this.Addr.City } // new object, not shared
        };
    }
}
Person p1 = new Person { Name = "Alice", Addr = new Address { City = "New York" } };
Person p2 = p1.DeepCopy();

p2.Name = "Bob";
p2.Addr.City = "Los Angeles";

Console.WriteLine($"{p1.Name}, {p1.Addr.City}"); // Alice, New York
Console.WriteLine($"{p2.Name}, {p2.Addr.City}"); // Bob, Los Angeles

*) When u ll use Abstraction and INterface give me the real time example

1️⃣ Abstraction (Abstract Class)

✅ Purpose
When you want to provide some default implementation along with method declarations.
When classes share common behavior and state (fields/properties).

✅ Real-Time Scenario: Payment Gateway
Imagine an e-commerce system with multiple payment methods:

-> Class can inherit only one abstract class 

public abstract class PaymentProcessor
{
    public string TransactionId { get; set; }

    // Abstract method - must be implemented by derived class
    public abstract void ProcessPayment(decimal amount);

    // Concrete method - shared implementation
    public void LogTransaction()
    {
        Console.WriteLine($"Transaction {TransactionId} logged at {DateTime.Now}");
    }
}


public class PayPalProcessor : PaymentProcessor
{
    public override void ProcessPayment(decimal amount)
    {
        Console.WriteLine($"Processing PayPal payment of {amount}");
        LogTransaction();
    }
}

public class StripeProcessor : PaymentProcessor
{
    public override void ProcessPayment(decimal amount)
    {
        Console.WriteLine($"Processing Stripe payment of {amount}");
        LogTransaction();
    }
}

Common fields and methods (TransactionId, LogTransaction) can be shared.
Each processor can implement its specific behavior.


Interface
------------

When you want to define a contract that multiple unrelated classes can implement.
No implementation allowed (only method/property signatures).
A class can implement multiple interfaces.

public interface ILogger
{
    void LogInfo(string message);
    void LogError(string message);
}

public class FileLogger : ILogger
{
    public void LogInfo(string message) => File.AppendAllText("log.txt", message + "\n");
    public void LogError(string message) => File.AppendAllText("error.txt", message + "\n");
}

public class DatabaseLogger : ILogger
{
    public void LogInfo(string message) => Console.WriteLine($"DB Log Info: {message}");
    public void LogError(string message) => Console.WriteLine($"DB Log Error: {message}");
}

-> Class can inherit Multiple interface

Reflection
----------------
In C#, getting metadata values at runtime is done using Reflection.

Reflection allows you to inspect assemblies, types, and members at runtime.

You can get metadata like:
Class names
Method names and parameters
Properties and fields
Attributes applied to classes, methods, or properties
You can even invoke methods or create objects dynamically using reflectio

using System;
using System.Reflection;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public void SayHello()
    {
        Console.WriteLine($"Hello, my name is {Name}");
    }
}

class Program
{
    static void Main()
    {
        Type type = typeof(Person);

        // Get class name
        Console.WriteLine("Class: " + type.Name);

        // Get properties
        PropertyInfo[] properties = type.GetProperties();
        foreach (var prop in properties)
        {
            Console.WriteLine("Property: " + prop.Name + ", Type: " + prop.PropertyType);
        }

        // Get methods
        MethodInfo[] methods = type.GetMethods();
        foreach (var method in methods)
        {
            Console.WriteLine("Method: " + method.Name);
        }
    }
}






```

