# title: JAVA

## JAVA

### Table of Contents

| Sr No. | Question                                                                                                                                                                                                                                                 |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0      | [Ensuring Thread Execution Order](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-ensuring-thread-execution-order)                                                                                                      |
| 1      | [Handling Unhandled Exceptions in a Thread](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-handling-unhandled-exceptions-in-a-thread)                                                                                  |
| 2      | [Difference Between List<? extends T> and List<? super T>](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-difference-between-list-extends-t-and-list-super-t)                                                          |
| 3      | [Passing List<String> to a Method Accepting List<Object>](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-passing-liststring-to-a-method-accepting-listobject)                                                          |
| 4      | [Difference Between List<?> and List<Object>](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-difference-between-list-and-listobject)                                                                                   |
| 5      | [Generics with Arrays](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-generics-with-arrays)                                                                                                                            |
| 6      | [Sealed Classes & Interfaces](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-sealed-classes--interfaces)                                                                                                               |
| 7      | [What is Thread in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-thread-in-java)                                                                                                                       |
| 8      | [What is the difference between Thread and Process in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-thread-and-process-in-java)                                                 |
| 9      | [How do you implement Thread in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-do-you-implement-thread-in-java)                                                                                             |
| 10     | [When to use Runnable vs Thread in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-when-to-use-runnable-vs-thread-in-java)                                                                                       |
| 11     | [What is the difference between start() and run() method of Thread class?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-start-and-run-method-of-thread-class)                         |
| 12     | [What is the difference between Runnable and Callable in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-runnable-and-callable-in-java)                                           |
| 13     | [What is the difference between CyclicBarrier and CountDownLatch in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-cyclicbarrier-and-countdownlatch-in-java)                     |
| 14     | [What is Java Memory model?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-java-memory-model)                                                                                                                 |
| 15     | [What is volatile variable in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-volatile-variable-in-java)                                                                                                 |
| 16     | [What is thread-safety? Is Vector a thread-safe class?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-thread-safety-is-vector-a-thread-safe-class)                                                            |
| 17     | [What is race condition in Java? Given one example?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-race-condition-in-java-given-one-example)                                                                  |
| 18     | [How to stop a thread in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-to-stop-a-thread-in-java)                                                                                                           |
| 19     | [What happens when an Exception occurs in a thread?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-happens-when-an-exception-occurs-in-a-thread)                                                                 |
| 20     | [How do you share data between two threads in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-do-you-share-data-between-two-threads-in-java)                                                                 |
| 21     | [What is the difference between notify and notifyAll in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-notify-and-notifyall-in-java)                                             |
| 22     | [Why wait, notify and notifyAll are not inside thread class?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-why-wait-notify-and-notifyall-are-not-inside-thread-class)                                                |
| 23     | [What is ThreadLocal variable in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-threadlocal-variable-in-java)                                                                                           |
| 24     | [What is FutureTask in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-futuretask-in-java)                                                                                                               |
| 25     | [What is the difference between the interrupted() and isInterrupted() method in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-the-interrupted-and-isinterrupted-method-in-java) |
| 26     | [Why wait and notify method are called from synchronized block?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-why-wait-and-notify-method-are-called-from-synchronized-block)                                         |
| 27     | [Why should you check condition for waiting in a loop?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-why-should-you-check-condition-for-waiting-in-a-loop)                                                           |
| 28     | [What is the difference between synchronized and concurrent collection in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-synchronized-and-concurrent-collection-in-java)         |
| 29     | [What is the difference between Stack and Heap in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-the-difference-between-stack-and-heap-in-java)                                                         |
| 30     | [What is thread pool? Why should you thread pool in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-what-is-thread-pool-why-should-you-thread-pool-in-java)                                                      |
| 31     | [How to avoid Deadlock in Java](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-to-avoid-deadlock-in-java)                                                                                                          |
| 32     | [How do you check if Thread holds a lock or not in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-do-you-check-if-thread-holds-a-lock-or-not-in-java)                                                       |
| 33     | [How do you take Thread dump in Java?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-how-do-you-take-thread-dump-in-java)                                                                                             |
| 34     | [Which JVM parameter is used to control stack size of a Thread?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-which-jvm-parameter-is-used-to-control-stack-size-of-a-thread)                                         |
| 35     | [ReentrantLock vs Synchronized Keyword In Java](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-003.html#-reentrantlock-vs-synchronized-keyword-in-java)                                                                          |

## \*. You have thread T1, T2, and T3, how will you ensure that thread T2 run after T1 and thread T3 run after T2?

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

## \*. How do you handle an unhandled exception in the thread?

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

## \*. What is the difference between `List<? extends T>` and `List <? super T>` ?

- `List<? extends T>`: A list of objects that are instances of T or its subclasses. You can read from the list, but you cannot add to it (except `null`).

- `List<? super T>`: A list of objects that are instances of T or its superclasses. You can add instances of T or its subclasses to the list, but reading from it only returns `Object`.

## \*. Can you pass `List<String>` to a method which accepts `List<Object>` ?

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

## \*. Difference between `List<?>` and `List<Object>` in Java?

- `List<?>`: A list of unknown type. You can only read from the list, but cannot add to it (except `null`).

- `List<Object>`: A list that can hold any type of objects. You can both read from and add to the list.

## \*. Can we use Generics with Array?

You cannot create generic arrays directly in Java due to type erasure. However, you can use `List` or other generic collections instead.

```java
// This will cause a compile-time error
// T[] array = new T[10];

// You can use ArrayList instead
List<T> list = new ArrayList<>();
```

## \*. Explain Sealed Classes & Interfaces in Java.

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

To provide answers to the questions along with Java code snippets, let's go through each question from the provided image and offer a detailed explanation and corresponding code.

## \*. What is Thread in Java?

A `Thread` in Java is a lightweight process. It is the smallest unit of a process that can run concurrently with other threads.

```java
public class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }

    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start();
    }
}
```

## \*. What is the difference between Thread and Process in Java?

A `Process` is an instance of a program that runs independently and isolated from other processes, while a `Thread` is a subset of the process that runs in shared memory space.

```java
// Example code not required as this is a conceptual explanation
```

## \*. How do you implement Thread in Java?

Threads can be implemented by either extending the `Thread` class or implementing the `Runnable` interface.

```java
// Extending Thread class
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class TestThread {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}

// Implementing Runnable interface
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class TestRunnable {
    public static void main(String[] args) {
        Thread t2 = new Thread(new MyRunnable());
        t2.start();
    }
}
```

## \*. When to use Runnable vs Thread in Java?

Use `Runnable` when you want to share the same task across multiple threads or when your class already extends another class.

```java
// Runnable example provided above
```

## \*. What is the difference between start() and run() method of Thread class?

The `start()` method creates a new thread and executes the `run()` method in that new thread, while `run()` method just executes in the current thread.

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Running in thread: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.run();  // This will run in the main thread
        t1.start(); // This will run in a new thread
    }
}
```

## \*. What is the difference between Runnable and Callable in Java?

`Runnable` is a functional interface that returns void, while `Callable` returns a result and can throw a checked exception.

```java
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

class MyCallable implements Callable<Integer> {
    public Integer call() {
        return 123;
    }
}

public class TestCallable {
    public static void main(String[] args) throws Exception {
        MyCallable callable = new MyCallable();
        FutureTask<Integer> futureTask = new FutureTask<>(callable);
        Thread t = new Thread(futureTask);
        t.start();
        System.out.println(futureTask.get()); // Output will be 123
    }
}
```

## \*. What is the difference between CyclicBarrier and CountDownLatch in Java?

`CountDownLatch` is used for a single event while `CyclicBarrier` can be used for multiple events.

```java
import java.util.concurrent.CountDownLatch;
import java.util.concurrent.CyclicBarrier;

public class TestSynchronization {
    public static void main(String[] args) throws InterruptedException {
        // CountDownLatch example
        CountDownLatch latch = new CountDownLatch(3);
        Runnable task = () -> {
            latch.countDown();
            System.out.println("Counted down");
        };
        new Thread(task).start();
        new Thread(task).start();
        new Thread(task).start();
        latch.await();
        System.out.println("All tasks completed");

        // CyclicBarrier example
        CyclicBarrier barrier = new CyclicBarrier(3, () -> System.out.println("Barrier reached"));
        Runnable barrierTask = () -> {
            try {
                barrier.await();
                System.out.println("Barrier released");
            } catch (Exception e) {
                e.printStackTrace();
            }
        };
        new Thread(barrierTask).start();
        new Thread(barrierTask).start();
        new Thread(barrierTask).start();
    }
}
```

## \*. What is Java Memory model?

The Java Memory Model (JMM) defines how threads interact through memory and what behaviors are allowed in concurrent executions.

```java
// Conceptual explanation; code example not required
```

## \*. What is volatile variable in Java?

A `volatile` variable ensures visibility of changes to variables across threads.

```java
public class VolatileExample {
    private volatile boolean flag = true;

    public void run() {
        while (flag) {
            // Busy-wait loop
        }
        System.out.println("Flag changed");
    }

    public void stop() {
        flag = false;
    }

    public static void main(String[] args) throws InterruptedException {
        VolatileExample example = new VolatileExample();
        new Thread(example::run).start();
        Thread.sleep(1000);
        example.stop();
    }
}
```

## \*. What is thread-safety? Is Vector a thread-safe class?

Thread-safety means that a class or method can be used by multiple threads concurrently without causing problems. Yes, `Vector` is a thread-safe class.

```java
// Vector is synchronized, making it thread-safe
import java.util.Vector;

public class TestVector {
    public static void main(String[] args) {
        Vector<Integer> vector = new Vector<>();
        vector.add(1);
        vector.add(2);
        vector.add(3);
        System.out.println("Vector: " + vector);
    }
}
```

## \*. What is race condition in Java? Given one example?

A race condition occurs when two or more threads can access shared data and they try to change it at the same time.

```java
public class RaceConditionExample {
    private int count = 0;

    public void increment() {
        count++;
    }

    public static void main(String[] args) {
        RaceConditionExample example = new RaceConditionExample();
        Runnable task = () -> {
            for (int i = 0; i < 1000; i++) {
                example.increment();
            }
        };
        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
        try {
            t1.join();
            t2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Final count: " + example.count); // Expected 2000 but result may vary
    }
}
```

## \*. How to stop a thread in Java?

You can stop a thread in Java using a boolean flag.

```java
public class StopThreadExample {
    private volatile boolean running = true;

    public void run() {
        while (running) {
            System.out.println("Running");
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
    }

    public void stop() {
        running = false;
    }

    public static void main(String[] args) throws InterruptedException {
        StopThreadExample example = new StopThreadExample();
        Thread t = new Thread(example::run);
        t.start();
        Thread.sleep(500);
        example.stop();
    }
}
```

## \*. What happens when an Exception occurs in a thread?

When an exception occurs in a thread, it will terminate unless the exception is caught and handled.

```java
public class ExceptionThreadExample {
    public static void main(String[] args) {
        Thread t = new Thread(() -> {
            try {
                throw new RuntimeException("Thread exception");
            } catch (Exception e) {
                System.out.println("Caught exception: " + e.getMessage());
            }
        });
        t.start();
    }
}
```

## \*. How do you share data between two threads in Java?

You can share data between threads using shared objects or data structures.

```java
public class SharedDataExample {
    private int counter = 0;

    public synchronized void increment() {
        counter++;
    }

    public static void main(String[] args) {
        SharedDataExample example = new SharedDataExample();
        Runnable task = () -> {
            for (int i = 0; i < 1000; i++) {
                example.increment();
            }
        };
        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
        try {
            t1.join();
            t2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Final counter: " + example.counter); // Should be 2000
    }
}
```

## \*. What is the difference between notify and notifyAll in Java?

`notify` wakes up one waiting thread, while `notifyAll` wakes up all waiting threads.

```java
public class NotifyExample {
    private final Object lock = new Object();

    public void doWait() {
        synchronized (lock) {
            try {
                System.out.println("Waiting");
                lock.wait();
                System.out.println("Woken up");
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
    }

    public void doNotify

() {
        synchronized (lock) {
            System.out.println("Notifying one");
            lock.notify(); // or lock.notifyAll();
        }
    }

    public static void main(String[] args) throws InterruptedException {
        NotifyExample example = new NotifyExample();
        Thread t1 = new Thread(example::doWait);
        Thread t2 = new Thread(example::doWait);
        t1.start();
        t2.start();
        Thread.sleep(1000);
        example.doNotify();
    }
}
```

## \*. Why wait, notify and notifyAll are not inside thread class?

`wait`, `notify`, and `notifyAll` are part of the `Object` class because they are meant to be used on shared objects.

## \*. What is ThreadLocal variable in Java?

A `ThreadLocal` variable provides thread-local variables where each thread accessing such a variable has its own independently initialized copy.

```java
public class ThreadLocalExample {
    private static final ThreadLocal<Integer> threadLocal = ThreadLocal.withInitial(() -> 1);

    public static void main(String[] args) {
        Runnable task = () -> {
            int value = threadLocal.get();
            System.out.println("Initial value: " + value);
            threadLocal.set(value + 1);
            System.out.println("Updated value: " + threadLocal.get());
        };
        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start();
        t2.start();
    }
}
```

## \*. What is FutureTask in Java?

`FutureTask` represents a cancellable asynchronous computation. It can be used to wrap `Callable` or `Runnable` objects.

```java
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

public class FutureTaskExample {
    public static void main(String[] args) throws Exception {
        Callable<Integer> callable = () -> {
            Thread.sleep(1000);
            return 42;
        };

        FutureTask<Integer> futureTask = new FutureTask<>(callable);
        Thread t = new Thread(futureTask);
        t.start();
        System.out.println("Result: " + futureTask.get()); // Outputs 42 after 1 second
    }
}
```

## \*. What is the difference between the interrupted() and isInterrupted() method in Java?

`interrupted()` checks the interrupt status of the current thread and clears it, while `isInterrupted()` checks the interrupt status of any thread without clearing it.

```java
public class InterruptExample {
    public static void main(String[] args) {
        Thread t = new Thread(() -> {
            while (!Thread.currentThread().isInterrupted()) {
                System.out.println("Running");
            }
            System.out.println("Thread interrupted status: " + Thread.interrupted());
        });
        t.start();
        try {
            Thread.sleep(1000);
            t.interrupt();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

## \*. Why wait and notify method are called from synchronized block?

`wait` and `notify` must be called from within a synchronized block to ensure that the current thread holds the lock on the object before calling these methods.

```java
// Conceptual explanation; code example included in NotifyExample
```

## \*. Why should you check condition for waiting in a loop?

To avoid spurious wakeups, it's essential to check the waiting condition in a loop.

```java
public class SpuriousWakeupExample {
    private final Object lock = new Object();
    private boolean condition = false;

    public void waitForCondition() {
        synchronized (lock) {
            while (!condition) { // Check in a loop
                try {
                    lock.wait();
                } catch (InterruptedException e) {
                    Thread.currentThread().interrupt();
                }
            }
            System.out.println("Condition met");
        }
    }

    public void setCondition() {
        synchronized (lock) {
            condition = true;
            lock.notifyAll();
        }
    }

    public static void main(String[] args) throws InterruptedException {
        SpuriousWakeupExample example = new SpuriousWakeupExample();
        new Thread(example::waitForCondition).start();
        Thread.sleep(1000);
        example.setCondition();
    }
}
```

## \*. What is the difference between synchronized and concurrent collection in Java?

Synchronized collections are thread-safe but have a single lock for the entire collection, leading to contention. Concurrent collections, like `ConcurrentHashMap`, use finer-grained locking for better scalability.

```java
import java.util.Collections;
import java.util.HashMap;
import java.util.Map;
import java.util.concurrent.ConcurrentHashMap;

public class CollectionExample {
    public static void main(String[] args) {
        Map<String, String> syncMap = Collections.synchronizedMap(new HashMap<>());
        syncMap.put("key1", "value1");
        syncMap.put("key2", "value2");

        ConcurrentHashMap<String, String> concurrentMap = new ConcurrentHashMap<>();
        concurrentMap.put("key1", "value1");
        concurrentMap.put("key2", "value2");

        System.out.println("Synchronized Map: " + syncMap);
        System.out.println("Concurrent Map: " + concurrentMap);
    }
}
```

## \*. What is the difference between Stack and Heap in Java?

The stack is used for static memory allocation and method execution, while the heap is used for dynamic memory allocation for objects at runtime.

```java
// Conceptual explanation; code example not required
```

## \*. What is thread pool? Why should you thread pool in Java?

A thread pool manages a set of reusable threads (pool of worker threads ) for executing tasks. It improves performance by reducing the overhead associated with creating and destroying threads.

#### Why use a thread pool?

- **Resource Management**: Reuses a fixed number of threads, managing system resources efficiently.
- **Improved Performance**: Reduces the latency associated with thread creation.
- **Simplified Concurrency**: Provides a higher-level API for executing tasks concurrently.

#### Example using `ExecutorService`:

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ThreadPoolExample {
    public static void main(String[] args) {
        // Create a thread pool with 3 threads
        ExecutorService executor = Executors.newFixedThreadPool(3);

        // Submit 5 tasks to the thread pool
        for (int i = 0; i < 5; i++) {
            executor.submit(() -> {
                String threadName = Thread.currentThread().getName();
                System.out.println("Thread name: " + threadName);
                try {
                    // Simulate some work with Thread.sleep
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    Thread.currentThread().interrupt();
                }
                System.out.println("Completed: " + threadName);
            });
        }

        // Shut down the executor service
        executor.shutdown();
    }
}
```

#### Explanation:

- **ExecutorService**: Interface that represents a pool of threads.
- **Executors.newFixedThreadPool(int nThreads)**: Creates a thread pool with a fixed number of threads.
- **executor.submit(Runnable task)**: Submits a task for execution.
- **executor.shutdown()**: Initiates an orderly shutdown where previously submitted tasks are executed, but no new tasks will be accepted.

## \*. How to avoid Deadlock in Java

Deadlocks occur when two or more threads are blocked forever, waiting for each other. To avoid deadlock, you can follow several strategies:

#### 1 Avoid Nested Locks

Avoid acquiring multiple locks if possible. If you must, always acquire the locks in the same order.

```java
class A {
    synchronized void methodA(B b) {
        System.out.println("Thread 1 starts execution of methodA");
        b.last();
    }

    synchronized void last() {
        System.out.println("Inside A.last()");
    }
}

class B {
    synchronized void methodB(A a) {
        System.out.println("Thread 2 starts execution of methodB");
        a.last();
    }

    synchronized void last() {
        System.out.println("Inside B.last()");
    }
}

public class AvoidDeadlock implements Runnable {
    A a = new A();
    B b = new B();

    AvoidDeadlock() {
        Thread t = new Thread(this);
        t.start();
        a.methodA(b); // main thread
    }

    public void run() {
        b.methodB(a); // child thread
    }

    public static void main(String[] args) {
        new AvoidDeadlock();
    }
}
```

#### 2 Use `tryLock` with Timeout

Use `ReentrantLock` with `tryLock` to avoid waiting indefinitely.

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class AvoidDeadlockWithTryLock {
    private final Lock lock1 = new ReentrantLock();
    private final Lock lock2 = new ReentrantLock();

    public void method1() {
        try {
            if (lock1.tryLock() && lock2.tryLock()) {
                // Critical section
            }
        } finally {
            lock1.unlock();
            lock2.unlock();
        }
    }

    public void method2() {
        try {
            if (lock2.tryLock() && lock1.tryLock()) {
                // Critical section
            }
        } finally {
            lock2.unlock();
            lock1.unlock();
        }
    }
}
```

## \*. How do you check if Thread holds a lock or not in Java.

The `Thread` class does not provide a direct method to check if a thread holds a lock. However, you can use `ReentrantLock` to check if the current thread holds the lock.

```java
import java.util.concurrent.locks.ReentrantLock;

public class CheckLock {
    private final ReentrantLock lock = new ReentrantLock();

    public void checkLock() {
        lock.lock();
        try {
            // Check if current thread holds the lock
            if (lock.isHeldByCurrentThread()) {
                System.out.println("Current thread holds the lock");
            }
        } finally {
            lock.unlock();
        }
    }

    public static void main(String[] args) {
        CheckLock example = new CheckLock();
        example.checkLock();
    }
}
```

## \*. How do you take Thread dump in Java.

A thread dump provides a snapshot of all the threads running in a JVM. You can take a thread dump in several ways:

#### 1 Using `jstack` Command

Use the `jstack` command-line utility to get a thread dump.

```sh
jstack <pid>
```

Replace `<pid>` with the process ID of your Java application.

#### 2 Using `jvisualvm`

You can also use the `jvisualvm` tool, which provides a graphical interface to take a thread dump.

#### 3 Programmatically

You can use `ThreadMXBean` to take a thread dump programmatically.

```java
import java.lang.management.ManagementFactory;
import java.lang.management.ThreadInfo;
import java.lang.management.ThreadMXBean;

public class ThreadDump {
    public static void main(String[] args) {
        ThreadMXBean threadMxBean = ManagementFactory.getThreadMXBean();
        ThreadInfo[] threadInfos = threadMxBean.dumpAllThreads(true, true);
        for (ThreadInfo threadInfo : threadInfos) {
            System.out.println(threadInfo.toString());
        }
    }
}
```

## \*. Which JVM parameter is used to control stack size of a Thread.

You can control the stack size of a thread using the `-Xss` JVM parameter.

```sh
java -Xss512k MyClass
```

This sets the stack size of each thread to 512 kilobytes.

## \*. ReentrantLock vs Synchronized Keyword In Java.

#### Synchronized Keyword

- Implicit lock mechanism.
- Block-structured: lock is acquired and released automatically.
- Simpler to use.
- No explicit timeout.

```java
public class SynchronizedExample {
    public synchronized void syncMethod() {
        // Critical section
    }
}
```

#### ReentrantLock

- Explicit lock mechanism.
- More flexible: allows explicit lock and unlock, as well as tryLock with timeout.
- Can be fair (first-come, first-served).
- Supports multiple conditions.

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class ReentrantLockExample {
    private final Lock lock = new ReentrantLock();

    public void lockMethod() {
        lock.lock();
        try {
            // Critical section
        } finally {
            lock.unlock();
        }
    }
}
```
