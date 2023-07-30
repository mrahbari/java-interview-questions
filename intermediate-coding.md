
Java Interview Coding Questions For Intermediate
------------------------------------------------

Now, let's have a look at some of the most asked Java technical interview questions for intermediate experienced professionals.

---
### > Why are generics used in Java Programming?

Generics in Java are used to enhance the type safety and reusability of code. They allow you to create classes, interfaces, and methods that can work with different data types while providing compile-time type checking. By using generics, you can write code that is more flexible and less error-prone, as the compiler ensures that the data types used are consistent.

Benefits of using generics:

1. Type safety: With generics, the compiler can catch type-related errors at compile-time, reducing the likelihood of runtime exceptions.
2. Code reusability: Generics allow you to create classes and methods that can be used with various data types, promoting code reuse and eliminating the need for duplicated code.
3. Elimination of casting: Generics eliminate the need for explicit type casting, making the code more concise and readable.
4. Better code documentation: Using generics adds clarity to the code by explicitly stating the types that a class or method is designed to work with.

Sample code demonstrating the use of generics:

Let's create a simple generic class called `Box`, which can store an object of any type:

```java
public class Box<T> {
    private T content;

    public Box(T content) {
        this.content = content;
    }

    public T getContent() {
        return content;
    }

    public void setContent(T content) {
        this.content = content;
    }

    public static void main(String[] args) {
        // Create a Box of Integer
        Box<Integer> intBox = new Box<>(10);
        int value = intBox.getContent();
        System.out.println("Integer value: " + value);

        // Create a Box of String
        Box<String> stringBox = new Box<>("Hello, Generics!");
        String message = stringBox.getContent();
        System.out.println("String content: " + message);
    }
}
```

In the example above, we have a generic class `Box`, which can be instantiated with different types (`T`). We create instances of `Box` with different data types (Integer and String), and the compiler ensures type safety by performing type checking at compile-time.

Without generics, we might have to use a non-generic Object type for the content, which would require casting and increase the risk of runtime errors:

```java
public class NonGenericBox {
    private Object content;

    public NonGenericBox(Object content) {
        this.content = content;
    }

    public Object getContent() {
        return content;
    }

    public void setContent(Object content) {
        this.content = content;
    }

    public static void main(String[] args) {
        NonGenericBox intBox = new NonGenericBox(10);
        int value = (int) intBox.getContent(); // Requires casting
        System.out.println("Integer value: " + value);

        NonGenericBox stringBox = new NonGenericBox("Hello, Generics!");
        String message = (String) stringBox.getContent(); // Requires casting
        System.out.println("String content: " + message);
    }
}
```

As you can see, the non-generic version involves casting and lacks the safety and clarity provided by generics.

---
### > What is the difference between JDK, JRE, and JVM?

JVM has a Just in Time (JIT) compiler tool that converts all the Java source code into the low-level compatible machine language. Therefore, it runs faster than the regular application.

JRE has class libraries and other JVM supporting files. But it doesn’t have any tool for java development such as compiler or debugger.

JDK has tools that are required to write Java Programs and uses JRE to execute them. It has a compiler, Java application launcher, and an applet viewer.

---
### > What is a JIT compiler?

JIT compiler refers to Just in Time compiler. It is the simplest way of executing the computer code that takes in compilation during the execution of a program rather than before performance. It commonly uses bytecode translation to machine code. It is then executed directly.

---
### > What are Brief Access Specifiers and Types of Access Specifiers?

Access Specifiers are predefined keywords used to help JVM understand the scope of a variable, method, and class. We have four access specifiers.
*   Public Access Specifier 
*   Private Access Specifier 
*   Protected Access Specifier 
*   Default Access Specifier

---
### > How many types of constructors are used in Java?

In Java, there are three types of constructors that can be used to initialize objects of a class:
1. Default Constructor:
   - A default constructor is automatically provided by Java if no constructors are explicitly defined in the class.
   - It has no parameters and does not take any arguments.
   - The default constructor initializes the object with default values for instance variables (e.g., numeric fields set to 0, object references set to null, etc.).

Example of a class with a default constructor:

```java
public class Person {
    private String name;
    private int age;

    // Default constructor (automatically provided if not explicitly defined)
    public Person() {
        // No parameters or arguments
        // Initializes name and age to default values (null and 0, respectively)
    }

    // Other methods and constructors can be defined here
}
```

2. Parameterized Constructor:
   - A parameterized constructor is a constructor that takes one or more parameters to initialize the object's instance variables with the provided values.
   - It allows you to provide specific values to the object's fields during object creation.
   - You can have multiple parameterized constructors with different sets of parameters.

Example of a class with a parameterized constructor:

```java
public class Car {
    private String make;
    private String model;
    private int year;

    // Parameterized constructor with three parameters
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Other methods and constructors can be defined here
}
```

3. Copy Constructor:
   - A copy constructor is a constructor that takes an object of the same class as a parameter and creates a new object with the same values as the provided object.
   - It is useful when you want to create a new object that is a deep copy of an existing object.

Example of a class with a copy constructor:

```java
public class Student {
    private String name;
    private int age;

    // Parameterized constructor
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Copy constructor that takes an object of the same class as a parameter
    public Student(Student otherStudent) {
        this.name = otherStudent.name;
        this.age = otherStudent.age;
    }

    // Other methods and constructors can be defined here
}
```

---
### > Can a constructor return a value?

Yes, A constructor can return a value. It replaces the class's current instance implicitly; you cannot make a constructor return a value explicitly.

In Java, constructors do not have a return type, including `void`. This means constructors cannot return a value explicitly like regular methods do. The primary purpose of a constructor is to initialize the object's state and allocate memory for it.

When you create an instance of a class using the `new` keyword, a constructor is automatically called to initialize the object. The constructor initializes the instance variables of the object to their default values (e.g., numeric fields to 0, object references to null, etc.) or to the values provided in the constructor parameters.

For example, consider the following class with a constructor:

```java
public class Person {
    private String name;
    private int age;

    // Constructor with parameters
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```
In this example, the `Person` class has a constructor with two parameters, `name` and `age`. When you create a `Person` object using this constructor, it will initialize the `name` and `age` instance variables with the values provided in the constructor parameters.

```java
Person person = new Person("John", 30);
```
In this case, the constructor does not return any value explicitly. Instead, it initializes the `person` object's `name` and `age` fields with "John" and `30`, respectively.

If you need to get specific values after object creation, you can use getter methods to retrieve the values of instance variables. However, the constructor itself does not return any value. Its purpose is solely to initialize the object's state.

---
### > Explain ‘this’ keyword in Java.

The term "this" is a particular keyword designated as a reference keyword. The "this" keyword is used to refer to the current class properties like method, instance, variable, and constructors.

---
### > Explain ‘super’ keyword in Java.

The term "super" is a particular keyword designated as a reference keyword. The "super" keyword refers to the immediate parent class object.

---
### > Explain Method Overloading in Java.

The process of creating multiple method signatures using one method name is called Method Overloading in Java. Two ways to achieve method overloading are:

1.  Varying the number of arguments
2.  Changing the return type of the Method 

Method overloading in Java allows you to define multiple methods with the same name but different parameter lists within the same class. The methods can have different types or numbers of parameters. Java determines which method to call based on the number or types of arguments passed during the method invocation. Here's a sample code to illustrate method overloading:

```java
public class MathOperations {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method to add two doubles
    public double add(double a, double b) {
        return a + b;
    }

    // Method to concatenate two strings
    public String add(String str1, String str2) {
        return str1 + str2;
    }

    // Main method to test the overloaded methods
    public static void main(String[] args) {
        MathOperations mathOps = new MathOperations();

        int result1 = mathOps.add(10, 20);
        int result2 = mathOps.add(5, 10, 15);
        double result3 = mathOps.add(3.5, 2.7);
        String result4 = mathOps.add("Hello", " World");

        System.out.println("Result 1: " + result1);
        System.out.println("Result 2: " + result2);
        System.out.println("Result 3: " + result3);
        System.out.println("Result 4: " + result4);
    }
}
```
In the `main` method, we create an instance of the `MathOperations` class and test each of the overloaded `add` methods with different sets of arguments. The program will output:

```
Result 1: 30
Result 2: 30
Result 3: 6.2
Result 4: Hello World
```
As you can see, Java selects the appropriate `add` method based on the number and types of arguments passed to it, allowing us to perform different operations with the same method name. This is the concept of method overloading in Java.
```
---
### Write a sample of ‘super’ keyword in Java?
```java
class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }

    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    String breed;

    Dog(String name, String breed) {
        super(name); // Call the constructor of the superclass (Animal) with the 'name' parameter
        this.breed = breed;
    }

    void makeSound() {
        super.makeSound(); // Call the makeSound() method of the superclass (Animal)
        System.out.println("Dog barks");
    }

    void displayDetails() {
        System.out.println("Name: " + super.name); // Access the 'name' variable of the superclass (Animal)
        System.out.println("Breed: " + breed);
    }
}

public class SuperKeywordExample {
    public static void main(String[] args) {
        Dog dog = new Dog("Buddy", "Labrador");
        dog.makeSound();
        dog.displayDetails();
    }
}
```

---
### > Can we overload a static method?
Yes, in Java, you can overload static methods just like you can overload instance methods. Method overloading allows you to define multiple methods with the same name within the same class, but with different parameter lists.

When you overload a static method, Java determines which version of the method to call based on the number or types of arguments passed during the method invocation. The decision is made at compile-time, depending on the method's signature.

Here's an example of overloading a static method:

```java
public class MathOperations {
    // Static method to add two integers
    public static int add(int a, int b) {
        return a + b;
    }

    // Static method to add three integers
    public static int add(int a, int b, int c) {
        return a + b + c;
    }

    // Static method to add two doubles
    public static double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result1 = MathOperations.add(10, 20);
        int result2 = MathOperations.add(5, 10, 15);
        double result3 = MathOperations.add(3.5, 2.7);

        System.out.println("Result 1: " + result1);
        System.out.println("Result 2: " + result2);
        System.out.println("Result 3: " + result3);
    }
}
```

In this example, we have a class `MathOperations` with three overloaded static `add` methods. The methods are overloaded based on the number and types of arguments they accept.

In the `main` method, we call each of the static `add` methods with different sets of arguments. The output will be:
```
Result 1: 30
Result 2: 30
Result 3: 6.2
```
As you can see, Java correctly selects the appropriate static `add` method based on the number and types of arguments passed, allowing us to perform different operations with the same method name. This demonstrates that static methods can be overloaded in Java.

---
### > Define Late Binding.

Binding is a process of unifying the method call with the method's code segment. Late binding happens when the method's code segment is unknown until it is called during the runtime. 

Late binding, also known as dynamic binding or runtime polymorphism, is a feature in object-oriented programming languages where the actual method or function to be called is determined at runtime rather than compile-time. This enables the program to make decisions about method calls based on the actual type of the object being referenced.

Late binding is typically associated with inheritance and polymorphism. It occurs when a class has one or more methods that are declared in the superclass and overridden (redefined) in one or more of its subclasses. The decision about which version of the method to call is deferred until runtime when the actual object type is known.

The late binding mechanism allows for more flexibility and extensibility in the code, as it allows different subclasses to provide their own implementations of the same method. This enables polymorphism, where a reference variable of a superclass type can be used to refer to objects of various subclasses, and the appropriate method is called based on the actual object type at runtime.

Here's a simple Java example to illustrate late binding:

```java
class Shape {
    void draw() {
        System.out.println("Drawing a shape.");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle.");
    }
}

class Square extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a square.");
    }
}

public class LateBindingExample {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Square();

        shape1.draw(); // Calls the draw() method of Circle (late binding)
        shape2.draw(); // Calls the draw() method of Square (late binding)
    }
}
```

In this example, we have a base class `Shape` with a method `draw()`. The `Circle` and `Square` classes are subclasses of `Shape` that override the `draw()` method with their own implementations.

In the `main` method, we create objects of `Circle` and `Square` and assign them to references of type `Shape`. When we call the `draw()` method on these references, the appropriate method implementation is determined at runtime based on the actual object type. This is an example of late binding or runtime polymorphism.

---
### > Define Dynamic Method Dispatch.

The Dynamic method dispatch is a process where the method call is executed during the runtime. A reference variable is used to call the super-class. This process is also known as Run-Time Polymorphism.   

Dynamic Method Dispatch in Java refers to the mechanism by which the appropriate method implementation is determined at runtime, based on the actual object type rather than the reference type. It is an essential feature of polymorphism in object-oriented programming.

Example:

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Dog();
        Animal animal2 = new Cat();

        animal1.makeSound(); // Output: Dog barks
        animal2.makeSound(); // Output: Cat meows
    }
}
```

In the example above, we have a base class `Animal` and two derived classes `Dog` and `Cat`. Each derived class overrides the `makeSound()` method. During runtime, when we create instances of `Dog` and `Cat`, and call the `makeSound()` method through the base class reference (`Animal`), the appropriate method implementation from the actual object type (either `Dog` or `Cat`) is executed. This is dynamic method dispatch in action.

---
### > Why is the delete function faster in the linked list than an array?

Delete Function is faster in linked lists in Java as the user needs to make a minor update to the pointer value so that the node can point to the next successor in the list

---
### > Give a briefing on the life cycle of a thread.

The life cycle of a thread includes five stages, as mentioned below.

1.  New Born State
2.  Runnable State
3.  Running State
4.  Blocked State
5.  Dead State
```java
public class ThreadLifecycleExample {

    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            System.out.println("Thread is running");
            try {
                Thread.sleep(2000); // Simulating some task execution
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("Thread has finished");
        });

        System.out.println("Thread State: " + thread.getState()); // New

        thread.start();
        System.out.println("Thread State: " + thread.getState()); // Runnable

        try {
            Thread.sleep(500); // Give some time for the thread to start
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Thread State: " + thread.getState()); // Running

        try {
            thread.join(); // Wait for the thread to finish
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Thread State: " + thread.getState()); // Dead
    }
}
```

---
### > Explain the difference between >> and >>> operators.

Although they look similar, there is a massive difference between both.

*   \>> operator does the job of right shifting the sign bits. The leftmost bit (the sign bit) is used as the fill bit
*   \>>> operator is used in shifting out the zero-filled bits. The leftmost bit with 0.
```java
int num = -10; // Binary representation: 11111111 11111111 11111111 11110110
int result = num >> 2;
System.out.println(result); // Output: -3 (Binary representation: 11111111 11111111 11111111 11111101)
```
```java
int num = -10; // Binary representation: 11111111 11111111 11111111 11110110
int result = num >>> 2;
System.out.println(result); // Output: 1073741821 (Binary representation: 00111111 11111111 11111111 11111101)
```

---
### > Explain the Externalizable interface.

The `Externalizable` interface in Java is used for customizing the serialization and deserialization process of objects. Unlike the `Serializable` interface, which performs automatic serialization and deserialization, the `Externalizable` interface requires you to explicitly define how an object should be written to and read from a stream.

To implement the `Externalizable` interface, a class must provide implementations for two methods: `writeExternal()` for serialization and `readExternal()` for deserialization.

Note that the `Externalizable` interface requires you to handle the entire serialization and deserialization process manually, including any additional members in the class that need to be serialized or deserialized. It provides greater flexibility but requires more effort compared to the automatic serialization provided by the `Serializable` interface.

Here's a sample code demonstrating the usage of the `Externalizable` interface:

```java
import java.io.*;

class Person implements Externalizable {
    private String name;
    private int age;

    // A no-argument constructor is required for Externalizable
    public Person() {}

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public void writeExternal(ObjectOutput out) throws IOException {
        // Custom serialization logic
        out.writeObject(name);
        out.writeInt(age);
    }

    @Override
    public void readExternal(ObjectInput in) throws IOException, ClassNotFoundException {
        // Custom deserialization logic
        name = (String) in.readObject();
        age = in.readInt();
    }

    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + "]";
    }
}

public class ExternalizableExample {
    public static void main(String[] args) {
        try {
            // Serialize the object
            Person person = new Person("John", 30);
            FileOutputStream fileOut = new FileOutputStream("person.ser");
            ObjectOutputStream out = new ObjectOutputStream(fileOut);
            out.writeObject(person);
            out.close();
            fileOut.close();

            System.out.println("Object has been serialized.");

            // Deserialize the object
            FileInputStream fileIn = new FileInputStream("person.ser");
            ObjectInputStream in = new ObjectInputStream(fileIn);
            Person deserializedPerson = (Person) in.readObject();
            in.close();
            fileIn.close();

            System.out.println("Object has been deserialized:");
            System.out.println(deserializedPerson);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

In the example above, we have a `Person` class that implements the `Externalizable` interface. We override the `writeExternal()` and `readExternal()` methods to define our custom serialization and deserialization logic. When the `Person` object is serialized to a file using `ObjectOutputStream`, the `writeExternal()` method is called, and when it is deserialized using `ObjectInputStream`, the `readExternal()` method is called. This way, we have full control over the serialization and deserialization process.

---
### > What is the Daemon Thread?

In Java, a daemon thread is a special type of thread that runs in the background and provides a supporting role to other non-daemon threads. The main characteristic of a daemon thread is that it does not prevent the Java Virtual Machine (JVM) from exiting when all non-daemon threads have finished their execution. In other words, the JVM can terminate if only daemon threads are running.

Daemon threads are typically used for tasks that do not require the program to wait for their completion. They are often used for services, maintenance, or background tasks that should run as long as the program is running but are not critical to the application's main functionality.

Key points about daemon threads:
1. They are created by setting the thread's `setDaemon(true)` method to `true` before starting the thread.
2. Daemon threads inherit the priority of the thread that created them unless explicitly set.
3. Daemon threads are automatically terminated when there are no more non-daemon threads running.
4. They should not be used for tasks that involve critical operations, such as writing to files or database management, as they can be abruptly terminated when the JVM exits.

Here's a simple example of creating a daemon thread in Java:

```java
public class DaemonThreadExample {
    public static void main(String[] args) {
        Thread daemonThread = new Thread(() -> {
            while (true) {
                System.out.println("Daemon thread is running");
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        daemonThread.setDaemon(true); // Set the thread as daemon
        daemonThread.start();

        // Main thread sleeps for a while to observe the daemon thread running
        try {
            Thread.sleep(5000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Main thread is done");
    }
}
```

In this example, we create a daemon thread that prints a message every second. Since the main thread sleeps for 5 seconds, we can observe the daemon thread running for that period. When the main thread is done, the JVM exits, and the daemon thread is terminated without completing its iteration.

Note that the exact behavior of daemon threads can be platform-dependent and may vary in different Java Virtual Machine implementations.

---
### > Explain the term enumeration in Java.
In Java, an enumeration (often referred to as an "enum") is a special data type that represents a fixed set of constant values. It is a collection of named constants, where each constant represents a unique symbolic value within the enumeration. Enumerations provide a way to define a set of related constants as a single data type, making the code more readable, type-safe, and maintainable.

Key characteristics of enumerations in Java:

1. Constants with Meaningful Names: Each constant in an enumeration is assigned a meaningful name, which helps in improving code readability and understanding.

2. Type-Safety: Enumerations are type-safe, meaning that the compiler ensures that you can only use valid enumeration constants for the defined enum type.

3. Fixed Set of Values: The set of constants defined within an enumeration is fixed during the program's execution. You cannot add or remove elements from an enumeration at runtime.

4. Instances of Enumeration Constants: Each constant defined within an enumeration is an instance of the enum type.

5. Comparable: Enumerations implement the `java.lang.Comparable` interface, which allows for sorting and comparison operations.

Here's an example of how to define and use an enumeration in Java:

```java
enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

public class EnumExample {
    public static void main(String[] args) {
        Day today = Day.TUESDAY;

        // Using switch-case with enum
        switch (today) {
            case SUNDAY:
                System.out.println("Today is Sunday");
                break;
            case MONDAY:
                System.out.println("Today is Monday");
                break;
            case TUESDAY:
                System.out.println("Today is Tuesday");
                break;
            // ... other cases ...
            default:
                System.out.println("Today is some other day");
        }

        // Enum iteration
        System.out.println("All days of the week:");
        for (Day day : Day.values()) {
            System.out.println(day);
        }

        // Using enum in a method
        printDayName(today);
    }

    public static void printDayName(Day day) {
        switch (day) {
            case SUNDAY:
                System.out.println("Day name: Sunday");
                break;
            case MONDAY:
                System.out.println("Day name: Monday");
                break;
            case TUESDAY:
                System.out.println("Day name: Tuesday");
                break;
            // ... other cases ...
            default:
                System.out.println("Unknown day");
        }
    }
}
```
---
### > Why is Java is Dynamic?
Java is often considered a dynamic language due to several features that allow it to exhibit dynamic behavior during runtime. Some of the reasons why Java is considered dynamic are as follows:

1. Reflection: Java provides a powerful reflection API that allows programs to inspect and modify the structure, behavior, and attributes of classes and objects during runtime. Reflection enables dynamic loading of classes, introspection, and the ability to invoke methods dynamically based on runtime information.

2. Runtime Polymorphism: Java supports polymorphism, which allows a variable of a superclass type to hold an object of any subclass type. The actual method implementation to be called is determined dynamically at runtime based on the actual object type, a characteristic of dynamic binding.

3. Late Binding: Java uses late binding or dynamic binding for method invocations. During runtime, the JVM determines the actual method to be executed based on the type of the object, allowing for flexibility and polymorphic behavior.

4. Dynamic Class Loading: Java supports dynamic class loading, enabling programs to load classes at runtime from external sources like JAR files or network locations. This feature allows for dynamic extensibility and adaptability of Java applications.

5. Dynamic Arrays and Collections: Java provides dynamic data structures like ArrayList, LinkedList, HashMap, etc., which can dynamically change in size at runtime based on the elements they hold.

6. Dynamic Memory Allocation: In Java, objects are allocated memory dynamically on the heap during runtime, and the memory management is handled by the Java Virtual Machine (JVM).

7. Dynamic Exception Handling: Java allows the handling of exceptions during runtime, providing the ability to react to various error conditions at runtime and take appropriate actions.

8. Dynamic Input and Output: Java provides dynamic input/output capabilities through streams, which allow reading and writing data from/to various sources, like files, network connections, or memory buffers, at runtime.

While Java is dynamic in several aspects, it is essential to note that it is primarily considered a statically-typed language since type checking is performed at compile-time. The dynamic features of Java mainly come into play during runtime, providing flexibility, adaptability, and the ability to work with unknown or changing data and structures.


### > Can you run a code before executing the main method?
Yes, you can execute code before the `main` method in Java using a static initializer block or static fields of a class. These static elements are executed when the class is loaded into memory, which happens before the `main` method is called.

Here's an example to demonstrate code execution before the `main` method:

```java
public class CodeBeforeMain {
    // Static field
    static int someValue = initialize();

    // Static initializer block
    static {
        System.out.println("Code executed in static initializer block");
    }

    // Static method
    static int initialize() {
        System.out.println("Code executed in static method");
        return 42;
    }

    public static void main(String[] args) {
        System.out.println("Inside the main method");
    }
}
```

When you run the above code, the output will be:

```
Code executed in static method
Code executed in static initializer block
Inside the main method
```

As you can see, the static method `initialize` and the static initializer block are executed before the `main` method is called. This behavior allows you to perform necessary setup tasks or configurations before the main logic of your program executes.

---
### > How many times is the finalize method called?

The finalize method is called the Garbage collector. For every object, the Garbage Collector calls the finalize() method just for one time.

