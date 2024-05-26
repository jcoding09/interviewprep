# title: Q&A

## JAVA

## \*. What are the key principles of object-oriented programming, and could you provide an example of each?

Object-oriented programming (OOP) in Java is based on four key principles: Encapsulation, Inheritance, Polymorphism, and Abstraction. Here's an overview of each principle with examples:

### 1. Encapsulation

Encapsulation is the bundling of data (variables) and methods (functions) that operate on the data into a single unit, usually a class. It restricts direct access to some of the object's components, which is a means of preventing accidental interference and misuse of the data.

**Example:**

```java
public class EncapsulationExample {
    private String name;
    private int age;

    // Getter method for name
    public String getName() {
        return name;
    }

    // Setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for age
    public int getAge() {
        return age;
    }

    // Setter method for age
    public void setAge(int age) {
        this.age = age;
    }
}
```

#### Example of Encapsulation with Validation

While getters and setters are the most common way to achieve encapsulation, another way to demonstrate encapsulation is by restricting direct access to certain class members and providing methods that control access and modify these members in a controlled manner. This can include methods that perform validation or other logic before modifying the state.

**BankAccount Class with Encapsulation**

```java
public class BankAccount {
    // Private fields to encapsulate the data
    private String accountNumber;
    private double balance;

    // Constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        if (initialBalance >= 0) {
            this.balance = initialBalance;
        } else {
            this.balance = 0;
        }
    }

    // Method to deposit money with validation
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: $" + amount);
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    // Method to withdraw money with validation
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrew: $" + amount);
        } else {
            System.out.println("Invalid withdrawal amount or insufficient balance.");
        }
    }

    // Method to display the current balance
    public void displayBalance() {
        System.out.println("Current balance: $" + balance);
    }

    // Private method for internal use
    private void logTransaction(String message) {
        // Log transaction (hypothetical implementation)
        System.out.println("Transaction Log: " + message);
    }
}
```

**Main Class to Use BankAccount**

```java
public class Main {
    public static void main(String[] args) {
        // Creating a BankAccount object
        BankAccount account = new BankAccount("123456789", 1000);

        // Accessing the BankAccount through its methods
        account.displayBalance(); // Output: Current balance: $1000
        account.deposit(500);     // Output: Deposited: $500
        account.displayBalance(); // Output: Current balance: $1500
        account.withdraw(200);    // Output: Withdrew: $200
        account.displayBalance(); // Output: Current balance: $1300
        account.withdraw(2000);   // Output: Invalid withdrawal amount or insufficient balance.
    }
}
```

#### Explanation

1. **Private Fields**: The `accountNumber` and `balance` fields are private, meaning they cannot be accessed directly from outside the class. This encapsulates the data, ensuring that it can only be modified through the class methods.

2. **Constructor with Validation**: The constructor ensures that the initial balance cannot be negative.

3. **Methods with Validation**: The `deposit` and `withdraw` methods include logic to validate the input. This ensures that the state of the `BankAccount` object remains consistent and valid. For example, you can't withdraw more money than is available in the account, and you can't deposit or withdraw a negative amount.

4. **Private Helper Method**: The `logTransaction` method is private, meaning it is intended for internal use within the `BankAccount` class only. This method can be used to log transactions without exposing this functionality to the outside world.

By using methods with built-in validation and making fields private, this example demonstrates encapsulation by controlling how the internal state of an object is accessed and modified.

### 2. Inheritance

Inheritance is a mechanism wherein a new class is derived from an existing class. The new class, known as the subclass (or derived class), inherits the attributes and methods of the superclass (or base class).

**Example:**

```java
// Superclass
public class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

// Subclass
public class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }

    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Inherited method
        dog.bark(); // Own method
    }
}
```

### 3. Polymorphism

Polymorphism allows methods to do different things based on the object it is acting upon, even though they share the same name. It can be achieved through method overriding (runtime polymorphism) and method overloading (compile-time polymorphism).

**Example:**

```java
// Method Overloading (Compile-time Polymorphism)
public class PolymorphismExample {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        PolymorphismExample example = new PolymorphismExample();
        System.out.println(example.add(2, 3));       // Output: 5
        System.out.println(example.add(2, 3, 4));    // Output: 9
    }
}

// Method Overriding (Runtime Polymorphism)
public class Animal {
    public void sound() {
        System.out.println("This animal makes a sound");
    }
}

public class Cat extends Animal {
    @Override
    public void sound() {
        System.out.println("The cat meows");
    }

    public static void main(String[] args) {
        Animal myCat = new Cat();
        myCat.sound();  // Output: The cat meows
    }
}
```

### 4. Abstraction

Abstraction is the concept of hiding the complex implementation details and showing only the essential features of the object. It can be achieved using `abstract classes and interfaces`.

**Example:**

```java
// Abstract Class
abstract class Animal {
    // Abstract method (does not have a body)
    public abstract void animalSound();

    // Regular method
    public void sleep() {
        System.out.println("This animal sleeps.");
    }
}

// Subclass (inherited from Animal)
public class Pig extends Animal {
    public void animalSound() {
        System.out.println("The pig says: wee wee");
    }

    public static void main(String[] args) {
        Pig myPig = new Pig();
        myPig.animalSound(); // Output: The pig says: wee wee
        myPig.sleep();       // Output: This animal sleeps.
    }
}
```

#### Is the @Override Annotation Necessary for Interface Methods?

The `@Override` annotation is not strictly necessary when implementing methods from an interface, but it is highly recommended. Here’s why:

1. **Compile-Time Checking**: The `@Override` annotation tells the compiler that the method is intended to override a method in a superclass or implement an interface method. If the method signature does not match the method in the interface (e.g., due to a typo or incorrect parameters), the compiler will generate an error. This helps catch mistakes early.

2. **Readability and Maintenance**: Using `@Override` makes the code more readable and maintainable. It clearly indicates that the method is an implementation of an interface method, making it easier for other developers (or your future self) to understand the code.

**Example:**

```java
public interface Animal {
    void animalSound();
    void sleep();
}

public class Pig implements Animal {
    @Override
    public void animalSound() {
        System.out.println("The pig says: wee wee");
    }

    @Override
    public void sleep() {
        System.out.println("The pig sleeps.");
    }
}
```

#### Why Can't We Create Objects of an Interface or Abstract Class?

##### Interfaces:

- **Purpose**: An interface is a contract that specifies what methods a class must implement but does not provide any implementation itself.
- **Instantiation**: Since interfaces do not have any concrete implementation, there is no behavior to instantiate. You cannot create an instance of an interface directly because it does not have any code to execute.

##### Abstract Classes:

- **Purpose**: An abstract class can provide both complete (concrete) methods and incomplete (abstract) methods that must be implemented by subclasses.
- **Instantiation**: Similar to interfaces, you cannot create an instance of an abstract class because it might contain abstract methods with no implementation. Even if it has some concrete methods, it is meant to be a base class to be extended, not to be instantiated on its own.

**Example:**

```java
// Interface
public interface Animal {
    void animalSound();
    void sleep();
}

// Abstract Class
public abstract class Bird {
    public abstract void fly(); // Abstract method

    public void eat() { // Concrete method
        System.out.println("The bird eats.");
    }
}

// Class implementing an interface
public class Pig implements Animal {
    @Override
    public void animalSound() {
        System.out.println("The pig says: wee wee");
    }

    @Override
    public void sleep() {
        System.out.println("The pig sleeps.");
    }
}

// Class extending an abstract class
public class Sparrow extends Bird {
    @Override
    public void fly() {
        System.out.println("The sparrow flies.");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Pig myPig = new Pig(); // Valid
        myPig.animalSound();
        myPig.sleep();

        Sparrow mySparrow = new Sparrow(); // Valid
        mySparrow.fly();
        mySparrow.eat();

        // Animal myAnimal = new Animal(); // Invalid, cannot instantiate interface
        // Bird myBird = new Bird(); // Invalid, cannot instantiate abstract class
    }
}
```

#### **default methods** and **static methods** in Interface JAVA 8

In Java 8, interfaces can have concrete methods. These are called **default methods** and **static methods**.

##### Default Methods

Default methods are methods defined in an interface with the `default` keyword and provide a concrete implementation. This feature allows interfaces to evolve by adding new methods without breaking existing implementations of the interface.

**Example of Default Methods:**

```java
public interface Animal {
    void animalSound(); // Abstract method

    // Default method
    default void sleep() {
        System.out.println("This animal sleeps.");
    }
}

public class Pig implements Animal {
    @Override
    public void animalSound() {
        System.out.println("The pig says: wee wee");
    }

    // Pig class does not need to implement sleep() method
    // as it has a default implementation in the interface
}

public class Main {
    public static void main(String[] args) {
        Pig myPig = new Pig();
        myPig.animalSound(); // Output: The pig says: wee wee
        myPig.sleep();       // Output: This animal sleeps.
    }
}
```

##### Static Methods

Static methods in interfaces are similar to static methods in classes. They belong to the interface itself rather than to instances of the interface.

**Example of Static Methods:**

```java
public interface Animal {
    void animalSound(); // Abstract method

    // Static method
    static void printInfo() {
        System.out.println("This is an animal.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal.printInfo(); // Output: This is an animal.
    }
}
```

##### Why Introduce Default and Static Methods?

1. **Backward Compatibility**: Default methods allow the addition of new methods to interfaces without breaking the existing implementations. Before Java 8, adding a new method to an interface would force all implementing classes to provide an implementation for that method, potentially breaking a lot of code.
2. **Utility Methods**: Static methods in interfaces provide a way to include utility methods related to the interface without requiring a separate utility class.

These principles are fundamental to writing robust, maintainable, and scalable object-oriented code in Java.

## \*. Is it possible for the 'public static void main' method to work without being named 'main'? If not, why? Describe 'public static void main'

The main method must be named main because it is a convention specified by the JVM to identify the entry point of a Java application. Deviating from this convention will prevent the JVM from starting the program correctly.

Public:- it is an access specifier that means it will be accessed by publically. Static:- it is access modifier that means when the java program is load then it will create the space in memory automatically.
Void:- it is a return type that is it does not return any value.
main():- it is a method or a function name.

## \*. Can we run a class in Java 1.9, which was compiled in Java 1.8?

yes but in some cases it might not work.

## \*. Can a single Java class contain multiple 'main' methods? If so, how does the program determine which one to execute?

Yes, a single Java class can contain multiple `main` methods with different parameter lists (overloaded), but only the `public static void main(String[] args)` method will be executed by the JVM.

Below is a code example of a single Java class containing multiple `main` methods with different parameter lists (overloaded). The JVM will only execute the `public static void main(String[] args)` method.

```java
public class MainMethodExample {

    // Standard main method that JVM will execute
    public static void main(String[] args) {
        System.out.println("Hello from the standard main method!");
        // Calling other main methods for demonstration
        main(42);
        main("Overloaded main method");
    }

    // Overloaded main method with an integer parameter
    public static void main(int arg) {
        System.out.println("Hello from the main method with int parameter: " + arg);
    }

    // Overloaded main method with a string parameter
    public static void main(String arg) {
        System.out.println("Hello from the main method with String parameter: " + arg);
    }
}
```

### Explanation

1. **Standard `main` method**: This is the method that the JVM will look for and execute when the program starts.

2. **Overloaded `main` methods**: These methods have different parameter lists (one takes an `int`, and the other takes a `String`). These will not be executed by the JVM automatically but can be called from within the standard `main` method or other methods in the class.

### Execution

When you run the program using the command `java MainMethodExample`, the JVM will execute the standard `public static void main(String[] args)` method, and the output will be:

```
Hello from the standard main method!
Hello from the main method with int parameter: 42
Hello from the main method with String parameter: Overloaded main method
```

## \*. Describe what is constructor and types of constructor in JAVA with code example.

### What is a Constructor in Java?

A constructor in Java is a special method that is called when an object is instantiated. The purpose of a constructor is to initialize the newly created object. Constructors have the same name as the class and do not have a return type, not even `void`.

### Types of Constructors in Java

1. **Default Constructor**: A no-argument constructor provided by the compiler if no constructors are defined in the class. It initializes the object with default values.
2. **No-Argument Constructor**: A constructor that does not take any parameters. If a class does not explicitly define a constructor, the compiler automatically provides a default no-argument constructor.
3. **Parameterized Constructor**: A constructor that takes arguments to initialize the object with specific values.

### Examples

**1. Default Constructor**

If you do not provide any constructor, Java provides a default constructor that initializes the object with default values.

```java
public class DefaultConstructorExample {
    int value;

    // No need to explicitly define a default constructor
    // Java provides one if no constructors are defined

    public static void main(String[] args) {
        DefaultConstructorExample obj = new DefaultConstructorExample();
        System.out.println("Value: " + obj.value); // Output: Value: 0
    }
}
```

**2. No-Argument Constructor**

You can explicitly define a no-argument constructor to initialize default values.

```java
public class NoArgConstructorExample {
    int value;

    // No-argument constructor
    public NoArgConstructorExample() {
        value = 42; // Default initialization
    }

    public static void main(String[] args) {
        NoArgConstructorExample obj = new NoArgConstructorExample();
        System.out.println("Value: " + obj.value); // Output: Value: 42
    }
}
```

**3. Parameterized Constructor**

A constructor with parameters allows you to pass initial values to the object at the time of creation.

```java
public class ParameterizedConstructorExample {
    int value;

    // Parameterized constructor
    public ParameterizedConstructorExample(int value) {
        this.value = value;
    }

    public static void main(String[] args) {
        ParameterizedConstructorExample obj = new ParameterizedConstructorExample(100);
        System.out.println("Value: " + obj.value); // Output: Value: 100
    }
}
```

### Summary

- **Default Constructor**: Provided by the compiler if no constructors are defined.
- **No-Argument Constructor**: Explicitly defined with no parameters, used to initialize default values.
- **Parameterized Constructor**: Allows passing specific values to initialize the object during instantiation.

These constructors help in the creation and initialization of objects, providing flexibility in how objects are instantiated and initialized in Java.

## \*. Explain the differences between encapsulation and abstraction in Java with examples.

### \*. Differentiate between method overloading and method overriding, providing examples.

### \*. Explain Inheritance vs Composition

### \*. What are access modifiers in Java, and which ones are inherited by subclasses?

### \*. Default vs protected access specifiers.

### \*. Explain the concept of a static method in Java and its significance.

### \*. Can you override a private or static method in Java?

### \*. Could you elaborate on the usage of 'this' and 'super' keywords in Java?

### \*. Discuss the immutability of Strings in Java and the reasons behind it.

### \*. Implement your own immutable class in Java.

### \*. Compare and contrast shallow cloning and deep cloning in Java, providing examples.

### \*. What happens when you override both the 'equals' and 'hashCode' methods in Java? What if 'hashCode' returns the same value while 'equals' returns false?

### \*. Explore the features introduced in Java 8 such as Function Interface, Method Reference, Streams, lambda function and Collections.

### \*. What are the different types of functional interfaces in java ?

### \*. How do you invoke lambda function ?

### \*. How is the diamond problem resolved in interfaces after Java 8?

### \*. Differentiate between abstract classes and interfaces in Java, discussing their respective use cases.

### \*. What is marker interface ?

### \*. What is multithreading in Java, and how can you implement it using threads (Start with how thread is created)?

### \*. Explain the concepts of compile-time and runtime exceptions in Java, with examples.

### \*. What are some best practices for handling exceptions in Java programs?

### \*. Is a catch block mandatory when handling exceptions in Java? Explain.

### \*. What is nested try-catch in Java, and when might you use it (Describe all possibilities)?

### \*. What will happen if you put the return statement or System.exit() on the try or catch block? Will finally block execute?

### \*. If a method throws NullPointerException in the superclass, can we override it with a method that throws RuntimeException? - Is it possible to load a class by two ClassLoader?

### \*. Discuss the significance of the 'volatile' keyword in Java and its impact on multithreading.

### \*. Explain serialization in Java and its importance in data persistence.

### \*. What happens if your Serializable class contains a member which is not serializable? How do you fix it?

### \*. What is a Singleton class, and how do you implement it in Java? What problem does it solve?

### \*. What is double check locking in singletons? - Are enums Singleton in Java?

### \*. Could you elaborate on FutureTask and Callable interfaces in Java, and how they relate to concurrency?

### \*. Why do we use readResolve in singletons? - Why wait(), notify(), and notifyAll() methods have to be called from a synchronized method or block?

### \*. Why are wait, notify, and notifyAll in the Object class?

### \*. Differentiate between concurrency and parallelism in Java.

### \*. Provide examples of IllegalStateException and NoSuchElementException in Java, and when they might occur.

### \*. How would you implement the Producer-Consumer pattern in Java using both wait/notify and BlockingQueue?

### \*. Why can constructors be created in abstract classes but not initialized? Explain the reasoning behind this.

### \*. How can you create custom exceptions in Java? Provide a brief overview of the process.

### \*. Explain the differences between ClassNotFoundException and NoClassDefFoundError exceptions in Java.

### \*. {Concurrency, Parallelism, Threads (Multithreading) (java)}, Processes, Async, and Sync?

### \*. How does hashing work in Java HashMap? Provide an overview of the process.

### \*. Compare and contrast ArrayList with LinkedList in Java, highlighting their differences.

### \*. Discuss the distinctions between ArrayList and HashMap in Java.

### \*. What are the differences between TreeSet and HashSet in Java, and when would you use each?

### \*. Compare Vector and ArrayList in Java, considering their features and use cases.

### \*. How to create a custom annotation?

### \*. What is Record In Java?

### \*. Map vs. flatMap in Stream API.

### \*. Discuss Stringbuffer vs Stringbuilder vs string

### \*. Describe Has a & Is a relationship.

### \*. What is Try with resources in exception handling.
