# title: JAVA Code

## JAVA Code

| Sr.No. | Question                                                                                                                                                                                                                                           |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | [Create a ArrayList and find duplicate elements from ArrayList using Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-create-a-arraylist-and-find-duplicate-elements-from-arraylist-using-stream-api) |

| 2 | [Find a name of the employees starting with alphabet A from list using Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-create-a-arraylist-and-find-duplicate-elements-from-arraylist-using-stream-api) |

## \*. Create a ArrayList and find duplicate elements from ArrayList using Stream API.

Certainly! Here's an example of Java code that demonstrates how to create an `ArrayList` and find duplicate elements from the list using the Stream API:

```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online

import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.Arrays;
import java.util.Collections;
import java.util.function.Function;
import java.util.stream.Collectors;

public class FindDuplicates {

    public static void main(String[] args) {
        // Create an ArrayList and add elements to it
        List<String> list = new ArrayList<>();
        list.add("apple");
        list.add("banana");
        list.add("orange");
        list.add("apple");
        list.add("banana");
        list.add("grape");

        // Find duplicate elements using Stream API
        List<String> duplicates = list.stream()
            .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()))
            .entrySet().stream()
            .filter(entry -> entry.getValue() > 1)
            .map(Map.Entry::getKey)
            .collect(Collectors.toList());

        // Print the duplicate elements
        System.out.println("Duplicate elements using 1st Approach: ");
        System.out.println(duplicates);

        //2nd Method
        List<Integer> myList = Arrays.asList(10,15,8,49,25,98,98,32,15);

        System.out.println("Duplicate elements using 2nd Approach: ");
        System.out.println(myList.stream().filter(i->Collections.frequency(myList,i)>1).collect(Collectors.toSet()));
    }
}
```

When you run this code, it will output:

```
Duplicate elements using 1st Approach:
[banana, apple]
Duplicate elements using 2nd Approach:
[98, 15]
```

## \*. Find a name of the employees starting with alphabet A from list using Stream API.

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

class Employee {
    private String name;

    public Employee(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

public class FilterEmployees {

    public static void main(String[] args) {
        // Create a list of employees
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee("Alice"));
        employees.add(new Employee("Bob"));
        employees.add(new Employee("Alex"));
        employees.add(new Employee("John"));
        employees.add(new Employee("Amy"));

        // Filter employees whose names start with 'A'
        List<Employee> employeesStartingWithA = employees.stream()
            .filter(employee -> employee.getName().startsWith("A"))
            .collect(Collectors.toList());

        // Print the names of employees starting with 'A'
        System.out.println("Employees whose names start with 'A':");
        employeesStartingWithA.forEach(employee -> System.out.println(employee.getName()));
    }
}

```

When you run this code, it will output:

```
Employees whose names start with 'A':
Alice
Alex
Amy
```

## \*.
