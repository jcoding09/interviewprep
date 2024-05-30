# title: JAVA Code

## JAVA Code

| Sr.No. | Question                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0      | [Create a ArrayList and find duplicate elements from ArrayList using Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-create-a-arraylist-and-find-duplicate-elements-from-arraylist-using-stream-api)                                                                                                                                                                                            |
| 1      | [Find a name of the employees starting with alphabet A from list using Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-find-a-name-of-the-employees-starting-with-alphabet-a-from-list-using-stream-api)                                                                                                                                                                                        |
| 2      | [Merge two Employee ArrayList and sort by age in using Java 8 stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-merge-two-employee-arraylist-and-sort-by-age-in-using-java-8-stream-api)                                                                                                                                                                                                          |
| 3      | [Crete ArrayList. Find the duplicates using streams. Find the elements of strings which has length more than 5 using streams. Print all the strings as UpperCase using streams.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-crete-arraylist-find-the-duplicates-using-streams-find-the-elements-of-strings-which-has-length-more-than-5-using-streams-print-all-the-strings-as-uppercase-using-streams) |
| 4      | [Find the frequency of “cc” string from array using stream.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-find-the-frequency-of-cc-string-from-array-using-stream)                                                                                                                                                                                                                                        |
| 5      | [From an ArrayList containing integers (1, 2, 3, 4, 5, 6), you need to print the minimum, maximum, sum, and sum of even numbers using the Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-from-an-arraylist-containing-integers-1-2-3-4-5-6-you-need-to-print-the-minimum-maximum-sum-and-sum-of-even-numbers-using-the-stream-api)                                                             |
| 6      | [You want to find the frequency of each character from a given string using different methods: HashMap and Stream API etc.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-you-want-to-find-the-frequency-of-each-character-from-a-given-string-using-different-methods-hashmap-and-stream-api-etc)                                                                                                         |
| 7      | [Remove duplicates from a sorted array using both traditional Java methods and the Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-remove-duplicates-from-a-sorted-array-using-both-traditional-java-methods-and-the-stream-api)                                                                                                                                                                |
| 8      | [Print the names of the passengers in a list using the Stream API.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-print-the-names-of-the-passengers-in-a-list-using-the-stream-api)                                                                                                                                                                                                                        |
| 9      | [Create and Join the two maps using streams.](https://jcoding09.github.io/interviewprep/module002/module0000/lecture-001.html#-create-and-join-the-two-maps-using-streams)                                                                                                                                                                                                                                                                    |

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

## \*. Merge two Employee ArrayList and sort by age in using Java 8 stream API.

Sure, here is a Java code snippet that demonstrates how to merge two `ArrayList` of `Employee` objects and sort them by age using the Java 8 Stream API.

First, let's define the `Employee` class:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

class Employee {
    private String name;
    private int age;

    // Constructor
    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getters
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    // Override toString method for easy printing
    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

Next, here is the code to merge two `ArrayList` of `Employee` objects and sort them by age:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args) {
        // Create two ArrayLists of Employee
        ArrayList<Employee> list1 = new ArrayList<>();
        list1.add(new Employee("Alice", 30));
        list1.add(new Employee("Bob", 25));

        ArrayList<Employee> list2 = new ArrayList<>();
        list2.add(new Employee("Charlie", 35));
        list2.add(new Employee("David", 28));

        // Merge and sort the lists using Java 8 Stream API
        List<Employee> mergedAndSorted = Stream.concat(list1.stream(), list2.stream())
                .sorted((e1, e2) -> Integer.compare(e1.getAge(), e2.getAge()))
                .collect(Collectors.toList());

        // Print the merged and sorted list
        mergedAndSorted.forEach(System.out::println);


        // Extract and print the names of the employees using Stream API
        List<String> employeeNames = mergedAndSorted.stream()
                .map(Employee::getName)
                .collect(Collectors.toList());

        System.out.println("Employee Names: " + employeeNames);
    }
}
```

Explanation:

1. We define the `Employee` class with appropriate constructors, getters, and a `toString` method for easy printing.
2. In the `Main` class, we create two `ArrayList` instances containing `Employee` objects.
3. We use `Stream.concat` to merge the two lists into a single stream.
4. We then sort the merged stream by the `age` attribute using `sorted` with a comparator.
5. Finally, we collect the sorted stream into a `List` and print each `Employee` in the merged and sorted list.

This will output:

```
Employee{name='Bob', age=25}
Employee{name='David', age=28}
Employee{name='Alice', age=30}
Employee{name='Charlie', age=35}
```

## \*. Crete ArrayList. Find the duplicates using streams. Find the elements of strings which has length more than 5 using streams. Print all the strings as UpperCase using streams.

Sure, here's the Java code that fulfills your requirements using Java 8 Stream API:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();
        fruits.add("apple");
        fruits.add("apple");
        fruits.add("banana");
        fruits.add("apple");
        fruits.add("orange");
        fruits.add("banana");
        fruits.add("papaya");

        // Find duplicates using streams
        List<String> duplicates = fruits.stream()
                .collect(Collectors.groupingBy(s -> s))
                .entrySet()
                .stream()
                .filter(e -> e.getValue().size() > 1)
                .map(e -> e.getKey())
                .collect(Collectors.toList());

        System.out.println("Duplicates: " + duplicates);

        // Find elements with length more than 5 using streams
        List<String> moreThan5Length = fruits.stream()
                .filter(s -> s.length() > 5)
                .collect(Collectors.toList());

        System.out.println("Strings with length more than 5: " + moreThan5Length);

        // Print in List format as UpperCase using streams
        System.out.println(fruits.stream().map(i->i.toUpperCase()).collect(Collectors.toList()));


        // Print all strings as UpperCase using streams
        fruits.stream()
                .map(String::toUpperCase)
                .forEach(System.out::println);
    }
}
```

Explanation:

1. We create an `ArrayList` called `fruits` and add the given fruits to it.
2. To find duplicates, we use the `groupingBy` collector to group elements by their identity (in this case, the fruit name). Then, we filter the entries by checking if the size of the list of values for each key is greater than 1, indicating a duplicate. We then map these entries back to the key (the fruit name) and collect them into a list.
3. To find elements with a length greater than 5, we simply filter the stream based on the length of each string.
4. To print all strings as uppercase, we use the `toUpperCase` method on each string in the stream and then print them using `forEach`.

This will output:

```
Duplicates: [banana, apple]
Strings with length more than 5: [banana, orange, banana, papaya]
[APPLE, APPLE, BANANA, APPLE, ORANGE, BANANA, PAPAYA]
APPLE
APPLE
BANANA
APPLE
ORANGE
BANANA
PAPAYA
```

## \*. Find the frequency of "cc" string from array using stream.

### Version 1 :

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        String[] input = {"aaa", "bbb", "cc", "cc"};

        // Find the frequency of "cc" string using stream
        long frequencyOfCc = Arrays.stream(input)
                .filter(s -> s.equals("cc"))
                .count();

        System.out.println("Frequency of 'cc': " + frequencyOfCc);
    }
}
```

Explanation:

1. We create a `String` array named `input` containing the given strings.
2. Using the `Arrays.stream()` method, we convert the array into a stream.
3. We use the `filter()` method to keep only those elements which are equal to "cc".
4. We then count the occurrences of "cc" using the `count()` method.
5. Finally, we print the frequency of "cc".

The output will be:

```
Frequency of 'cc': 2
```

### Version 2 :

Use the `equals()` method instead of `==`.

```java
import java.util.Arrays;
import java.util.function.Function;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        String[] input = {"aaa", "bbb", "cc", "cc"};

        long frequencyOfCc = Arrays.stream(input)
                .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()))
                .entrySet().stream()
                .filter(v -> v.getKey().equals("cc")) // Use equals() instead of ==
                .map(v -> v.getValue())
                .findFirst()
                .orElse(0L); // Default value if "cc" is not found

        System.out.println("Frequency of 'cc': " + frequencyOfCc);
    }
}
```

Explanation:

- We first use `Collectors.groupingBy` to group the elements of the array by their identity (i.e., the string value) and count their occurrences.
- Then, we convert the resulting map to a stream of entries.
- We use `filter` to keep only the entry where the key (the string) is equal to "cc". Note that we use `equals()` for string comparison.
- We then map the stream of entries to their values (which represent the count of occurrences).
- Finally, we use `findFirst()` to get the first occurrence count of "cc", or a default value of 0 if "cc" is not found.

This code will correctly output:

```
Frequency of 'cc': 2
```

## \*. From an ArrayList containing integers (1, 2, 3, 4, 5, 6), you need to print the minimum, maximum, sum, and sum of even numbers using the Stream API.

Sure, here's the refined version of the question:

From an ArrayList containing integers (1, 2, 3, 4, 5, 6), you need to print the minimum, maximum, sum, and sum of even numbers using the Stream API.

And here's the Java code to achieve this:

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6);

        // Print Min, Max, Sum using stream API
        int min = numbers.stream().min(Integer::compareTo).orElse(0);
        int max = numbers.stream().max(Integer::compareTo).orElse(0);
        int sum = numbers.stream().mapToInt(Integer::intValue).sum();

        System.out.println("Min: " + min);
        System.out.println("Max: " + max);
        System.out.println("Sum: " + sum);

        // Print sum of even numbers using stream API
        int sumOfEven = numbers.stream()
                .filter(n -> n % 2 == 0)
                .mapToInt(Integer::intValue)
                .sum();

        System.out.println("Sum of Even Numbers: " + sumOfEven);
    }
}
```

Explanation:

- We create an ArrayList of integers using `Arrays.asList()`.
- To find the minimum, maximum, and sum of all numbers, we use the Stream API's `min`, `max`, and `sum` methods respectively.
- To find the sum of even numbers, we use the `filter` method to keep only even numbers, then use the `mapToInt` method to convert them to `IntStream`, and finally, use the `sum` method to calculate the sum.
- We print the results accordingly.

This code will output:

```
Min: 1
Max: 6
Sum: 21
Sum of Even Numbers: 12
```

## \*. You want to find the frequency of each character from a given string using different methods: HashMap and Stream API etc.

```java
import java.util.HashMap;
import java.util.Map;
import java.util.function.Function;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        String inputString = "hello world";

        // Using HashMap
        Map<Character, Integer> frequencyMap = new HashMap<>();
        for (char c : inputString.toCharArray()) {
            frequencyMap.put(c, frequencyMap.getOrDefault(c, 0) + 1);
        }
        System.out.println("Frequency using HashMap:");
        System.out.println(frequencyMap);

        // Using Stream API
        Map<Character, Long> frequencyMapStream = inputString.chars()
                .mapToObj(c -> (char) c)
                .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()));
        System.out.println("Frequency using Stream API:");
        System.out.println(frequencyMapStream);

        // Using Stream API - Variant 1
        Map<Character, Integer> frequency2 = inputString.chars()
                .mapToObj(c -> (char) c)
                .collect(Collectors.groupingBy(Function.identity(), Collectors.summingInt(c -> 1)));
        System.out.println("Frequency using Stream API (Variant 1):");
        System.out.println(frequency2);

        // Using Stream API - Variant 2
        Map<Character, Integer> frequency3 = inputString.chars()
                .mapToObj(c -> (char) c)
                .collect(Collectors.toMap(Function.identity(), c -> 1, Math::addExact));
        System.out.println("Frequency using Stream API (Variant 2):");
        System.out.println(frequency3);
    }
}
```

Explanation:

- **Using HashMap**:

  - We create a `HashMap<Character, Integer>` called `frequencyMap` to store the frequency of each character.
  - We iterate through each character in the input string using a for-each loop.
  - For each character, we update its frequency in the map using `getOrDefault` method to handle the case where the character is encountered for the first time.
  - Finally, we print the frequency map.

- **Using Stream API**:

  - We convert the input string to an `IntStream` using `chars()`.
  - Then, we map each character code to its corresponding character using `mapToObj`.
  - Next, we collect the characters into a map using `groupingBy` collector to group characters by their identity and `counting` collector to count occurrences of each character.
  - Finally, we print the frequency map.

- **Using Stream API - Variant 1**:

  - We use `Collectors.summingInt` to calculate the sum of the occurrence of each character, similar to the previous approach.

- **Using Stream API - Variant 2**:

  - We use `Collectors.toMap` to collect characters into a map, where the value is always `1` for each character. We use `Math::addExact` to handle the case where two characters with the same key are encountered, ensuring the accurate sum.

## \*. Remove duplicates from a sorted array using both traditional Java methods and the Stream API.

Using Java normal method:

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] sortedArray = {1, 1, 2, 3, 3, 4, 5, 5, 6, 7, 7};
        int[] uniqueArray = removeDuplicates(sortedArray);

        System.out.println("Unique elements in the array (Normal Method): ");
        for (int i = 0; i < uniqueArray.length; i++) {
            System.out.print(uniqueArray[i] + " ");
        }
    }

    public static int[] removeDuplicates(int[] sortedArray) {
        int n = sortedArray.length;
        if (n == 0 || n == 1) {
            return sortedArray;
        }
        int[] temp = new int[n];
        int j = 0;
        for (int i = 0; i < n - 1; i++) {
            if (sortedArray[i] != sortedArray[i + 1]) {
                temp[j++] = sortedArray[i];
            }
        }
        temp[j++] = sortedArray[n - 1];
        int[] uniqueArray = new int[j];
        for (int i = 0; i < j; i++) {
            uniqueArray[i] = temp[i];
        }
        return uniqueArray;
    }
}
```

Using Stream API:

```java
import java.util.Arrays;
import java.util.stream.IntStream;

public class Main {
    public static void main(String[] args) {
        int[] sortedArray = {1, 1, 2, 3, 3, 4, 5, 5, 6, 7, 7};

        int[] uniqueArray = IntStream.range(0, sortedArray.length)
                                      .filter(i -> i == 0 || sortedArray[i] != sortedArray[i - 1])
                                      .map(i -> sortedArray[i])
                                      .toArray();

        System.out.println("Unique elements in the array (Stream API): ");
        Arrays.stream(uniqueArray).forEach(System.out::print);
    }
}
```

Explanation:

- In the normal method, we iterate over the array, comparing each element with the next one. If they are not equal, we copy the element to a temporary array. Finally, we create a new array with unique elements based on the size of the temporary array.
- In the Stream API method, we use `IntStream` to iterate over the indices of the array. We filter out the elements that are equal to their previous ones (except for the first element), and then map each index to its corresponding element. Finally, we collect these elements into an array using `toArray()`.

## \*. Print the names of the passengers in a list using the Stream API.

Create a stream of the `Passenger` objects, map them to their names, and collect them into a list. Here's how you can do it:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
        List<Passenger> passengers = new ArrayList<>();
        passengers.add(new Passenger("Alice", 1, "2024-05-30"));
        passengers.add(new Passenger("Bob", 2, "2024-05-30"));
        passengers.add(new Passenger("Charlie", 3, "2024-05-30"));

        // Print the names of passengers in a list using Stream API
        List<String> passengerNames = passengers.stream()
                .map(Passenger::getName)
                .collect(Collectors.toList());

        // Print the list of passenger names
        System.out.println("Passenger Names:");
        passengerNames.forEach(System.out::println);
    }
}

class Passenger {
    private String name;
    private int id;
    private String date;

    // Constructor
    public Passenger(String name, int id, String date) {
        this.name = name;
        this.id = id;
        this.date = date;
    }

    // Getter for name
    public String getName() {
        return name;
    }
}
```

In this code:

- We create a `Passenger` class with `name`, `id`, and `date` attributes.
- We create a list of `Passenger` objects and populate it.
- We use the Stream API to convert the list of `Passenger` objects into a stream.
- We use the `map` operation to extract the names of the passengers.
- We collect these names into a list using the `collect` method with `Collectors.toList()`.
- Finally, we print the list of passenger names.

This will output:

```
Passenger Names:
Alice
Bob
Charlie
```

## \*. Create and Join the two maps using streams.

You can use the `Stream.concat()` method along with `Collectors.toMap()` to merge the maps. Here's how you can do it:

```java
import java.util.HashMap;
import java.util.Map;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args) {
        // Create two maps
        Map<Integer, String> map1 = new HashMap<>();
        map1.put(1, "Alice");
        map1.put(2, "Bob");
        map1.put(3, "Charlie");

        Map<Integer, String> map2 = new HashMap<>();
        map2.put(4, "David");
        map2.put(5, "Eve");
        map2.put(6, "Frank");

        // Join the two maps using streams
        Map<Integer, String> joinedMap = Stream.concat(map1.entrySet().stream(), map2.entrySet().stream())
                .collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue, (value1, value2) -> value2));

        // Print the joined map
        System.out.println("Joined Map:");
        joinedMap.forEach((key, value) -> System.out.println(key + " -> " + value));
    }
}
```

In this code:

- We create two maps, `map1` and `map2`, each containing key-value pairs.
- We use `Stream.concat()` to concatenate the entry sets of both maps into a single stream of map entries.
- We then collect these map entries into a new map using `Collectors.toMap()`. In case of duplicate keys, we resolve conflicts by choosing the value from the second map (you can adjust this behavior by providing your own merge function).
- Finally, we print the joined map.

This will output:

```
Joined Map:
1 -> Alice
2 -> Bob
3 -> Charlie
4 -> David
5 -> Eve
6 -> Frank
```
