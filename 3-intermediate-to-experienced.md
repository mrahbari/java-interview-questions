
Java Interview Questions for Experienced
----------------------------------------

Now, lets move on to our last section of Advanced Core Java Interview Questions which is primarly useful for experienced and working professionals.

### > Can "this" and "super" keywords be used together?

No, the `this` and `super` keywords cannot be used together in Java. They have distinct and separate purposes in the context of object-oriented programming.

1. `this`: The `this` keyword refers to the current instance of the class. It is used to differentiate between instance variables and local variables when they have the same name, as well as to invoke other constructors of the same class within one constructor.

Example:
```java
class MyClass {
    private int x;

    public MyClass(int x) {
        this.x = x; // Use "this" to refer to the instance variable "x"
    }
}
```

2. `super`: The `super` keyword refers to the superclass (i.e., the parent class) of the current class. It is used to call the superclass's constructor or to access members of the superclass that are hidden or overridden by the subclass.

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
        super.makeSound(); // Call the overridden method in the superclass
        System.out.println("Dog barks");
    }
}
```

In the above example, the `super.makeSound()` call is used to invoke the `makeSound()` method from the superclass (`Animal`) before adding additional behavior specific to the subclass (`Dog`).

You cannot use `this` and `super` together because their functionalities are different and do not overlap. Attempting to do so would result in a compilation error.


---
### > What is JDBC?

JDBC is an abstraction layer used to establish connectivity between an existing database and a Java application

JDBC stands for "Java Database Connectivity." It is a Java API (Application Programming Interface) that provides a standard way for Java programs to interact with relational databases. JDBC enables Java applications to perform database operations such as connecting to databases, executing SQL queries, updating and retrieving data, and managing database transactions.

Key features and components of JDBC:

1. **Driver Manager:** JDBC includes the `DriverManager` class, which manages the database drivers. It provides methods to register and get a connection to a specific database.

2. **Database Drivers:** JDBC drivers are software components that implement the JDBC API for a particular database. There are four types of JDBC drivers: Type 1 (JDBC-ODBC Bridge), Type 2 (Native-API), Type 3 (Network Protocol), and Type 4 (Pure Java).

3. **Connection:** The `Connection` interface represents a connection to a database. It is obtained using the `DriverManager.getConnection()` method and is used to perform database operations.

4. **Statement:** The `Statement` interface is used to execute SQL queries and updates on the database. There are three types of statements: `Statement` (for general SQL queries), `PreparedStatement` (for parameterized queries), and `CallableStatement` (for executing stored procedures).

5. **ResultSet:** The `ResultSet` interface represents the result of a query and provides methods to retrieve data from the database.

6. **SQL Exceptions:** JDBC methods throw `SQLException` in case of database-related errors, and handling these exceptions is essential in JDBC programming.

Using JDBC, Java developers can create database-driven applications, perform CRUD (Create, Read, Update, Delete) operations, and work with the data stored in relational databases like MySQL, Oracle, PostgreSQL, SQL Server, etc.

Here's a simple example of using JDBC to connect to a database and execute a query:

```java
import java.sql.*;

public class JDBCSample {
    public static void main(String[] args) {
        try {
            // Load the JDBC driver (type 4)
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Create a connection to the database
            String url = "jdbc:mysql://localhost:3306/mydatabase";
            String username = "myuser";
            String password = "mypassword";
            Connection connection = DriverManager.getConnection(url, username, password);

            // Create a statement and execute a query
            Statement statement = connection.createStatement();
            String query = "SELECT * FROM employees";
            ResultSet resultSet = statement.executeQuery(query);

            // Process the result set
            while (resultSet.next()) {
                int id = resultSet.getInt("id");
                String name = resultSet.getString("name");
                double salary = resultSet.getDouble("salary");
                System.out.println("Employee ID: " + id + ", Name: " + name + ", Salary: " + salary);
            }

            // Close the resources
            resultSet.close();
            statement.close();
            connection.close();
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }
    }
}
```

Please note that in a real application, you should use try-with-resources or properly close the resources in the `finally` block to ensure proper resource management.

---
### > What are the observer and observable classes?

In Java, the Observer pattern is a behavioral design pattern that allows one object (the "subject" or "observable") to notify multiple dependent objects (the "observers") of any state changes it undergoes. The Observer pattern helps to establish a one-to-many dependency between objects, where the observers automatically update their state when the subject changes.

To implement the Observer pattern in Java, there are two main classes involved:

1. **Observable class (Subject):**
The `Observable` class is a part of the Java Standard Library (`java.util` package). It serves as the subject that maintains a list of observers and notifies them when a state change occurs. The `Observable` class provides methods to manage the list of observers and notify them of changes using the `notifyObservers()` method.

2. **Observer interface (Observer):**
The `Observer` interface is also part of the Java Standard Library (`java.util` package). It represents the observer objects that receive notifications from the `Observable` class. The `Observer` interface has a single method called `update(Observable o, Object arg)` that is called when the observed object (`Observable`) changes its state.

The Observer pattern is widely used in event-driven programming and user interfaces (e.g., graphical user interfaces), where changes in one part of the application need to be reflected in other parts.

Here's a simplified example of how to use `Observable` and `Observer` in Java:

```java
import java.util.Observable;
import java.util.Observer;

// Subject (Observable) class
class WeatherStation extends Observable {
    private int temperature;

    public void setTemperature(int temperature) {
        this.temperature = temperature;
        setChanged(); // Mark the object as changed
        notifyObservers(temperature); // Notify the observers with the new temperature
    }
}

// Observer class
class TemperatureDisplay implements Observer {
    @Override
    public void update(Observable o, Object arg) {
        int temperature = (int) arg;
        System.out.println("Temperature Display: " + temperature + " degrees Celsius");
    }
}

public class ObserverPatternExample {
    public static void main(String[] args) {
        WeatherStation weatherStation = new WeatherStation();
        TemperatureDisplay temperatureDisplay = new TemperatureDisplay();

        // Add the observer to the observable
        weatherStation.addObserver(temperatureDisplay);

        // Simulate a change in temperature
        weatherStation.setTemperature(25);
    }
}
```

In this example, `WeatherStation` is the `Observable` class that represents the subject, and `TemperatureDisplay` is the `Observer` class that represents the observer. When the temperature changes in the `WeatherStation`, it notifies the `TemperatureDisplay`, which then updates its display with the new temperature.

---
### > What is Session Management in Java?

A session is essentially defined as the random conversation's dynamic state between the client and the server. The virtual communication channel includes a string of responses and requests from both sides. The popular way of implementing session management is establishing a session ID in the client's communicative discourse and the server.
```java
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

@WebServlet("/storeName")
public class NameServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        // Get the name entered by the user
        String name = request.getParameter("name");

        // Get the session or create a new one if it doesn't exist
        HttpSession session = request.getSession(true);

        // Store the name in the session
        session.setAttribute("userName", name);

        // Get the name stored in the session
        //String name = (String) session.getAttribute("userName");

        // Redirect the user to a new page to display the name
        response.sendRedirect("displayName");
    }
}
```


---
### > Briefly explain the term Spring Framework.

The Spring Framework is a powerful and widely-used open-source application framework for building enterprise-level Java applications. It provides a comprehensive programming and configuration model that simplifies the development of robust and flexible applications.

Key features of the Spring Framework include:

1. **Dependency Injection (DI):** Spring promotes the principle of Inversion of Control (IoC) by handling the creation and management of objects (beans) and their dependencies. Instead of manually creating and wiring components, Spring automatically injects the required dependencies into objects, reducing coupling and enhancing modularity.

2. **Aspect-Oriented Programming (AOP):** Spring supports AOP, allowing developers to separate cross-cutting concerns (e.g., logging, security, transaction management) from the business logic. AOP enables the modularization of such concerns, making the codebase more maintainable.

3. **Enterprise Integration:** Spring offers integrations with various enterprise technologies, such as data access frameworks (e.g., JDBC, JPA, Hibernate), messaging systems (e.g., JMS), and other frameworks like Quartz for scheduling tasks.

4. **Web Development Support:** Spring provides features to build web applications efficiently. It includes the Spring Web MVC module, which offers a flexible and powerful model-view-controller framework for web development.

5. **Transaction Management:** Spring provides a transaction management abstraction that supports both programmatic and declarative transaction management. It simplifies working with transactions in a consistent and scalable manner.

6. **Security:** Spring Security is a part of the Spring ecosystem and provides comprehensive security features to secure applications, including authentication, authorization, and protection against common security vulnerabilities.

7. **Testing:** Spring's test framework supports unit and integration testing of Spring applications. It provides tools to write test cases for Spring components easily.

8. **Extensibility:** Spring is highly extensible, allowing developers to plug in additional modules or frameworks, making it suitable for various types of applications.

The Spring Framework promotes best practices, encourages loosely coupled and modular design, and enhances developer productivity. It has become a de facto standard in the Java ecosystem for building enterprise-level applications, from small-scale projects to large-scale, mission-critical systems.

---
### > How to handle exceptions in Spring MVC Framework?

Spring MVC has two approaches for handling the exceptions:

*   Exception handler method: In this kind of exception handling, the user will get the @ExceptionHandler annotation type used to annotate a method to handle exceptions.
*   XML Configuration: The user can use the SimpleMappingExceptionResolver bean in Spring’s application file and map the exception.

---
### > What is JCA in Java?

JCA stands for Java Cryptography Architecture. It is a framework provided by Java to enable developers to integrate cryptographic services into their applications securely. JCA allows seamless integration of various cryptographic algorithms, providers, and services, making it easier for developers to implement encryption, decryption, digital signatures, message authentication codes (MAC), and other cryptographic operations.

Here's a brief overview along with a sample code of how JCA can be used in Java:

**1. Key Components of JCA:**

a. **Providers:** Providers are implementations of cryptographic algorithms and services. Java comes with a default provider (the "SunJCE" provider) that offers various algorithms. However, developers can add other third-party providers or implement custom providers to support additional algorithms.

b. **Security API:** The `java.security` package contains classes and interfaces that form the foundation of the JCA.

c. **Service Providers Interface (SPI):** JCA uses the SPI mechanism to allow providers to register their services in a dynamic and pluggable way.

**2. Sample Code:**

Below is a simple Java code that demonstrates using JCA for encryption and decryption using the AES algorithm:

```java
import javax.crypto.Cipher;
import javax.crypto.KeyGenerator;
import javax.crypto.SecretKey;
import java.nio.charset.StandardCharsets;
import java.util.Base64;

public class JCAExample {
    public static void main(String[] args) throws Exception {
        String plainText = "Hello, JCA!"; // The text to be encrypted

        // Generate a secret key for AES encryption
        KeyGenerator keyGenerator = KeyGenerator.getInstance("AES");
        keyGenerator.init(128); // 128-bit key size
        SecretKey secretKey = keyGenerator.generateKey();

        // Create a cipher instance for AES encryption
        Cipher cipher = Cipher.getInstance("AES/ECB/PKCS5Padding");
        cipher.init(Cipher.ENCRYPT_MODE, secretKey);

        // Encrypt the plain text
        byte[] encryptedText = cipher.doFinal(plainText.getBytes(StandardCharsets.UTF_8));

        // Print the encrypted text
        System.out.println("Encrypted Text: " + Base64.getEncoder().encodeToString(encryptedText));

        // Now let's decrypt the encrypted text
        cipher.init(Cipher.DECRYPT_MODE, secretKey);
        byte[] decryptedText = cipher.doFinal(encryptedText);

        // Print the decrypted text
        System.out.println("Decrypted Text: " + new String(decryptedText, StandardCharsets.UTF_8));
    }
}
```

In this example, we use the AES algorithm for encryption and decryption. We generate a secret key using the `KeyGenerator` class, create a `Cipher` instance for AES, and then use it to encrypt the plaintext. We print the encrypted text and then decrypt it back to the original plaintext. The `Base64` class is used to encode the binary data to a printable string representation.

---
### > Explain JPA in Java.

The Java Persistence API enables us to create the persistence layer for desktop and web applications. Java Persistence deals in the following:

1.  Java Persistence API
2.  Query Language
3.  Java Persistence Criteria API
4.  Object Mapping Metadata

```java
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Product {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private double price;

    // Getters and setters, constructors, etc.
}
```

```java
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

public class JpaExample {
    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("my-persistence-unit");
        EntityManager em = emf.createEntityManager();

        Product product = new Product();
        product.setName("Example Product");
        product.setPrice(19.99);

        EntityTransaction transaction = em.getTransaction();
        transaction.begin();
        em.persist(product);
        transaction.commit();

        em.close();
        emf.close();
    }
}
```

---
### > Explain the FailFast iterator and FailSafe iterator along with examples for each.

FailFast iterators and FailSafe iterators are used in Java Collections. 

FailFast iterators do not allow changes or modifications to the Java Collections, which means they fail when the latest element is added to the collection or an existing element gets removed from the collection. The FailFast iterators tend to fail and throw an exception called ConcurrentModificationException.

Ex: ArrayList, HashMap

Whereas, on the other hand, FailSafe iterators allow changes or modifications to be done on the Java Collections. It is possible, as the FailSafe iterators usually operate on the cloned copy of the collection. Hence, they do not throw any specific exception.

Ex: CopyOnWriteArrayList

**Example of Fail-Fast Iterator:**
```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class FailFastIteratorExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("apple");
        list.add("banana");
        list.add("orange");

        Iterator<String> iterator = list.iterator();

        while (iterator.hasNext()) {
            String fruit = iterator.next();
            System.out.println(fruit);

            // This line will throw ConcurrentModificationException
            list.remove(fruit);
        }
    }
}
```

**Example of Fail-Safe Iterator:**

```java
import java.util.Iterator;
import java.util.concurrent.ConcurrentHashMap;

public class FailSafeIteratorExample {
    public static void main(String[] args) {
        ConcurrentHashMap<Integer, String> map = new ConcurrentHashMap<>();
        map.put(1, "one");
        map.put(2, "two");
        map.put(3, "three");

        Iterator<Integer> iterator = map.keySet().iterator();

        while (iterator.hasNext()) {
            Integer key = iterator.next();
            System.out.println(key + ": " + map.get(key));

            // Safe to modify the map while iterating
            map.put(4, "four");
        }
    }
}
```
In summary, Fail-Fast iterators quickly detect any concurrent modifications to the collection and raise exceptions to avoid potential data corruption, while Fail-Safe iterators work on a copied version of the collection and continue iterating without any exceptions even if the collection is modified. The choice between Fail-Fast and Fail-Safe iterators depends on the specific use case and the desired behavior of the iterator in concurrent scenarios.

---
### > How do we reverse a string?

```java
public class StringReversal {
    public static String reverseString(String str) {
        StringBuilder reversedString = new StringBuilder();
        for (int i = str.length() - 1; i >= 0; i--) {
            reversedString.append(str.charAt(i));
        }
        return reversedString.toString();
    }

    public static void main(String[] args) {
        String originalString = "Hello, World!";
        String reversedString = reverseString(originalString);
        System.out.println("Original String: " + originalString);
        System.out.println("Reversed String: " + reversedString);
    }
}
```

---
### > Write a program to find the square root of a number.

```java
import java.util.Scanner;

public class SquareRootFinder {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number to find its square root: ");
        double number = scanner.nextDouble();
        
        if (number < 0) {
            System.out.println("Cannot find the square root of a negative number.");
        } else {
            double squareRoot = Math.sqrt(number);
            System.out.println("Square root of " + number + " is: " + squareRoot);
        }
        
        scanner.close();
    }
}
```

Expected Output:
Input a number to find square root: 25
The square root is: 5

---
### > Write a program that detects duplicate characters in a string.

```java
import java.util.HashMap;
import java.util.Map;

public class DuplicateCharacterDetector {
    public static void main(String[] args) {
        String inputString = "Hello, World!";
        Map<Character, Integer> charFrequencyMap = new HashMap<>();

        // Convert the string to lowercase to make the detection case-insensitive
        inputString = inputString.toLowerCase();

        // Loop through each character in the input string
        for (char ch : inputString.toCharArray()) {
            // Ignore non-alphabetic characters and spaces
            if (Character.isAlphabetic(ch)) {
                // If the character is already present in the map, increment its frequency
                // Otherwise, add it to the map with a frequency of 1
                charFrequencyMap.put(ch, charFrequencyMap.getOrDefault(ch, 0) + 1);
            }
        }

        // Display the duplicate characters and their frequencies
        System.out.println("Duplicate characters in the string:");
        for (Map.Entry<Character, Integer> entry : charFrequencyMap.entrySet()) {
            if (entry.getValue() > 1) {
                System.out.println("'" + entry.getKey() + "' appears " + entry.getValue() + " times.");
            }
        }
    }
}
```

---
### > Write a Program to remove duplicates in an ArrayList.
```java
import java.util.ArrayList;
import java.util.HashSet;

public class RemoveDuplicates {
    public static void main(String[] args) {
        ArrayList<Integer> arrayList = new ArrayList<>();
        arrayList.add(1);
        arrayList.add(2);
        arrayList.add(3);
        arrayList.add(2);
        arrayList.add(4);
        arrayList.add(1);
        
        System.out.println("Original ArrayList: " + arrayList);
        
        ArrayList<Integer> uniqueList = removeDuplicates(arrayList);
        
        System.out.println("ArrayList with Duplicates Removed: " + uniqueList);
    }
    
    public static <T> ArrayList<T> removeDuplicates(ArrayList<T> list) {
        // Create a HashSet to store unique elements
        HashSet<T> uniqueElements = new HashSet<>(list);
        
        // Create a new ArrayList from the unique elements
        ArrayList<T> result = new ArrayList<>(uniqueElements);
        
        return result;
    }
}
```

---
### > Find the word count in a string using HashMap Collection.

```java
import java.util.HashMap;

public class WordCount {
    public static void main(String[] args) {
        String inputString = "Hello world, how are you? Hello world!";
        
        HashMap<String, Integer> wordCountMap = countWords(inputString);
        
        System.out.println("Word Count Map: " + wordCountMap);
    }
    
    public static HashMap<String, Integer> countWords(String input) {
        HashMap<String, Integer> wordCountMap = new HashMap<>();
        
        String[] words = input.split("\\s+"); // Split the input string into words
        
        for (String word : words) {
            word = word.replaceAll("[^a-zA-Z]", "").toLowerCase(); // Remove non-alphabetic characters and convert to lowercase
            if (!word.isEmpty()) { // Ignore empty words
                wordCountMap.put(word, wordCountMap.getOrDefault(word, 0) + 1);
            }
        }
        
        return wordCountMap;
    }
}
```

### > Write a program to find the Second Highest number in an ArrayList


```java
import java.util.ArrayList;
import java.util.Collections;

public class SecondHighestNumber {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);
        numbers.add(5);
        numbers.add(20);
        numbers.add(15);
        numbers.add(25);

        int secondHighest = findSecondHighest(numbers);
        
        System.out.println("Second Highest Number: " + secondHighest);
    }
    
    public static int findSecondHighest(ArrayList<Integer> list) {
        if (list.size() < 2) {
            throw new IllegalArgumentException("List should contain at least two numbers");
        }
        
        // Sort the list in descending order
        Collections.sort(list, Collections.reverseOrder());
        
        // The second highest number will be at index 1 after sorting
        return list.get(1);
    }
}
```
OR
```java
import java.util.ArrayList;

public class SecondHighestNumberWithoutSort {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);
        numbers.add(5);
        numbers.add(20);
        numbers.add(15);
        numbers.add(25);

        int secondHighest = findSecondHighest(numbers);

        System.out.println("Second Highest Number: " + secondHighest);
    }

    public static int findSecondHighest(ArrayList<Integer> list) {
        if (list.size() < 2) {
            throw new IllegalArgumentException("List should contain at least two numbers");
        }

        int highest = Integer.MIN_VALUE;
        int secondHighest = Integer.MIN_VALUE;

        for (int number : list) {
            if (number > highest) {
                secondHighest = highest;
                highest = number;
            } else if (number > secondHighest && number != highest) {
                secondHighest = number;
            }
        }

        return secondHighest;
    }
}
```

---
### > What is the difference between System.out, System.err, and System.in?

System.out and System.err represent the monitor by default and thus can be used to send data or results to the monitor. System.out is used to display normal messages and results. System.err is used to display error messages. System.in represents InputStream object which by default represents standard input device, i.e., keyboard.

---
### > Could you provide some implementation of a Dictionary having a large number of words?


```java
import java.util.HashMap;
import java.util.Map;

public class Dictionary {
    public static void main(String[] args) {
        // Create and populate the dictionary
        HashMap<String, String> dictionary = createDictionary();

        // Look up words and display their definitions
        lookupAndDisplay(dictionary, "apple");
        lookupAndDisplay(dictionary, "banana");
        lookupAndDisplay(dictionary, "chocolate");
    }

    public static HashMap<String, String> createDictionary() {
        HashMap<String, String> dictionary = new HashMap<>();

        // Populate the dictionary with words and their definitions
        dictionary.put("apple", "a round fruit with red, green, or yellow skin");
        dictionary.put("banana", "a long curved fruit with a yellow skin");
        dictionary.put("chocolate", "a sweet food made from cacao beans");

        // Add more words and definitions here...

        return dictionary;
    }

    public static void lookupAndDisplay(Map<String, String> dictionary, String word) {
        String definition = dictionary.get(word);
        if (definition != null) {
            System.out.println(word + ": " + definition);
        } else {
            System.out.println(word + " not found in the dictionary.");
        }
    }
}
```

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
