# title: JAVA Code

## JAVA Code

| Sr.No. | Question                                                                                                                                                             |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | [Create a ArrayList and find duplicate elements from ArrayList using Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-) |

## \*. Create a ArrayList and find duplicate elements from ArrayList using Stream API.

Certainly! Here's an example of Java code that demonstrates how to create an `ArrayList` and find duplicate elements from the list using the Stream API:

```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online

import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.*;
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
