# title: JAVA

## JAVA

### Table of Contents

| Sr.No. | Question |
| ------ | -------- |
| 0      | [ ]()    |

Sure! Here are the explanations along with the Java code examples:

## \*. Ensuring Thread Execution Order

To ensure that thread T2 runs after T1 and thread T3 runs after T2, you can use the `join()` method. This method allows one thread to wait for the completion of another.

```java
public class ThreadExecutionOrder {
    public static void main(String[] args) {
        Thread t1 = new Thread(() -> {
            System.out.println("Thread T1 is running");
        });

        Thread t2 = new Thread(() -> {
            try {
                t1.join(); // T2 waits for T1 to finish
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("Thread T2 is running");
        });

        Thread t3 = new Thread(() -> {
            try {
                t2.join(); // T3 waits for T2 to finish
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("Thread T3 is running");
        });

        t1.start();
        t2.start();
        t3.start();
    }
}
```

## \*. Handling Unhandled Exceptions in a Thread

You can set an `UncaughtExceptionHandler` for a thread to handle uncaught exceptions.

```java
public class UnhandledException {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            throw new RuntimeException("An unhandled exception");
        });

        thread.setUncaughtExceptionHandler((t, e) -> {
            System.out.println("Caught exception from thread: " + t.getName() + " - " + e.getMessage());
        });

        thread.start();
    }
}
```

## \*. Difference Between `List<? extends T>` and `List<? super T>`

- `List<? extends T>`: A list of objects that are instances of T or its subclasses. You can read from the list, but you cannot add to it (except `null`).

- `List<? super T>`: A list of objects that are instances of T or its superclasses. You can add instances of T or its subclasses to the list, but reading from it only returns `Object`.

## \*. Passing `List<String>` to a Method Accepting `List<Object>`

No, you cannot pass `List<String>` to a method that accepts `List<Object>` because of type safety. Generics are invariant in Java.

```java
public class GenericExample {
    public static void main(String[] args) {
        List<String> stringList = new ArrayList<>();
        // methodAcceptingObjectList(stringList); // This will cause a compile-time error
    }

    public static void methodAcceptingObjectList(List<Object> list) {
        // Implementation
    }
}
```

## \*. Difference Between `List<?>` and `List<Object>`

- `List<?>`: A list of unknown type. You can only read from the list, but cannot add to it (except `null`).

- `List<Object>`: A list that can hold any type of objects. You can both read from and add to the list.

## \*. Generics with Arrays

You cannot create generic arrays directly in Java due to type erasure. However, you can use `List` or other generic collections instead.

```java
// This will cause a compile-time error
// T[] array = new T[10];

// You can use ArrayList instead
List<T> list = new ArrayList<>();
```

## \*. Sealed Classes & Interfaces

Sealed classes and interfaces restrict which classes can extend or implement them. Introduced in Java 15 as a preview feature and standardized in Java 17.

```java
sealed class Shape permits Circle, Square {
}

final class Circle extends Shape {
}

final class Square extends Shape {
}

public class SealedClassExample {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Square();
        System.out.println(shape1 instanceof Circle); // true
        System.out.println(shape2 instanceof Square); // true
    }
}
```

In this example, only `Circle` and `Square` are permitted to extend `Shape`. Any attempt to extend `Shape` by another class will result in a compilation error.
