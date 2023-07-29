
Java Interview Coding Questions For Intermediate
------------------------------------------------

Now, let's have a look at some of the most asked Java technical interview questions for intermediate experienced professionals.

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

In languages like Java, C++, and C#, late binding is achieved using virtual functions (in C++) or method overriding (in Java and C#). When a method is declared as virtual (or overridden) in the base class, the runtime system dynamically dispatches the call to the appropriate method based on the actual type of the object being referenced.

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
