Java Interview Questions for Freshers
-------------------------------------

### > List the features of the Java Programming language?

Java is a widely used and versatile programming language known for its simplicity, platform independence, and extensive library support. Here are some of the key features of the Java programming language:

**1. Object-Oriented:** Java follows the object-oriented programming (OOP) paradigm, which allows developers to create modular and reusable code through the use of classes and objects.

**2. Platform Independence:** Java programs can run on any platform with a Java Virtual Machine (JVM), making it highly portable. The "write once, run anywhere" principle is achieved by compiling Java source code into bytecode, which can be executed on any system with a compatible JVM.

**3. Garbage Collection:** Java features automatic memory management through garbage collection. It frees developers from explicitly deallocating memory, as the JVM automatically identifies and reclaims unused objects.

**4. Strong Standard Library:** Java comes with a comprehensive standard library, known as the Java Class Library (JCL), which provides a wide range of pre-built classes and APIs for common tasks like input/output, networking, database connectivity, and more.

**5. Exception Handling:** Java provides a robust exception handling mechanism that allows developers to handle and recover from unexpected errors and exceptions during runtime, ensuring program stability.

**6. Multi-threading:** Java supports concurrent programming with built-in support for multi-threading. Developers can create and manage multiple threads of execution within a single program, enabling efficient utilization of system resources and concurrent processing.

**7. Security:** Java has built-in security features to create secure applications. It includes features like bytecode verification, sandbox security model, and cryptography libraries for encryption and secure communication.

**8. Portability:** Java's platform independence makes it highly portable across different operating systems and architectures, allowing developers to write code that can run on a wide range of devices, from desktop computers to mobile devices and embedded systems.

**9. Performance:** While Java is not the fastest language, it offers good performance due to its efficient Just-In-Time (JIT) compilation and optimized JVM implementations. Java's performance can be further improved through various optimization techniques.

**10. Community and Ecosystem:** Java has a vast and active developer community, which contributes to a rich ecosystem of libraries, frameworks, and tools. This community support provides developers with a wide range of resources and helps foster innovation and productivity.

These are just some of the prominent features of the Java programming language that have contributed to its popularity and widespread use in various domains, including web development, enterprise software, mobile app development, and more.

---
### > What are the differences between the Java Runtime Environment (JRE) and the Java Development Kit (JDK)?

JRE (Java Runtime Environment) and JDK (Java Development Kit) are essential components in the Java ecosystem. Here's an explanation of each:

***1. JRE (Java Runtime Environment):***
JRE is the set of software tools and libraries required to run Java applications. It includes the Java Virtual Machine (JVM), which is responsible for executing Java bytecode, as well as core classes, libraries, and other necessary files.

When you want to run a Java application or applet on your computer, you need to have JRE installed. JRE provides the runtime environment necessary for executing Java programs without the need for any development tools. It ensures that Java applications can run on any platform that supports JRE, regardless of the underlying operating system or hardware.

JRE includes the JVM, libraries, and other components needed for running Java applications but does not contain tools for compiling or developing Java programs.

***2. JDK (Java Development Kit):***
JDK is a software development kit that provides tools and libraries for developing Java applications. It includes everything in JRE and additional components specifically designed for developers.

The main components of JDK are:

- Java Compiler (javac): It is the Java source code compiler that converts human-readable Java source code into platform-independent Java bytecode.

- JVM (Java Virtual Machine): The JVM in JDK is used for executing and testing Java applications during the development process.

- Development Tools: JDK includes various tools that aid in Java application development, such as the Java debugger (jdb), Java documentation generator (javadoc), and other utilities for packaging, signing, and deploying Java applications.

- Libraries and APIs: JDK provides a rich set of libraries and APIs (Application Programming Interfaces) that developers can utilize to build robust and feature-rich Java applications. These libraries cover a wide range of functionalities, including networking, database access, GUI development, XML processing, and more.

In summary, JRE is required to run Java applications, while JDK is needed for Java application development. If you are a developer, you'll typically need to install JDK on your machine, which includes JRE as part of its package. JRE, on the other hand, is sufficient if you only want to run existing Java applications without writing any code.

---
### > What is a ClassLoader?

A classloader in Java is a subsystem of Java Virtual Machine, dedicated to loading class files when a program is executed; ClassLoader is the first to load the executable file.

In brief, a ClassLoader in Java is responsible for dynamically loading classes into memory during program execution. It locates and loads class files, performs linking to resolve references, initializes classes, and enforces Java's security model. 

---
### > What are the Memory Allocations available in JavaJava?

Java has five significant types of memory allocations.

*   Class Memory
*   Heap Memory
*   Stack Memory
*   Program Counter-Memory
*   Native Method Stack Memory

---
### > What are the differences between Heap and Stack Memory in Java?

Stack memory in data structures is the amount of memory allocated to each individual programme. It is a fixed memory space. 
Heap memory, in contrast, is the portion that was not assigned to the Java code but will be available for use by the Java code when it is required, which is generally during the program's runtime.
In summary, heap memory is used for dynamically allocated objects with a longer lifespan and supports multiple thread access, while stack memory is used for method execution and local variables with a shorter lifespan, providing faster memory access and thread safety.

---
### > Will the program run if we write static public void main?

Yes, the program will successfully execute if written so. Because, in Java, there is no specific rule for the order of specifiers

---
### > What is the default value stored in Local Variables?

Neither the Local Variables nor any primitives and Object references have any default value stored in them. 

---
### > Explain the expected output of the following code segment?
``` java
public class Test   
{  
    public static void main (String args\[\])   
    {  
        System.out.println(100 + 100 +“Test");   
        System.out.println(“E-Learning Company" + 100 + 100);  
    }  
}
```
The answers for the two print statements are as follows.

*   200Test
*   E-Learning Company100100

---
### > What is an Association?

An Association can be defined as a relationship that has no ownership over another. For example, a person can be associated with multiple banks, and a bank can be related to various people, but no one can own the other.
An association is a relationship between two or more classes that represents a connection or interaction between their objects. It is a fundamental concept in object-oriented programming and represents how classes are related to each other in terms of their behavior and data exchange.

```java
// Author class representing an author
class Author {
    private String name;
    
    public Author(String name) {
        this.name = name;
    }
    
    public String getName() {
        return name;
    }
}

// Book class representing a book
class Book {
    private String title;
    private Author author;
    
    public Book(String title, Author author) {
        this.title = title;
        this.author = author;
    }
    
    public String getTitle() {
        return title;
    }
    
    public Author getAuthor() {
        return author;
    }
}

// Main class to demonstrate the association
public class AssociationExample {
    public static void main(String[] args) {
        // Create an author
        Author author = new Author("John Smith");
        
        // Create two books associated with the author
        Book book1 = new Book("Book 1", author);
        Book book2 = new Book("Book 2", author);
        
        // Retrieve book information
        System.out.println("Book 1: " + book1.getTitle() + " by " + book1.getAuthor().getName());
        System.out.println("Book 2: " + book2.getTitle() + " by " + book2.getAuthor().getName());
    }
}

```
In the example above, we have an Author class representing an author with a name, and a Book class representing a book with a title and an associated author. The Book class has an instance variable of type Author, establishing a one-to-many association between the two classes.

---
### > What do you mean by aggregation?

The term aggregation refers to the relationship between two classes best described as a “whole/part” and “has-a” relationship. This kind is the most specialized version of an association relationship. It contains the reference to another class and is said to have ownership of that class.

---
### > Define Copy Constructor in Java

A Copy Constructor in Java is a constructor that initializes an object through another object of the same class.
```java
// Person class representing a person
class Person {
    private String name;
    private int age;
    
    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Copy constructor
    public Person(Person otherPerson) {
        this.name = otherPerson.name;
        this.age = otherPerson.age;
    }
    
    // Getters
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
}

// Main class to demonstrate the copy constructor
public class CopyConstructorExample {
    public static void main(String[] args) {
        // Create a person
        Person person1 = new Person("John Doe", 25);
        
        // Create a new person using the copy constructor
        Person person2 = new Person(person1);
        
        // Display information of both persons
        System.out.println("Person 1: " + person1.getName() + ", Age: " + person1.getAge());
        System.out.println("Person 2: " + person2.getName() + ", Age: " + person2.getAge());
    }
}
```

---
### > What is a Marker Interface?

An empty interface in Java is referred to as a Marker interface. Serializable and Cloneable are some famous examples of Marker Interface. 
```java
// Marker Interface
interface Printable {
}

// Class implementing the Marker Interface
class Book implements Printable {
    ...
}

// Main class to demonstrate the Marker Interface
public class MarkerInterfaceExample {
    public static void main(String[] args) {
        Book book = new Book("Sample Book");
        
        if (book instanceof Printable) {
            System.out.println("Book is printable.");
        } else {
            System.out.println("Book is not printable.");
        }
    }
}
```

---
### > What is Object Cloning?

An ability to recreate an object entirely similar to an existing object is known as Object Cloning in Java. Java provides a clone() method to clone a current object offering the same functionality as the original object.
```java
// Class to be cloned
class Person implements Cloneable {
    private String name;
    private int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
    
    // Override the clone() method
    @Override
    public Person clone() throws CloneNotSupportedException {
        return (Person) super.clone();
    }
}

// Main class to demonstrate object cloning
public class ObjectCloningExample {
    public static void main(String[] args) {
        try {
            // Create an object to be cloned
            Person person1 = new Person("John Doe", 25);
            
            // Perform cloning
            Person person2 = person1.clone();
            
            // Modify the cloned object
            person2.setName("Jane Smith");
            person2.setAge(30);
            
            // Display information of both objects
            System.out.println("Original Person: " + person1.getName() + ", Age: " + person1.getAge());
            System.out.println("Cloned Person: " + person2.getName() + ", Age: " + person2.getAge());
        } catch (CloneNotSupportedException e) {
            e.printStackTrace();
        }
    }
}
```

---
### > Can Java be said to be the complete object-oriented programming language

No, Java cannot be treated as a complete object-oriented programming language.

---
### > What is an object-oriented paradigm?

A Paradigm that is based on the concepts of “Objects.” It contains data and code. Data that is in the form of fields, and regulation, that is in the form of procedures. The exciting feature of this paradigm is that the object’s procedures can access and often modify the data fields themselves.

---
### > Define Wrapper Classes in Java.

In Java, when you declare primitive datatypes, then Wrapper classes are responsible for converting them into objects(Reference types). 
```java
public class WrapperClassExample {
    public static void main(String[] args) {
        // Creating wrapper objects
        Integer number1 = new Integer(42);
        Double number2 = new Double(3.14);
        Boolean flag = new Boolean(true);
        Character ch = new Character('A');

        // Using wrapper objects
        System.out.println("Number 1: " + number1);
        System.out.println("Number 2: " + number2);
        System.out.println("Flag: " + flag);
        System.out.println("Character: " + ch);

        // Converting wrapper objects to primitive values
        int value1 = number1.intValue();
        double value2 = number2.doubleValue();
        boolean value3 = flag.booleanValue();
        char value4 = ch.charValue();

        // Using primitive values
        System.out.println("Value 1: " + value1);
        System.out.println("Value 2: " + value2);
        System.out.println("Value 3: " + value3);
        System.out.println("Value 4: " + value4);

        // Using autoboxing and unboxing
        Integer number3 = 10; // autoboxing
        int value5 = number3; // unboxing

        System.out.println("Number 3: " + number3);
        System.out.println("Value 5: " + value5);
    }
}

```
### > What is a singleton class in Java? And How to implement a singleton class?

A class that can possess only one object at a time is called a singleton class. To implement a singleton class given steps are to be followed:

1.  Make sure that the class has only one object
2.  Give global access to that object

```java
public class Logger {
    private static Logger instance;
    
    // Private constructor to prevent direct instantiation
    private Logger() {
    }
    
    // Static method to access the instance
    public static Logger getInstance() {
        if (instance == null) {
            instance = new Logger();
        }
        return instance;
    }
    
    // Logging method
    public void log(String message) {
        System.out.println("[LOG] " + message);
    }
    
    // Other logging-related methods and implementation details
}


//Usage:
public class LoggingExample {
    public static void main(String[] args) {
        Logger.getInstance().log("Starting the application...");
        // Perform application logic
        
        Logger.getInstance().log("Application execution completed.");
    }
}
```
By using the singleton pattern, all parts of your application can use the same instance of the Logger class, ensuring consistent logging behavior and avoiding the need to pass logger instances around manually.

---
### > Define package in Java.

The package is a collective bundle of classes and interfaces and the necessary libraries and JAR files. The use of packages helps in code reusability.
```java
package com.example.myproject;
```
---
### > Can you implement pointers in a Java Program?

Java Virtual Machine takes care of memory management implicitly. Java's primary motto was to keep programming simple. So, accessing memory directly through pointers is not a recommended action. Hence, pointers are eliminated in Java. 

---
### > Differentiate between instance and local variables.

For instance, variables are declared inside a class, and the scope of variables in java scope of variables in java is limited to only a specific object.

A local variable can be anywhere inside a method or a specific block of code. Also, the scope is limited to the code segment where the variable is declared.  

In summary, instance variables are associated with objects and have class-level scope, whereas local variables are limited to specific methods, constructors, or blocks and have a shorter lifespan. Instance variables store state or data unique to each object, while local variables store temporary data within a specific method, constructor, or block.
```java
public class VariableExample {
    // Instance variable
    private int instanceVariable;
    
    public void instanceVariableDemo() {
        // Local variable
        int localVariable = 10;
        
        System.out.println("Instance variable: " + instanceVariable);
        System.out.println("Local variable: " + localVariable);
    }
    
    public static void main(String[] args) {
        VariableExample obj = new VariableExample();
        obj.instanceVariableDemo();
    }
}

//Instance variable: 0
//Local variable: 10
```

---
### > Explain Java String Pool.

A collection of strings in Java's Heap memory is referred to as Java String Pool. In case you try to create a new string object, JVM first checks for the presence of the object in the pool. If available, the same object reference is shared with the variable, else a new object is created.

---
### > What is an Exception?

An Exception handling in Java is considered an unexpected event that can disrupt the program's normal flow. These events can be fixed through the process of Exception Handling.

---
### > What is the final keyword in Java?
The final keyword ensures that certain entities in Java remain unchanged or unextendable, providing immutability and preventing unintended modifications or overrides.
The term final is a predefined word in Java that is used while declaring values to variables. When a value is declared using the final keyword, then the variable's value remains constant throughout the program's execution.

```java
public class FinalVariableExample {
    public static void main(String[] args) {
        final int constantValue = 10;
        // constantValue = 20; // This will cause a compilation error
        System.out.println("Constant Value: " + constantValue);
    }
}
```

```java
public class FinalMethodExample {
    public final void finalMethod() {
        System.out.println("Final method");
    }
}

public class Subclass extends FinalMethodExample {
    // Cannot override final method
    // public void finalMethod() {
    //     System.out.println("Overridden method");
    // }
}
```
```java
public final class FinalClassExample {
    // Class implementation
}

// Cannot extend final class
// public class Subclass extends FinalClassExample {
//     // Subclass implementation
// }
```

---
### > What happens when the main() isn't declared as static?

When the main method is not declared as static, then the program may be compiled correctly but ends up with a severe ambiguity and throws a run time error that reads "NoSuchMethodError."

---
### > Why is Java a platform independent language?

Java is platform-independent because it uses bytecode and a virtual machine (JVM) to execute code, allowing it to run on any platform with a compatible JVM. The "Write Once, Run Anywhere (WORA)" principle and platform-specific JVM implementations enable Java code to be executed on different operating systems without modification. Java's standard APIs and platform-independent language features further contribute to its portability.

---
### > Why is the main method static in Java?

Java's main() function is static by default, allowing the compiler to call it either before or after creating a class object. The main () function is where the compiler begins programme execution in every Java programme. Thus, the main () method needs to be called by the compiler. If the main () method is permitted to be non-static, the JVM must instantiate its class when calling the function. 

---
### > What part of memory - Stack or Heap - is cleaned in the garbage collection process?

On Heap memory, garbage collection is employed to release the memory used by objects with no references. Every object created in the Heap space has access to the entire application and may be referred to from anywhere.

---
### > What is the difference between the program and the process?

A programme is a non-active entity that includes the collection of codes necessary to carry out a specific operation. When a programme is run, an active instance of the programme called a process is launched. A process is begun by a programme once it has been run. The process carries out the program's specified instructions.

---
### > What are the differences between constructor and method of a class in Java?

In summary, constructors are special methods used for object initialization, while methods define the behavior and actions of objects. Constructors are called automatically when creating an object, whereas methods are invoked explicitly by the programmer.

Initializing the state of the object is done by constructors. A function Object () { \[native code\] }, like methods, contains a group of statements (or instructions) that are carried out when an object is created. A method is a group of statements that work together to complete a certain task and return the outcome to the caller. A method has the option of working without returning anything.

---
### > Which among String or String Buffer should be preferred when there are a lot of updates required to be done in the data?

Because StringBuilder is quicker than StringBuffer, it is advised to utilize it wherever possible. However, StringBuffer objects are the best choice if thread safety is required.

---
### > What happens if the static modifier is not included in the main method signature in Java?

The main function is called by the JVM even before the objects are created, thus even if the code correctly compiles, there will still be an error at runtime.

---
### > Can we make the main() thread a daemon thread?

Yes, This technique designates whether the active thread is a user thread or a daemon thread. For instance, tU.setDaemon(true) would convert a user thread named tU into a daemon thread. On the other side, executing tD.setDaemon(false) would convert a Daemon thread, tD, into a user thread.

It is possible to make the `main()` thread a daemon thread in Java. A daemon thread is a background thread that runs in the background and does not prevent the program from exiting if there are no non-daemon threads running.
Here's a sample code snippet that demonstrates how to make the `main()` thread a daemon thread:

```java
public class MainThreadExample {
    public static void main(String[] args) {
        Thread mainThread = Thread.currentThread();
        mainThread.setDaemon(true); // Set the main thread as a daemon thread

        // Rest of your program logic...

        // Example code to keep the program running for demonstration purposes
        try {
            Thread.sleep(3000); // Sleep for 3 seconds to allow other threads to complete
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Exiting main thread...");
    }
}
```

In the above code, the `Thread.currentThread()` method returns the reference to the main thread. By calling the `setDaemon(true)` method on the main thread, we mark it as a daemon thread. Any code executed after setting the daemon flag will run in the context of the daemon thread.

Please note that setting the `main()` thread as a daemon thread should be done early in the program, ideally before creating any other threads. Once a thread has been started, you cannot change its daemon status.

---
### > What happens if there are multiple main methods inside one class in Java?

There is no limit to the number of major approaches you can use. Overloading is the ability to have main methods with different signatures than main (String \[\]), and the JVM will disregard those main methods.

---
### > How does an exception propagate in the code?

Exceptions in Java propagate through the code by being thrown from a method and moving up the call stack until they are caught by an appropriate exception handler. If an exception is not caught, it becomes an uncaught exception, which can lead to the termination of the program.

---
### > How do exceptions affect the program if it doesn't handle them?

If you don't handle an exception when it happens, the program will abruptly stop, and any code following the line where the exception occurred will not be executed.

---
### > Is it mandatory for a catch block to be followed after a try block?

Yes, in Java, if you use a `try` block to handle exceptions, it is mandatory to have at least one `catch` block or a `finally` block (or both) following the `try` block. This ensures that exceptions thrown within the `try` block can be caught and handled appropriately.

The `catch` block is used to specify the type of exception to catch and the corresponding code to handle the exception. Multiple `catch` blocks can be used to handle different types of exceptions.

Alternatively, you can use a `finally` block without any `catch` block. The `finally` block is executed regardless of whether an exception occurred or not. It is commonly used to perform cleanup operations or release resources.

In summary, to properly handle exceptions in Java, a `try` block must be followed by either a `catch` block or a `finally` block (or both).

---
### > Can you call a constructor of a class inside another constructor?

Yes, it is possible to call a constructor of a class inside another constructor in Java. This process is known as constructor chaining. It allows code reuse and enables different constructors to initialize the object with various parameter values.
```java
public class MyClass {
    private int value;

    public MyClass() {
        this(10); // Calling another constructor of the same class with a default value
    }

    public MyClass(int value) {
        this.value = value;
        System.out.println("Constructor called with value: " + value);
    }

    public static void main(String[] args) {
        MyClass obj1 = new MyClass(); // Calling the default constructor
        MyClass obj2 = new MyClass(20); // Calling the parameterized constructor
    }
}

//Constructor called with value: 10
//Constructor called with value: 20
```

---
### > Contiguous memory locations are usually used for storing actual values in an array but not in ArrayList. Explain.

Primitive data types like int, float, and others are typically present in an array. In such circumstances, the array immediately saves these elements at contiguous memory regions. While an ArrayList does not contain primitive data types. Instead of the actual object, an ArrayList includes the references to the objects' many locations in memory. The objects are not kept in consecutive memory regions because of this.

In Java, arrays use contiguous memory locations to store actual values, whereas `ArrayList` does not rely on contiguous memory allocation. Instead, `ArrayList` dynamically manages an underlying array to store its elements.

Here's a sample code that demonstrates the difference in memory allocation between an array and an `ArrayList`:

```java
import java.util.ArrayList;

public class MemoryAllocationExample {
    public static void main(String[] args) {
        // Array - Contiguous memory allocation
        int[] array = new int[5]; // Allocate an array of size 5
        array[0] = 10;
        array[1] = 20;
        array[2] = 30;
        array[3] = 40;
        array[4] = 50;

        // ArrayList - Dynamic memory allocation
        ArrayList<Integer> arrayList = new ArrayList<>();
        arrayList.add(10);
        arrayList.add(20);
        arrayList.add(30);
        arrayList.add(40);
        arrayList.add(50);

        // Accessing elements
        System.out.println("Array:");
        for (int i = 0; i < array.length; i++) {
            System.out.println(array[i]);
        }

        System.out.println("\nArrayList:");
        for (int i = 0; i < arrayList.size(); i++) {
            System.out.println(arrayList.get(i));
        }
    }
}
```

In the above code, an array of `int` is allocated with a fixed size of 5. The elements are assigned specific values using index-based access.

On the other hand, an `ArrayList` of `Integer` is created without specifying an initial size. It dynamically resizes its underlying array as elements are added. Elements are added to the `ArrayList` using the `add()` method.

The code then demonstrates accessing elements from both the array and the `ArrayList` using loops. The output displays the values stored in each collection.

Note: In practice, the `ArrayList` implementation in Java handles the resizing of the underlying array automatically, providing a convenient way to store and manipulate collections of objects without worrying about contiguous memory allocation.

---
### > Why does the java array index start with 0?

The convention of starting array indices at 0 in Java and many other programming languages is rooted in the implementation of arrays using pointer arithmetic. It simplifies memory addressing and calculations by aligning the offset of the first element with 0. Starting at 0 also provides consistency and intuitiveness in array manipulation and indexing, as the index directly corresponds to the position of an element in the array. However, it's worth noting that there are languages that deviate from this convention and allow different starting indices.

The distance from the array's beginning is just an offset. There is no distance because the first element is at the beginning of the array. Consequently, the offset is 0.

---
### > Why is the remove method faster in the linked list than in an array?

Because there is no background scaling of an array, insertion, addition, and removal operations are quicker with a LinkedList. Only references in adjacent items need to update when a new item is added in the middle of the list.

---
### > How many overloaded add() and addAll() methods are available in the List interface? Describe the need and uses.

List is an interface in the Java Collections Framework. The add() and addAll() methods are the main methods at the List interface. 
The add() method is used to add an element to the list, while the addAll() method is used to add a collection of elements to the list.

***The List interface contains two overloaded versions of the add() method:***

The first add() method accepts a single argument of type E, the element to be added to the list.
The second add() method accepts a variable number of arguments of type E, which are the elements to be added to the list.

***The List interface also contains two overloaded versions of the addAll() method:***

The first addAll() method accepts a single argument of type Collection<? Extends E>, which is the collection of elements to be added to the list.

The second addAll() method accepts a variable number of arguments of type E, which are the elements to be added to the list.

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class ListMethodsExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();

        // add()
        list.add("Apple");
        list.add("Banana");

        // add(int index, E element)
        list.add(1, "Orange");

        // addAll(Collection<? extends E> collection)
        List<String> fruits = Arrays.asList("Mango", "Grapes");
        list.addAll(fruits);

        // addAll(int index, Collection<? extends E> collection)
        List<String> moreFruits = Arrays.asList("Pineapple", "Watermelon");
        list.addAll(2, moreFruits);

        // Print the list
        System.out.println(list);
    }
}

//[Apple, Orange, Pineapple, Watermelon, Banana, Mango, Grapes]
```

---
### > How does the size of ArrayList grow dynamically? And also state how it is implemented internally?

A resizable array implementation in Java is called ArrayList. Dynamically expanding array lists make it possible to add new elements at any time. 
The underlying data structure of the ArrayList is an array of the Object class. The ArrayList class in Java has three constructors. 
There are available readObject and writeObject methods specific to it. The Object Array in an ArrayList is temporary. 
There are implemented and Serialization-capable versions of RandomAccess, Cloneable, and java.io (that are Marker Interface in Java).

---
### > Although inheritance is a popular OOPs concept, it is less advantageous than composition. Explain.

Composition, as an alternative to inheritance, offers advantages such as flexibility, code reusability, encapsulation, and reduced coupling. 
It allows for the assembly of different objects to achieve desired behaviors and promotes a more modular and maintainable code structure. 
While inheritance is still valuable in certain scenarios, composition provides greater flexibility and adaptability in object-oriented programming.

```java
// Composition Example
class Engine {
    public void start() {
        System.out.println("Engine started.");
    }
}

class Car {
    private Engine engine;

    public Car() {
        this.engine = new Engine();
    }

    public void startEngine() {
        engine.start();
    }
}

public class CompositionExample {
    public static void main(String[] args) {
        Car car = new Car();
        car.startEngine();
    }
}
```

---
### > What are Composition and Aggregation? State the difference.

Aggregation (HAS-A) and composition are its two forms (Belongs-to). In contrast to composition, which has a significant correlation, the aggregation has a very modest association. 
Aggregation can be thought of as a more confined version of the composition. Since all compositions are aggregates but not all aggregates are compositions, aggregate can be thought of as the superset of composition.

---
### > How is the creation of a String using new() different from that of a literal?

The new () operator always produces a new object in heap memory when creating a String object. 
The String pool may return an existing object if we build an object using the String literal syntax, such as "Baeldung," on the other hand.

---
### > How is the ‘new' operator different from the ‘newInstance()' operator in java?

Both the new operator and the newInstance() method are used to create objects in Java. If we already know the kind of object to create, we can use the new operator; however, if the type of object to create is supplied to us at runtime, we must use the newInstance() function.
```java
// Example class
class Person {
    private String name;
    
    public Person(String name) {
        this.name = name;
    }
    
    public void introduce() {
        System.out.println("Hello, my name is " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating an instance using the new operator
        Person person1 = new Person("John");
        person1.introduce();  // Output: Hello, my name is John
        
        try {
            // Creating an instance using newInstance() method
            Class<?> personClass = Person.class;
            Person person2 = (Person) personClass.newInstance();
            person2.introduce();  // Output: Hello, my name is null (default value)
        } catch (InstantiationException | IllegalAccessException ex) {
            ex.printStackTrace();
        }
    }
}
```

---
### > Is exceeding the memory limit possible in a program despite having a garbage collector?

Yes, even with a garbage collector in place, the programme could still run out of memory. Garbage collection aids in identifying and removing programme objects that are no longer needed in order to release the resources they use. 
When an object in a programme cannot be reached, trash collection is executed with respect to that object. 
If there is not enough memory available to create new objects, a garbage collector is used to free up memory for things that have been removed from the scope. 
When the amount of memory released is insufficient for the creation of new objects, the program's memory limit is exceeded.

---
### > Why is synchronization necessary? Explain with the help of a relevant example.

Multiple threads trying to access the same resources in a multi-threaded software may frequently result in unexpected and incorrect outcomes. 
Therefore, it must be ensured through some form of synchronization that only one thread can access the resource at any given time. 
Java offers a method for setting up threads and synchronizing their operations with the aid of synchronized blocks. 
The synchronized keyword in Java is used to identify synchronized blocks. 
In Java, a synchronized block is one that is tied to an object. Only one thread can be running at a time inside synchronized blocks since they are all synchronized on the same object. 
Until the thread inside the synchronized block exits the block, all other threads trying to enter the block are blocked. 


```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        Counter counter = new Counter();

        // Create multiple threads to increment the counter
        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        // Start the threads
        thread1.start();
        thread2.start();

        // Wait for the threads to finish
        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        // Print the final count
        System.out.println("Final count: " + counter.getCount());
    }
}
```

In this example, the `Counter` class has two synchronized methods: `increment()` and `getCount()`. 
These methods are synchronized using the `synchronized` keyword, which ensures that only one thread can execute the synchronized block at a time.

We create two threads, `thread1` and `thread2`, that concurrently increment the counter by calling the `increment()` method. 
The `join()` method is used to wait for the threads to finish their execution before printing the final count.

By using synchronization, we guarantee that the counter is incremented correctly and avoid potential race conditions that could occur if multiple threads accessed and modified the counter concurrently without synchronization.


---
### > Can you explain the Java thread lifecycle?

A thread can be in any of the following states in Java. These are the states:

*   New: A new thread is always in the new state when it is first formed. The function hasn't been run yet, thus it hasn't started to execute for a thread in the new state.
*   Active: A thread switches from the new state to the active state when it calls the start() method. The runnable state and the running state are both contained within the active state.
*   Blocked or Waiting: A thread is either in the blocked state or the waiting state when it is inactive for a while (but not indefinitely).
*   Timed waiting: When we use the sleep () method on a particular thread, we are actually engaging in timed waiting. The thread enters the timed wait state using the sleep () function. The thread awakens when the allotted time has passed and resumes execution where it left off.
*   Termination: A thread that has been terminated means it is no longer active in the system. In other words, the thread is inactive and cannot be revived (made active again after being killed).

---
### > What could be the tradeoff between the usage of an unordered array versus the usage of an ordered array?

When opposed to an unordered array, which has a time complexity of O, an ordered array's search times have a time complexity of O(log n) (n). 
Due to the need to shift the elements with higher values to create room for the new member, an ordered array has a temporal complexity of O(n) during the insertion process. 
Instead, an unordered array's insertion operation requires a constant O amount of time (1).

---
### > Is it possible to import the same class or package twice in Java and what happens to it during runtime?

The same package or class may be imported more than once. Neither the JVM nor the compiler raise an objection. 
Even if you import the same class several times, the JVM will only internally load it once.

---
### > In case a package has sub packages, will it suffice to import only the main package? e.g. Does importing of com.myMainPackage.\* also import com.myMainPackage.mySubPackage.\*?

Sub-packages won't be imported when a package is imported. When you import a package, all of its classes and interfaces—with the exception of those from its sub-packages—are imported.
```java
package com.example.application; // Main package

// Import statements

public class MainApplication {
    // Main class code
}

package com.example.application.models; // Sub-package

// Import statements

public class UserModel {
    // User model code
}

package com.example.application.controllers; // Sub-package

// Import statements

public class UserController {
    // User controller code
}

package com.example.application.utils; // Sub-package

// Import statements

public class StringUtils {
    // String utility code
}
```

---
### > Will the final block be executed if the code System.exit(0) is written at the end of the try block?

The system is established as the last line to be run, after which nothing will happen, therefore both the catch and finally blocks are essentially ignored.

---
### > Explain the term “Double Brace initialization” in Java?

The outer braces of the double-brace initialization construct an anonymous class that is descended from the provided class and gives an initializer block for that class (the inner braces).

this technique is not widely recommended in professional codebases due to potential memory leaks and performance overhead caused by creating unnecessary inner classes. It's generally considered a best practice to use regular initialization instead, but understanding the concept can still be useful. Here's a sample of Double Brace Initialization:

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class DoubleBraceInitializationSample {

    public static void main(String[] args) {
        // Double brace initialization for ArrayList
        List<String> stringList = new ArrayList<String>() {{
            add("Hello");
            add("World");
            add("Java");
        }};

        // Double brace initialization for HashMap
        Map<String, Integer> stringMap = new HashMap<String, Integer>() {{
            put("one", 1);
            put("two", 2);
            put("three", 3);
        }};

        // Printing the initialized collections
        System.out.println("stringList: " + stringList);
        System.out.println("stringMap: " + stringMap);
    }
}
```

---
### > Why is it said that the length() method of String class doesn't return accurate results?

Since this char \[\] array is used by the Java String class internally, the length variable cannot be made public.
There might be some confusion or misconceptions around its usage due to factors like character encodings, escape sequences, array length syntax, or trailing white spaces in the string. 
 
---
### > What are the possible ways of making objects eligible for garbage collection (GC) in Java?

If a reference variable for an object is removed from the programme while it is running, the object may be trash collected. 
They are also referred to as inaccessible objects occasionally.  The new operator returns a reference to an object after dynamically allocating memory for it.
```java
public class GarbageCollectionSample {
    public static void main(String[] args) {
        // Scenario 1: Nullifying the reference
        SomeObject obj1 = new SomeObject();
        obj1 = null; // obj1 is now eligible for garbage collection

        // Scenario 2: Reassigning the reference
        SomeObject obj2 = new SomeObject();
        SomeObject anotherObj = new SomeObject();
        obj2 = anotherObj; // obj2 is now eligible for garbage collection

        // Scenario 3: Exiting the method
        createObject(); // The object created inside the createObject method is eligible for garbage collection

        // Scenario 4: Circular reference
        SomeObject objA = new SomeObject();
        SomeObject objB = new SomeObject();
        objA.setReference(objB);
        objB.setReference(objA);
        // If there are no other references to objA and objB, both objects are eligible for garbage collection
    }

    public static void createObject() {
        SomeObject obj = new SomeObject();
        // obj will be eligible for garbage collection after this method exits
    }
}

class SomeObject {
    private SomeObject reference;

    public void setReference(SomeObject reference) {
        this.reference = reference;
    }
}
```

---
### > What is the best way to inject dependency? Also, state the reason.

Constructor injection. A class requesting its dependencies through its function Object() { \[native code\] } is the most typical instance of dependency injection. Since the client cannot be constructed without the required dependencies, this guarantees that it is always in a correct state.

```java
public class Printer {
    public void print(String message) {
        System.out.println(message);
    }
}

public class Logger {
    private final Printer printer;

    // Constructor injection: Printer dependency is passed through the constructor
    public Logger(Printer printer) {
        this.printer = printer;
    }

    public void log(String message) {
        printer.print(message);
    }
}

public class Main {
    public static void main(String[] args) {
        // Create a Printer object
        Printer printer = new Printer();

        // Create a Logger object with the Printer dependency injected
        Logger logger = new Logger(printer);

        // Use the Logger to print a message
        logger.log("This is a log message.");
    }
}
```

---
### > How we can set the spring bean scope. And what supported scopes does it have?

There are four ways to set the scope of a Spring bean: singleton, prototype, request, and session.

The singleton scope creates a single instance of a bean, which is shared by all objects that request it. 

The prototype scope creates a new instance of a bean for each object that requests it.

The request and session scopes are only available in a web-based context. The request scope creates a new bean instance for each HTTP request, and 

The session scope creates a single instance of a bean shared by all objects in a single HTTP session.
```java
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Scope;

@Configuration
public class AppConfig {

    @Bean
    @Scope("singleton") // Default scope, same as @Scope(ConfigurableBeanFactory.SCOPE_SINGLETON)
    public MySingletonBean singletonBean() {
        return new MySingletonBean();
    }

    @Bean
    @Scope("prototype")
    public MyPrototypeBean prototypeBean() {
        return new MyPrototypeBean();
    }

    @Bean
    @Scope("request")
    public MyRequestBean requestBean() {
        return new MyRequestBean();
    }

    @Bean
    @Scope("session")
    public MySessionBean sessionBean() {
        return new MySessionBean();
    }

    @Bean
    @Scope("globalSession")
    public MyGlobalSessionBean globalSessionBean() {
        return new MyGlobalSessionBean();
    }
}

class MySingletonBean {
    // Singleton bean logic here
}

class MyPrototypeBean {
    // Prototype bean logic here
}

class MyRequestBean {
    // Request-scoped bean logic here
}

class MySessionBean {
    // Session-scoped bean logic here
}

class MyGlobalSessionBean {
    // Global session-scoped bean logic here
}
```

---
### > What are the different categories of Java Design patterns?

The three categories of Java design patterns are creational, structural, and behavioural design patterns.

---
### > What is a Memory Leak? Discuss some common causes of it.

A memory leak is the slow degradation of system performance over time brought on by the fragmentation of a computer's RAM as a result of shoddy application design or programming that fails to release memory chunks when they are no longer required. These memory leaks frequently result from session items in excess, insertion into Collection objects without deletion, infinite caches, excessive page switching on the operating system, listener methods that are not called, and bespoke data structures that are poorly written.

---
### > Assume a thread has a lock on it, calling the sleep() method on that thread will release the lock?

No, the thread might release the locks using notify, notifyAll(), and wait() methods.

---
### > Write a Java Program to print Fibonacci Series using Recursion.

class FibonacciExample2{  

 static int n1=0,n2=1,n3=0;    
 static void printFibonacci(int count){    
    if(count>0){    
         n3 = n1 + n2;    
         n1 = n2;    
         n2 = n3;    
         System.out.print(" "+n3);   
         printFibonacci(count-1);    
     }    
   }    

    public static void main(String args\[\]){    
      int count=10;    
      System.out.print(n1+" "+n2);//printing 0 and 1  
      
      printFibonacci(count-2);//n-2 because 2 numbers are already printed   
    }  
 }  

---
### > Write a Java program to check if the two strings are anagrams.
An anagram is a word or phrase formed by rearranging the letters of another word or phrase, typically using all the original letters exactly once. In simpler terms, two words are considered anagrams if they have the same characters, but the order of the characters is different.

For example:
"listen" and "silent" are anagrams because they have the same characters.
"triangle" and "integral" are anagrams because they have the same characters.

```java
import java.util.Arrays;     
public class AnagramString {  

    static void isAnagram(String str1, String str2) {  
        String s1 = str1.replaceAll("\\\\s", "");  
        String s2 = str2.replaceAll("\\\\s", "");  
        boolean status = true;  

        if (s1.length() != s2.length()) {  
            status = false;  
        } else {  
            char\[\] ArrayS1 = s1.toLowerCase().toCharArray();  
            char\[\] ArrayS2 = s2.toLowerCase().toCharArray();  
            Arrays.sort(ArrayS1);  
            Arrays.sort(ArrayS2);  
            status = Arrays.equals(ArrayS1, ArrayS2);  
        }  

        if (status) {  
            System.out.println(s1 + " and " + s2 + " are anagrams");  
        } else {  
            System.out.println(s1 + " and " + s2 + " are not anagrams");  
        }  
    }  

    public static void main(String\[\] args) {  
        isAnagram("Keep", "Peek");  
        isAnagram("Mother In Law", "Hitler Woman");  
    }  
}  
```
Output

Keep and Peek are anagrams
MotherInLaw and HitlerWoman are anagrams

---
### > Write a Java Program to find the factorial of a given number.

4! = 4\*3\*2\*1 = 24  
5! = 5\*4\*3\*2\*1 = 120  
```java
import java.util.Scanner;

public class FactorialCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number to find its factorial: ");
        int number = scanner.nextInt();

        if (number < 0) {
            System.out.println("Factorial is not defined for negative numbers.");
        } else {
            long factorial = calculateFactorial(number);
            System.out.println("Factorial of " + number + " is: " + factorial);
        }

        scanner.close();
    }

    public static long calculateFactorial(int n) {
        if (n == 0 || n == 1) {
            return 1;
        } else {
            long factorial = 1;
            for (int i = 2; i <= n; i++) {
                factorial *= i;
            }
            return factorial;
        }
    }
}

```

---
### > Given an array of non-duplicating numbers from 1 to n where one number is missing, write an efficient java program to find that missing number.

Input: arr\[\] = {1, 2, 4, 6, 3, 7, 8}, N = 8
             Output: 5
            Explanation: The missing number between 1 to 8 is 5

You can find the missing number in an array of non-duplicating numbers from 1 to n by using the sum of the arithmetic series formula and calculating the sum of the given array. The missing number can be determined by subtracting the sum of the array elements from the expected sum of the sequence of numbers from 1 to n. Here's an efficient Java program to achieve this:

```java
public class MissingNumberFinder {
    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 6, 3, 7, 8};
        int n = 8;

        int missingNumber = findMissingNumber(arr, n);
        System.out.println("The missing number is: " + missingNumber);
    }

    public static int findMissingNumber(int[] arr, int n) {
        // Calculate the sum of the sequence from 1 to n using the arithmetic series formula
        int expectedSum = n * (n + 1) / 2;

        // Calculate the sum of the elements in the given array
        int actualSum = 0;
        for (int num : arr) {
            actualSum += num;
        }

        // The missing number is the difference between the expected sum and the actual sum
        int missingNumber = expectedSum - actualSum;

        return missingNumber;
    }
}
```

In this program, we have a method called `findMissingNumber` that takes the array `arr` and the integer `n` as input. It calculates the expected sum of the sequence from 1 to `n` using the arithmetic series formula `(n * (n + 1) / 2)`. Then, it calculates the actual sum of the elements in the given array. The missing number is obtained by subtracting the actual sum from the expected sum.

In the provided example, the array contains elements from 1 to 8, and the missing number is 5. The program will correctly output `5`.
You can test the program with different arrays and `N` values to find the missing number for different scenarios.

---
### > Write a Java Program to check if any number is a magic number or not. 

In mathematics, a "magic number" is a number where the recursive sum of its digits eventually leads to a single-digit number, which is usually 1. The process of adding the digits of a number to get a new number continues until a single-digit number is reached.

```java
import java.util.Scanner;

public class MagicNumberChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();

        if (isMagicNumber(number)) {
            System.out.println(number + " is a magic number!");
        } else {
            System.out.println(number + " is not a magic number.");
        }

        scanner.close();
    }

    public static boolean isMagicNumber(int number) {
        while (number > 9) {
            int sum = 0;
            while (number != 0) {
                sum += number % 10;
                number /= 10;
            }
            number = sum;
        }

        return number == 1;
    }
}
```

In this program, we have a method called `isMagicNumber`, which takes an integer `number` as input. It repeatedly calculates the sum of the digits of the number until the number becomes a single-digit number (less than or equal to 9). If the final single-digit number is 1, then the input number is a magic number.

For example, let's say we input the number `19`. The program will calculate the sum of its digits: `1 + 9 = 10`. As the result is not a single-digit number, the program will calculate the sum of the digits again: `1 + 0 = 1`. Since the result is now 1, the program will return `true`, indicating that `19` is a magic number.

On the other hand, if we input the number `23`, the program will calculate the sum of its digits: `2 + 3 = 5`. Since the result is already a single-digit number and not 1, the program will return `false`, indicating that `23` is not a magic number.

---
### > Write a Java program to create and throw custom exceptions.
In Java, you can create custom exceptions by extending the `Exception` or `RuntimeException` class (or any of their subclasses) to define your custom exception class. Here's an example Java program that demonstrates how to create and throw custom exceptions:

```java
class MyCustomException extends Exception {
    public MyCustomException() {
        super();
    }

    public MyCustomException(String message) {
        super(message);
    }
}

public class CustomExceptionDemo {
    public static void main(String[] args) {
        try {
            int age = 15;
            if (age < 18) {
                throw new MyCustomException("You must be at least 18 years old.");
            } else {
                System.out.println("You are eligible to proceed.");
            }
        } catch (MyCustomException e) {
            System.err.println("Custom Exception: " + e.getMessage());
        }
    }
}
```

---
### > Write a java program to check if any number given as input is the sum of 2 prime numbers.        

To check if a given number is the sum of two prime numbers, we can implement a Java program using a function that checks if a number is prime and then use that function to find two prime numbers whose sum equals the given input number. Here's how you can do it:

```java
import java.util.Scanner;

public class SumOfTwoPrimes {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();

        boolean isSumOfTwoPrimes = checkSumOfTwoPrimes(number);

        if (isSumOfTwoPrimes) {
            System.out.println(number + " can be expressed as the sum of two prime numbers.");
        } else {
            System.out.println(number + " cannot be expressed as the sum of two prime numbers.");
        }

        scanner.close();
    }

    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

    public static boolean checkSumOfTwoPrimes(int number) {
        for (int i = 2; i <= number / 2; i++) {
            int num1 = i;
            int num2 = number - i;
            if (isPrime(num1) && isPrime(num2)) {
                return true;
            }
        }
        return false;
    }
}
```

In this program, we first take a number as input from the user. Then, we have two methods:

1. `isPrime`: This method checks whether a given number is prime or not. It returns `true` if the number is prime and `false` otherwise.

2. `checkSumOfTwoPrimes`: This method takes the input number as an argument and checks whether it can be expressed as the sum of two prime numbers. It iterates through all possible pairs of numbers whose sum is equal to the input number and checks if both numbers are prime. If it finds such a pair, it returns `true`; otherwise, it returns `false`.

Finally, we call the `checkSumOfTwoPrimes` method with the user-input number and display the result to the user.

For example, if the user inputs `34`, the program will output:
```
34 can be expressed as the sum of two prime numbers.
```
This means that `34` can be expressed as `3 + 31`, where both `3` and `31` are prime numbers.

---
### > Write a Java program for solving the Tower of Hanoi Problem.

 // Java recursive program to solve tower of hanoi puzzle
```java
import java.util.Scanner;

public class TowerOfHanoi {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the number of disks: ");
        int numDisks = scanner.nextInt();

        solveTowerOfHanoi(numDisks, 'A', 'C', 'B');

        scanner.close();
    }

    public static void solveTowerOfHanoi(int n, char source, char destination, char auxiliary) {
        if (n == 1) {
            System.out.println("Move disk 1 from " + source + " to " + destination);
            return;
        }

        // Move n-1 disks from source to auxiliary peg using destination peg as the auxiliary peg
        solveTowerOfHanoi(n - 1, source, auxiliary, destination);

        // Move the nth disk from source to destination peg
        System.out.println("Move disk " + n + " from " + source + " to " + destination);

        // Move the n-1 disks from auxiliary peg to destination peg using source peg as the auxiliary peg
        solveTowerOfHanoi(n - 1, auxiliary, destination, source);
    }
}
```
---
### >  Implement Binary Search in Java using recursion.
```

public class BinarySearchRecursive {
    public static void main(String[] args) {
        int[] arr = {2, 5, 8, 12, 16, 23, 38, 45, 56, 72};
        int target = 16;

        int index = binarySearch(arr, target);

        if (index != -1) {
            System.out.println("Element found at index " + index);
        } else {
            System.out.println("Element not found in the array.");
        }
    }

    public static int binarySearch(int[] arr, int target) {
        return binarySearchRecursive(arr, target, 0, arr.length - 1);
    }

    private static int binarySearchRecursive(int[] arr, int target, int low, int high) {
        if (low <= high) {
            int mid = low + (high - low) / 2;

            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                return binarySearchRecursive(arr, target, mid + 1, high);
            } else {
                return binarySearchRecursive(arr, target, low, mid - 1);
            }
        }

        // Element not found
        return -1;
    }
}
```

### 75\. Is delete, next, main, exit or null keyword in java?

No, these keywords do not exist in Java. Delete, Next, Exit are the operations performed in the Java program, Main is the predefined method, and Null is the default String type.

With this we are done with the first section that is Basic Java Interview Question, Now, lets move on to our next section of Intermediate Java Interview Questions.

Java Interview Coding Questions For Intermediate
------------------------------------------------

Now, let's have a look at some of the most asked Java technical interview questions for intermediate experienced professionals.

### 76\. What is JDK? Mention the variants of JDK?

JDK is an abbreviation for Java Development Kit. It is a combined Package of JRE and Developer tools used for [designing Java Applications](https://www.simplilearn.com/popular-java-applications-article "designing Java Applications") and Applets. Oracle has the following variants.

*   JDK Standard Edition
*   JDK Enterprise Edition
*   JDK Micro Edition

### 77\. What is the difference between JDK, JRE, and JVM?

JVM has a Just in Time (JIT) compiler tool that converts all the Java source code into the low-level compatible machine language. Therefore, it runs faster than the regular application.

JRE has class libraries and other JVM supporting files. But it doesn’t have any tool for java development such as compiler or debugger.

JDK has tools that are required to write Java Programs and uses JRE to execute them. It has a compiler, Java application launcher, and an applet viewer.

### 78\. What is a JIT compiler?

JIT compiler refers to Just in Time compiler. It is the simplest way of executing the computer code that takes in compilation during the execution of a program rather than before performance. It commonly uses bytecode translation to machine code. It is then executed directly.

### 79\. What are Brief Access Specifiers and Types of Access Specifiers?

Access Specifiers are predefined keywords used to help JVM understand the scope of a variable, method, and class. We have four access specifiers.

*   Public Access Specifier 
*   Private Access Specifier 
*   Protected Access Specifier 
*   Default Access Specifier

### 80\. How many types of constructors are used in Java?

There are two [types of constructors in Java](https://www.simplilearn.com/tutorials/java-tutorial/constructor-in-java "types of constructors in Java").

Parameterized Constructors: Parameterized constructor accepts the parameters with which users can initialize the instance variables. Users can initialize the class variables dynamically at the time of instantiating the class.

Default constructors: This type doesn’t accept any parameters; rather, it instantiates the class variables with their default values. It is used mainly for object creation.

### 81\. Can a constructor return a value?

Yes, A constructor can return a value. It replaces the class's current instance implicitly; you cannot make a constructor return a value explicitly.

### 82\. Explain ‘this’ keyword in Java.

The term "this" is a particular keyword designated as a reference keyword. The "this" keyword is used to refer to the current class properties like method, instance, variable, and constructors.

### 83\. Explain ‘super’ keyword in Java.

The term "super" is a particular keyword designated as a reference keyword. The "super" keyword refers to the immediate parent class object.

### 84\. Explain Method Overloading in Java.

The process of creating multiple method signatures using one method name is called Method Overloading in Java. Two ways to achieve method overloading are:

1.  Varying the number of arguments
2.  Changing the return type of the Method 

### 85\. Can we overload a static method?

No, Java does not support the Overloading of a [static method.](https://www.simplilearn.com/tutorials/java-tutorial/static-keyword-in-java "static method.") The process would throw an error reading "static method cannot be referenced."

### 86\. Define Late Binding.

Binding is a process of unifying the method call with the method's code segment. Late binding happens when the method's code segment is unknown until it is called during the runtime. 

### 87\. Define Dynamic Method Dispatch.

The Dynamic method dispatch is a process where the method call is executed during the runtime. A reference variable is used to call the super-class. This process is also known as Run-Time Polymorphism.     

### 88\. Why is the delete function faster in the linked list than an array?

Delete Function is faster in [linked lists in Java](https://www.simplilearn.com/tutorials/java-tutorial/linked-list-in-java "linked lists in Java") as the user needs to make a minor update to the pointer value so that the node can point to the next successor in the list

### 89\. Give a briefing on the life cycle of a thread.

The life cycle of a thread includes five stages, as mentioned below.

1.  New Born State
2.  Runnable State
3.  Running State
4.  Blocked State
5.  Dead State

### 90\. Explain the difference between >> and >>> operators.

Although they look similar, there is a massive difference between both.

*   \>> operator does the job of right shifting the sign bits
*   \>>> operator is used in shifting out the zero-filled bits

### 91\. Brief the life cycle of an applet.

The life cycle of an applet involves the following.

1.  Initialization
2.  Start
3.  Stop
4.  Destroy
5.  Paint

### 92\. Why are generics used in Java Programming?

Compile-time type safety is provided by using generics. Compile-time type safety allows users to catch unnecessary invalid types at compile time. Generic methods and classes help programmers specify a single method declaration, a set of related methods, or related types with an available class declaration. 

### 93\. Explain the Externalizable interface.

The Externalizable interface helps with control over the process of serialization. An "externalisable" interface incorporates readExternal and writeExternal methods.

### 94\. What is the Daemon Thread?

The Daemon thread can be defined as a thread with the least priority. This Daemon thread is designed to run in the background during the Garbage Collection in Java.

The setDaemon() method creates a Daemon thread in Java.

### 95\. Explain the term enumeration in Java.

Enumeration or [enum is an interface in Java](https://www.simplilearn.com/tutorials/java-tutorial/enum-in-java "enum is an interface in Java"). Enum allows the sequential access of the elements stored in a collection in Java.

### 96\. Why is Java is Dynamic?

Java is designed to adapt to an evolving environment. Java programs include a large amount of runtime information that is used to resolve access to objects in real-time. 

### 97\. Can you run a code before executing the main method?

Yes, we can execute any code, even before the main method. We will be using a static block of code when creating the objects at the class's load time. Any statements within this static block of code will get executed at once while loading the class, even before creating objects in the main method.

### 98\. How many times is the finalize method called?

The finalize method is called the Garbage collector. For every object, the Garbage Collector calls the finalize() method just for one time.

Java Interview Questions for Experienced
----------------------------------------

Now, lets move on to our last section of Advanced Core Java Interview Questions which is primarly useful for experienced and working professionals.

### 99\. Can "this" and "super" keywords be used together?

No, "this" and "super" keywords should be used in the first statement in the class constructor. The following code gives you a brief idea.

public class baseClass {  

     baseClass() {  

         super();   

         this();  

         System.out.println(" baseClass object is created");  

     }  

     public static void main(String \[\]args){  

         baseClass bclass = new baseClass();  

     }  

}

### 100\. What is a JSP page?

JSP is an abbreviation for Java Servlet Page. The JSP page consists of two types of text.

*   Static Data 
*   JSP elements

Find Our Java Training in Top Cities

India

United States

Other Countries

[Java Training in Bangalore](https://www.simplilearn.com/advanced-java-training-course-bangalore-city "Java Training in Bangalore")

[Java Training New York](https://www.simplilearn.com/advanced-java-training-course-new-york-city "Java Training New York")

[Java Course London](https://www.simplilearn.com/advanced-java-training-course-london-city "Java Course London")

[Java Training in Chennai](https://www.simplilearn.com/advanced-java-training-course-chennai-city "Java Training in Chennai")

[Java Training San Diego](https://www.simplilearn.com/advanced-java-training-course-san-diego-city "Java Training San Diego")

[Java Course Singapore](https://www.simplilearn.com/advanced-java-training-course-singapore-city "Java Course Singapore")

[Java Training in Hyderabad](https://www.simplilearn.com/advanced-java-training-course-hyderabad-city "Java Training in Hyderabad")

[Java Training Dallas](https://www.simplilearn.com/advanced-java-training-course-dallas-city "Java Training Dallas")

[Java Course Melbourne](https://www.simplilearn.com/advanced-java-training-course-melbourne-city "Java Course Melbourne")

### 101\. What is JDBC?

JDBC is an abbreviation for Java Database Connector.

JDBC is an abstraction layer used to establish connectivity between an existing database and a Java application

### 102\. Explain the various directives in JSP.

Directives are instructions processed by JSP Engine. After the JSP page is compiled into a Servlet, Directives set page-level instructions, insert external files, and define customized tag libraries. Directives are defined using the symbols below:

start with "< %@" and then end with "% >" 

The various types of directives are shown below:

*   Include directive

It includes a file and combines the content of the whole file with the currently active pages.

*   Page directive

Page Directive defines specific attributes in the JSP page, like the buffer and error page.

*   Taglib

Taglib declares a custom tag library, which is used on the page.

### 103\. What are the observer and observable classes?

Objects that inherit the "Observable class" take care of a list of "observers." 

When an Observable object gets upgraded, it calls the update() method of each of its observers. 

After that, it notifies all the observers that there is a change of state. 

The Observer interface gets implemented by objects that observe Observable objects.

### 104\. What is Session Management in Java?

A session is essentially defined as the random conversation's dynamic state between the client and the server. The virtual communication channel includes a string of responses and requests from both sides. The popular way of implementing session management is establishing a session ID in the client's communicative discourse and the server.

### 105\. Briefly explain the term Spring Framework.

Spring is essentially defined as an application [framework in Java](https://www.simplilearn.com/tutorials/java-tutorial/java-frameworks "framework in Java") and inversion of control containers for Java. The spring framework creates enterprise applications in Java. Especially useful to keep in mind that the spring framework's central features are essentially conducive to any Java application.

### 106\. How to handle exceptions in Spring MVC Framework?

Spring MVC has two approaches for handling the exceptions:

*   Exception handler method: In this kind of exception handling, the user will get the @ExceptionHandler annotation type used to annotate a method to handle exceptions.
*   XML Configuration: The user can use the SimpleMappingExceptionResolver bean in Spring’s application file and map the exception.

### 107\. What is JCA in Java?

Java Cryptography Architecture gives a platform and provides architecture and application programming interfaces that enable decryption and encryption. 

Developers use Java Cryptography Architecture to combine the application with the security applications. Java Cryptography Architecture helps in implementing third party security rules and regulations. 

Java Cryptography Architecture uses the hash table, encryption message digest, etc. to implement the security.

### 108\. Explain JPA in Java.

The Java Persistence API enables us to create the persistence layer for desktop and web applications. Java Persistence deals in the following:

1.  Java Persistence API
2.  Query Language
3.  Java Persistence Criteria API
4.  Object Mapping Metadata

### 109\. Explain the different authentications in Java Servlets.

Authentication options are available in Servlets: There are four different options for authentication in servlet:

*   #### Basic Authentication: 
    

Usernames and passwords are given by the client to authenticate the user.

*   #### Form-based authentication: 
    

In this, the login form is made by the programmer by using HTML.

*   #### Digest Authentication: 
    

It is similar to basic authentication, but the passwords are encrypted using the Hash formula. Hash Formula makes digest more secure.

*   #### Client certificate Authentication:
    

It requires that each client accessing the resource has a certificate that it sends to authenticate itself. Client Authentication requires the SSL protocol.

### 110\. Explain FailFast iterator and FailSafe iterator along with examples for each.

FailFast iterators and FailSafe iterators are used in Java Collections. 

FailFast iterators do not allow changes or modifications to the Java Collections, which means they fail when the latest element is added to the collection or an existing element gets removed from the collection. The FailFast iterators tend to fail and throw an exception called ConcurrentModificationException.

Ex: ArrayList, HashMap

Whereas, on the other hand, FailSafe iterators allow changes or modifications to be done on the Java Collections. It is possible, as the FailSafe iterators usually operate on the cloned copy of the collection. Hence, they do not throw any specific exception.

Ex: CopyOnWriteArrayList

### 111\. How do we reverse a string?

The [string can be reversed](https://www.simplilearn.com/tutorials/java-tutorial/reverse-a-string-in-java "string can be reversed") by using the following program.

package simplilearnJava;

public class StringReverse {

public static void main(String args\[\]) {

String str = "Simplilearn";

String reverse = new StringBuffer(str).reverse().toString();

System.out.printf("Actual Word: %s, Word after reversing %s", str, reverse);

}

public static String reverse(String source) {

if (source == null || source.isEmpty()) {

return source;

}

String reverse = "";

for (int i = source.length() - 1; i >= 0; i--) {

reverse = reverse + source.charAt(i);

}

return reverse;

}

}

Expected Output:

Actual Word: Simplilearn, Word after reversing nraelilpmiS

### 112\. Write a program to find the square root of a number.

The Square root of a number can be found by using the following program.

package simplilearnJava;

import java.util.Scanner;

public class SRoot {

public static void main(String args\[\]) {

try (Scanner sc = new Scanner(System.in)) {

System.out.println("Input a number to find square root: ");

double square = sc.nextDouble();

double squareRoot = Math.sqrt(square);

System.out.printf("The square root is: %f ", squareRoot);

}

}

}

Expected Output:

Input a number to find square root: 

25

The square root is: 5

### 113\. Write a program that detects the duplicate characters in a string.

The program that finds the duplicate elements in a string is written below:

package simplilearnJava;

import java.util.HashMap;

import java.util.Map;

import java.util.Set;

public class FindDuplicate {

public static void main(String args\[\]) {

printDuplicateCharacters("Simplilearn");

}

public static void printDuplicateCharacters(String word) {

char\[\] characters = word.toCharArray();

Map<Character, Integer> charMap = new HashMap<Character, Integer>();

for (Character ch : characters) {

if (charMap.containsKey(ch)) {

charMap.put(ch, charMap.get(ch) + 1);

} else {

charMap.put(ch, 1);

}

}

Set<Map.Entry<Character, Integer>> entrySet = charMap.entrySet();

System.out.printf("List of duplicate characters in String '%s' %n", word);

for (Map.Entry<Character, Integer> entry : entrySet) {

if (entry.getValue() > 1) {

System.out.printf("%s: %d %n", entry.getKey(), entry.getValue());

}

}

}

}

Expected output:

List of duplicate characters in String 'Simplilearn.' 

i: 2 

l: 2 

### 114\. Write a Program to remove duplicates in an ArrayList.

The following program can be implemented to remove duplicate elements in an ArrayList

package simplilearnJava;

import java.util.ArrayList;

import java.util.LinkedHashSet;

import java.util.List;

import java.util.Set;

public class ArrayDuplicate {

public static void main(String args\[\]) {

List<Integer> num = new ArrayList<Integer>();

num.add(1);

num.add(2);

num.add(3);

num.add(4);

num.add(5);

num.add(6);

num.add(3);

num.add(4);

num.add(5);

num.add(6);

System.out.println("Your list of elements in ArrayList : " + num);

Set<Integer> primesWithoutDuplicates = new LinkedHashSet<Integer>(num);

num.clear();

num.addAll(primesWithoutDuplicates);

System.out.println("list of original numbers without duplication: " + num);

}

}

Expected Output:

Your list of elements in ArrayList : \[1, 2, 3, 4, 5, 6, 3, 4, 5, 6\]

list of original numbers without duplication: \[1, 2, 3, 4, 5, 6\]

### 115\. Find the word count in a string using HashMap Collection.

The following program can be used for word count.

package simplilearnJava;

import java.util.HashMap;

public class WordCount {

public static void main(String\[\] args) {

String str = "Hello World, Welcome to Simplilearn";

String\[\] split = str.split(" ");

HashMap<String, Integer> map = new HashMap<String, Integer>();

for (int i = 0; i < split.length; i++) {

if (map.containsKey(split\[i\])) {

int count = map.get(split\[i\]);

map.put(split\[i\], count + 1);

} else {

map.put(split\[i\], 1);

}

}

System.out.println(map);

}

}

Expected Output:

{Hello=1, Simplilearn=1, Welcome=1, to=1, World,=1}

### 116\. Write a program to find the Second Highest number in an ArrayList

The following program can be used to find the second biggest number in an array list.

package simplilearnJava;

public class NextHighest {

public static void main(String\[\] args)

    {

        int array\[\] = { 1, 2, 3, 4, 11, 12, 13, 14, 21, 22, 23, 24, 31, 32};

        int high = 0;

        int nextHigh = 0;

        System.out.println("The given array is:");

        for (int i = 0; i < array.length; i++)

        {

            System.out.print(array\[i\] + "\\t");

        }

        for (int i = 0; i < array.length; i++)

        {

            if (array\[i\] > high)

            {

                nextHigh = high;

                high = array\[i\];

            }

            else if (array\[i\] > nextHigh)

            {

                nextHigh = array\[i\];

            }

        }

        System.out.println("Second Highest is:" + nextHigh);

        System.out.println("Highest Number is: "  +high);

    }

}

Expected Output:

The given array is:

1 2 3 4 11 12 13 14 21 22 23 24 31 32

Second Highest is:31

The highest number is: 32

### 117\. What is the difference between System.out, System.err, and System.in?

System.out and System.err represent the monitor by default and thus can be used to send data or results to the monitor. System.out is used to display normal messages and results. System.eerr is used to display error messages. System.in represents InputStream object which by default represents standard input device, i.e., keyboard.

### 118\. Could you provide some implementation of a Dictionary having a large number of words?

The simplest implementation that can be given is that of a List wherein one can place ordered words and perform a Binary search. The other implementation with a better search performance is HashMap where the key is used as the first character of the word and the value as a LinkedList.

Up another level, there are HashMaps like:

hashmap {

a (key) -> hashmap (key-aa , value (hashmap(key-aaa,value)

b (key) -> hashmap (key-ba , value (hashmap(key-baa,value)

z (key) -> hashmap (key-za , value (hashmap(key-zaa,value)

}

Up to n levels where n is the average size of the word in the dictionary.

### 119\. How would you tackle it if you might have to encounter pattern programs in Java?

Solution - [Top 25 Most Frequently asked Pattern Programs in Java](https://www.simplilearn.com/tutorials/java-tutorial/pattern-programs-in-java "Top 25 Most Frequently asked Pattern Programs in Java")

With this, we have come to the end of this Java Interview Questions article. Moving ahead, we will look into the next crucial steps that you could pursue, to master Java.

### 120\. What do you understand by an instance variable and a local variable?

Generally, instance variables are declared in a class but outside methods whereas a local variable is declared within the blocks of code.

//Local Variable

import Java.io.\*;

class Main {

public static void main(String\[\] args)

{

int var = 145;

System.out.println("Local Variable: " + var);

}

}

//Instance variable

import Java.io.\*;

class Main {

public int value = 12;

public static void main(String\[\] args)

{

Main va = new Main();

System.out.println("My value is: " + va.value);

}

}

### 121\. Can the main method be overloaded?

Yes, the main method can be overloaded as many times as we want. Nevertheless, JVM prefers to call the main method with the help of its predefined calling method. 

Example:

class Main {

    public static void main(String args\[\]) {

        System.out.println(" Main Method");

    }

    public static void main(int\[\] args){

        System.out.println("Overloaded Integer array Main Method");

    }

    public static void main(char\[\] args){

        System.out.println("Overloaded Character array Main Method");

    }

    public static int main(double\[\] args){

        System.out.println("Overloaded Double array Main Method");

    }

    public static void main(float args){

        System.out.println("Overloaded float Main Method");

    }

}

### 122\. Comment on method overloading and overriding by citing relevant examples.

Method overloading occurs during the compile time, whereas method overriding occurs during the run time. Static binding is used during overloading, whereas dynamic binding is used during methods overriding.

//Function overloading

#function1

void addPodium(int a, int b)

{

System.out.println(a + b);

}

#function2

float addPodium(float a, float b, float c)

{

System.out.println(a + b + c);

}

//Function overriding

class Parent {

    void show()

    {

        System.out.println("I am Parent");

    }

}

class Child extends Parent {

    void show()

    {

        System.out.println("I am Child");

    }

}

class Main {

    public static void main(String\[\] args)

    {

        Parent obja = new Parent();

        obja.show();

        Parent objb = new Child();

        objb.show();

    }

}

### 123\. A single try block and multiple catch blocks can co-exist in a Java Program. Explain.

One or more catch blocks can follow a try block. Each catch block must have a unique exception handler. So, if you want to perform multiple tasks in response to various exceptions, use the Java multi-catch block.

### 124\. Do final, finally and finalize keywords have the same function?

No, final, finally and finalize keywords have different functionalities.

Final is used to restrict classes, variables, or methods, the final keyword.

Finally is used to execute the code written inside the block without handling any exceptions.

Finalize is used to call the function of the implementation of cleaning the garbage collection of an object. 

### 125\. When can you use the "super" keyword?

Basically, the super keyword is used to refer to the parent class. When there are the same fields in both parent and child classes, then one can use a super keyword to access data members of the parent class.

### 126\. What are shallow copy and deep copy in Java?

In the case of a shallow copy, primitive data types are copied, whereas in the case of a deep copy along with primitive data types the object references are also copied.

### 127\. Using relevant properties highlight the differences between interfaces and abstract classes.

An abstract class can have a combination of both abstract and non-abstract methods, whereas an interface has only abstract methods in it.

### 128\. What are the different ways of thread usage? 

There are two ways to define and implement a thread in Java. They are by implementing the runnable interface and extending the thread class.

Extending the Thread class

class InterviewBitThreadExample extends Thread{  

   public void run(){  

       System.out.println("Thread runs...");  

   }  

   public static void main(String args\[\]){  

       InterviewBitThreadExample ib = new InterviewBitThreadExample();  

       ib.start();  

   }  

}

Implementing the Runnable interface

class InterviewBitThreadExample implements Runnable{  

   public void run(){  

       System.out.println("Thread runs...");  

   }  

   public static void main(String args\[\]){  

       Thread ib = new Thread(new InterviewBitThreadExample()); 

       ib.start();  

   }  

}

Implementing a thread using the method of Runnable interface is more preferred and advantageous as Java does not have support for multiple inheritances of classes.

start() method is used for creating a separate call stack for the thread execution. Once the call stack is created, JVM calls the run() method for executing the thread in that call stack.

### 129\. What is the difference between the ‘throw' and ‘throws' keyword in Java?

The throw keyword is often used to explicitly throw an exception. It can only throw one exception at a time whereas throws can be used to declare multiple exceptions.

### 130\. Identify the output of the below Java program and Justify your answer.

class Main {

    public static void main(String args\[\]) {

        Scaler s = new Scaler(5);

    }

}

class InterviewBit{

    InterviewBit(){

        System.out.println(" Welcome to InterviewBit ");

    }

}

class Scaler extends InterviewBit{

    Scaler(){

        System.out.println(" Welcome to Scaler Academy ");

    }

    Scaler(int x){

        this();

        super();

        System.out.println(" Welcome to Scaler Academy 2");

    }

}

The above code will throw the compilation error. It is because the super() is used to call the parent class constructor. But there is the condition that super() must be the first statement in the block. Now in this case, if we replace this() with super() then also it will throw the compilation error. Because this() also has to be the first statement in the block. So in conclusion, we can say that we cannot use this() and super() keywords in the same block.

### 131\. Java works as a “pass by value” or “pass by reference” phenomenon?

Java works as a “pass by value” phenomenon, because “pass by reference” needs the help of pointers. But there are no pointers in Java.

### 132\. How to not allow serialization of attributes of a class in Java?

One approach to not allow serialization of attributes of a class in Java is by using writeObject() and readObject() methods in the subclass and throwing a not Serializable exception.

### 133\. What are the default values assigned to variables and instances in Java?

By default, for a numerical value it is 0, for the boolean value it is false and for objects it is NULL.

### 134\. What do you mean by data encapsulation?

Data encapsulation is one of the properties of OOPS concepts, where all the data such as variables and methods are enclosed together as a single unit.

### 135\. Can you tell the difference between equals() method and equality operator (==) in Java?

Equality operator (==) is used to check the equality condition between two variables. But the equals() method is used to check the equality condition between two objects.

### 136\. How is an infinite loop declared in Java?

An infinite loop can be declared in Java by breaking the logic in the instruction block.  For example,

for(int i = 1; i > 0; i++)

{

//statements

}

The above code forms an infinite loop in Java.

### 137\. Briefly explain the concept of constructor overloading

The concept of constructor overloading refers to having multiple methods in a class with their name being the same as the class name. The difference lies in the set of parameters passed to the functions.

### 138\. Explain the use of the final keyword in variable, method and class.

In Java, one can apply the final keyword to a variable, methods, and class. With the help of the final keyword, the variable turns out to be a constant, the method cannot be inherited and the class cannot be overridden.

### 139\. Is it possible that the ‘finally' block will not be executed? If yes then list the case.

Yes, there is a possibility that the ‘finally’ block cannot get executed. Here are some of the cases where the above situation occurs.

1.  During the time of fatal errors such as memory exhaustion, memory access error, etc.
2.  During the time of using System.exit()

### 140\. Difference between static methods, static variables, and static classes in Java.

A variable, method, or class can be made static by using the static keyword. A static class cannot be instantiated. When both objects or instances of a class share the same variables, this is referred to as static variables. Static methods are simply methods that refer to the class in which they are written.

### 141\. What is the main objective of garbage collection?

The main goal of using garbage collection is to free the heap memory by eliminating unnecessary objects.

### 142\. Apart from the security aspect, what are the reasons behind making strings immutable in Java?

Because of security, synchronization, concurrency, caching, and class loading, the String is immutable in Java. The reason for making string final would be to destroy its immutability and help stop others from trying to extend it. String objects are cached in the String pool, making them immutable.

### 143\. Which of the below generates a compile-time error? State the reason.

int\[\] n1 = new int\[0\];

boolean\[\] n2 = new boolean\[-200\];

double\[\] n3 = new double\[2241423798\];

char\[\] ch = new char\[20\];

We get a compile-time error in line 3. The error we will get in Line 3 is - the integer number too large. It is because the array requires size as an integer.  And Integer takes 4 Bytes in the memory. And the number (2241423798) is beyond the capacity of the integer. The maximum array size we can declare is - (2147483647).

Because the array requires the size in integer, none of the lines (1, 2, and 4) will give a compile-time error. The program will compile fine. But we get the runtime exception in line 2. The exception is - NegativeArraySizeException. 

Here what will happen is - At the time when JVM will allocate the required memory during runtime then it will find that the size is negative. And the array size can’t be negative. So the JVM will throw the exception.

### 144\. How would you differentiate between a String, StringBuffer, and a StringBuilder?

The string class is immutable but the other two are mutable in nature. StringBuffer is synchronous whereas the StringBuilder is asynchronous. String uses string pool as memory storage whereas the other two use heap memory for storage purposes.

### 145\. What is a Comparator in Java?

A comparator is an interface, which is used to sort the objects. 

### 146\. In Java, static as well as private method overriding is possible. Comment on the statement.

In Java, you could indeed override a private or static method. If you create a similar method in a child class with the same return type and method arguments, it will hide the super class method; this is known as method hiding. Similarly, you cannot override a private method in a subclass because it is not accessible from that.

### 147\. What makes a HashSet different from a TreeSet?

In a HashSet, the elements are unsorted and work faster than a Tree set.  It is implemented using a hash table.

### 148\. Why is the character array preferred over string for storing confidential information?

Because Strings are immutable, any change will result in the creation of a new String, whereas char\[\] allows you to set all of the elements to blank or zero. So storing a password in a character array clearly reduces the security risk of password theft.

### 149\. What are the differences between HashMap and HashTable in Java?

HashMap

HashTable

1\. Asynchronous in nature

1\. Synchronous in nature

2\. Not thread-safe

2\. Thread safe

3\. It allows one null key and null values

3\. It doesn’t allow null keys and values.

### 150\. What is the importance of reflection in Java?

Reflection is a property of Java, enabling the Java code to inspect itself. A Java class, for example, can get the names of all its members and showcase them.

### 151\. What are the different types of Thread Priorities in Java? And what is the default priority of a thread assigned by JVM?

There are different types of thread properties in Java. They are MIN\_PRIORITY, MAX\_PRIORITY, and NORM\_PRIORITY. By default, the thread is assigned NORM\_PRIORITY.

### 152\. What is the ‘IS-A ‘ relationship in OOPs Java?

‘IS-A’ relationship is related to the Inheritance property of OOPs Java. It is a kind of parent-child relationship that is established between two classes.

### 153\. Why is Java, not a pure object-oriented language?

It is not a pure object-oriented language because it supports primitive data types like int, double, and char, which are not objects, and it supports static methods and variables.

### 154\. Can static methods be overridden?

No, static methods cannot be overridden in Java.

### 155\. What are the different ways of thread usage?

Two ways to use threads in Java one is by extending the Thread class or by implementing the Runnable interface. Another way to use threads in Java is by using the Executor framework, which provides a higher level of abstraction for managing threads. 

### 156\. How do you achieve Object Cloning in Java?

Creating a new object with the same state as an existing object called Object Cloning in Java. This can be achieved by implementing the Cloneable interface and overriding the clone() method in the class. 

### 157\. What is a Java Virtual Machine?

It is an abstract machine that provides a runtime environment for Java programs to run. The JVM interprets the compiled Java code and executes it on the underlying operating System.

### 158\. What gives Java its 'write once and run anywhere' nature?

Java's 'write once and run anywhere' nature is achieved by using Java Virtual Machine (JVM) and bytecode. Java code is compiled into bytecode, which can be executed on any platform that has a JVM installed. 

### 159\. What are the advantages of Packages in Java?

Packages in Java provide a way to organize classes and interfaces into namespaces. This helps to avoid naming conflicts and makes it easier to manage large codebases. Packages provide a way to create reusable code through the use of libraries.

### 160\. Explain static variables with examples and a diagram.

A static variable in Java is a variable that is associated with the class rather than an instance of the class. This means that all instances of the class share the same static variable. They are declared using the static keyword.

public class Example {

    static int count = 0;

    public Example() {

        count++;

    }

}

**Diagram -** The diagram below illustrates the relationship between the class and the static variable:

          +----------+

Example | count=0 |

          +----------+

          | |

Instance1 | |

          +----------+

          | |

Instance2 | |

          +----------+

### 161\. Explain static block

A static block in Java is a block of code that is executed when the class is loaded into memory. Static blocks are enclosed in curly braces and are marked with the static keyword. 

### 162\. Difference between static (class) method and instance method

The main difference between a static method and an instance method in Java is that a static method is associated with the class, while an instance method is associated with an instance of the class. 

### 163\. How can constructor chaining be done using this keyword?

It is the process of calling one constructor from another constructor in the same class. This can be achieved using this keyword.

### 164\. Which class is the superclass for all the classes?

The Object class is the only superclass for all classes in Java.

### 165\. Why are multiple inheritances not supported in Java?

Multiple inheritances are not supported in Java because it can lead to several problems, including the diamond problem and name conflicts. 

### 166\. Why is method overloading not possible by changing the return type in Java?

It is not possible by changing the return type in Java because the return type of a method is not part of its signature.

### 167\. What is method overloading with type promotion?

Method overloading with type promotion in Java is the process of defining multiple methods in the same class with the same name but different parameter types.

### 168\. Can we change the scope of the overridden method in the subclass?

No, we cannot change the scope of the overridden method in the subclass.

### 169\. Can you have virtual functions in Java?

**I**n Java, all non-static methods are virtual functions by default.

### 170\. What is the covariant return type?

The covariant return type is a feature introduced in Java 5 that allows a subclass method to return a type that is a subclass of the return type of the overridden method in the superclass.

### 171\. What is the final variable?

A final variable in Java is a variable that cannot be changed once it is initialized.

### 172\. What is the final method?

A final method in Java is a method that cannot be overridden in a subclass. 

### 173\. What is the final class?

A final class in Java is a class that cannot be subclassed.

### 174\. What is the final blank variable?

The final blank variable in Java is a final variable that is not initialized when it is declared.

### 175\. Difference between the final method and the abstract method

The main difference between a final method and an abstract method in Java is that a final method cannot be overridden in a subclass, while an abstract method must be overridden in a subclass.

### 176\. Differences between Heap and Stack Memory in Java

Heap and Stack are two types of memory in Java used for storing data. Heap memory is used for storing objects, while Stack memory is used for storing local variables and method calls. One of the main differences between Heap and Stack memory is their allocation and deallocation. Heap memory is allocated when an object is created and deallocated when there are no more references to that object. Stack memory, on the other hand, is allocated when a method is called and deallocated when the method returns.

Another difference between Heap and Stack memory is their size. Heap memory is larger than Stack memory because it is used for storing objects. Stack memory is smaller because it is used for storing local variables and method calls only. 

### 177\. What do you understand about an instance variable and a local variable?

Instance variables and local variables are two types of variables in Java. Instance variables are declared inside a class but outside any method. They are used to store data that is specific to an object. Local variables, on the other hand, are declared inside a method and are used to store temporary data that is required only within that method.

One of the main differences between instance variables and local variables is their scope. Instance variables have a larger scope than local variables. The second difference between instance variables and local variables is their initialization. Instance variables are initialized automatically by default values if not initialized explicitly, while local variables must be initialized explicitly before they can be used. 

###  178. What is a JIT Compiler?

JIT (Just-In-Time) compiler is a part of the Java Virtual Machine (JVM) that compiles Java bytecode into native machine code at run time.

### 179\. Can you tell the difference between the equals() method and equality operator (==) in Java?

Equals() method and equality operator (==) are used for comparing objects in Java. However, they differ in their functionality. Equals() method is used to compare the contents of two objects, while the equality operator (==) is used to compare the references of two objects.

When we use the equality operator (==) to compare two objects, it checks if both objects refer to the same memory location. On the other hand, when we use the Equals() method, it checks if the contents of the two objects are equal.

**equals() method**

**equality operator (==)**

In Java, it is a binary operator.

It is a Java.lang public method.Object type.

It can be applied to derived types as well as primitive types

It can only be applied to derived types.

Primitive forms are most suitable for it.

It works best with derived types.

### 180\. What are shallow copy and deep copy in Java?

Shallow copy and deep copy are two types of object copying in Java. SC creates a new object with the same values as the original object, while deep copy creates a new object with new values.

**Shallow copy**

**Deep copy**

There is no new memory allocated, so it is quick

As fresh memory is allocated, the data moves slowly.

A shallow copy costs less money.

Deep copy is very costly.

Changes in one entity have an impact on the other.

Changes in one entity do not have any impact on the other.

### 181\. Does Java work as a "pass by value" or "pass by reference" phenomenon?

Java works as a "pass-by-value" phenomenon. This means that when we pass an object to a method, a copy of the reference to that object is passed, not the actual object.

For example, let's consider the following code:

public void changeValue(int x) {

   x = 5;

}

int num = 10;

changeValue(num);

System.out.println(num);

In this code, we pass the value of num to the changeValue() method. However, when we change the value of x inside the method, it does not affect the value of num outside the method. This is because Java passes a copy of the value of num, not the actual object. 

### 182\. Why Does Java Array Index Start with 0?

In Java, array indexing starts with 0. This is because an array is a contiguous block of memory where each element occupies a fixed amount of space. It is the offset from the start of the array.

Consider the following code:

int\[\] arr = new int\[5\];

arr\[0\] = 10;

arr\[1\] = 20;

arr\[2\] = 30;

arr\[3\] = 40;

arr\[4\] = 50;

In this code, we declare an array of size five and assign values to each element. The index of the first element is coming 0, and the last element index is coming 4, which is the size of the array minus 1. 

### 183\. Can you explain the Java thread lifecycle?

Java thread life cycle consists of several states, including New, Runnable, Blocked, Waiting, Timed Waiting, and Terminated. 

The New State represents a thread that has been created but not started yet. The Runnable state represents a thread that is ready to run but may not be scheduled to run by the operating System. The Blocked state represents a thread that is waiting for a monitor lock to be released. The Waiting state represents a thread that is waiting for another thread to perform a specific action. The Timed Waiting state represents a thread that is waiting for a specific amount of time to elapse. The Terminated state represents a thread that has completed its execution. 

### 184\. What are the possible ways of making objects eligible for garbage collection (GC) in Java? 

In Java, objects are automatically garbage collected when they are no longer referenced. However, we can also make objects eligible for garbage collection manually using the System.gc() method or by setting the object reference to null.

Consider the following code:

MyObject obj = new MyObject();

obj = null;

System.gc();

In this code, we create an object of the MyObject class and then set the object reference to null. We then call the System.gc() method to request the garbage collector to run. 

### 185\. What are the different categories of Java Design patterns?

Java Design Patterns can be categorized into three categories: Creational, Structural, and Behavioral.

Creational patterns are used for creating objects. Some examples of Creational patterns are Singleton, Factory, and Abstract Factory.

Structural patterns are used for assembling objects and creating relationships between them. Some examples of Structural patterns are Adapters, bridges, and Composites.

Behavioral patterns are used for managing algorithms, relationships, and responsibilities between objects. Some examples of Behavioral patterns are Observer, Strategy, and Template Methods. 

### 186\. List the features of the Java Programming language.

Java is a popular programming language that is widely used for developing applications. Some of the features of Java programming language are:

1.  Platform Independence: Java code can run on any platform that has a JVM installed.
2.  Object-Oriented: Java is an object-oriented programming language that supports encapsulation, inheritance, and polymorphism.
3.  Memory Management: Java has automatic memory management, which means that it manages memory allocation and deallocation automatically.
4.  Multithreading: Java supports multithreading, which allows multiple threads to run concurrently.
5.  Security: Java has built-in security features that protect the System from malicious attacks.
6.  Exception Handling: Java has a robust exception-handling mechanism that allows developers to handle errors and exceptions effectively.
7.  Garbage Collection: Java has automatic garbage collection, which means that it automatically frees the memory.
