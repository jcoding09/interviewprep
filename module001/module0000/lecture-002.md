# title: Q&A

## Spring Boot

## \*. How to create custom exception while creating the REST API in Spring Boot.

Creating custom exceptions in a Spring Boot REST API involves defining custom exception classes, creating a global exception handler, and using these exceptions in your service layer. Here’s a step-by-step guide on how to achieve this:

### 1. Define Custom Exception Classes

First, create your custom exception classes. These should extend `RuntimeException` or another appropriate exception superclass.

```java
// src/main/java/com/example/demo/exception/ResourceNotFoundException.java
package com.example.demo.exception;

public class ResourceNotFoundException extends RuntimeException {
    public ResourceNotFoundException(String message) {
        super(message);
    }
}
```

You can create more custom exceptions in a similar way.

### 2. Create a Global Exception Handler

Next, create a global exception handler using the `@ControllerAdvice` annotation. This class will handle exceptions thrown by your controllers and return appropriate HTTP responses.

```java
// src/main/java/com/example/demo/exception/GlobalExceptionHandler.java
package com.example.demo.exception;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.ControllerAdvice;
import org.springframework.web.context.request.WebRequest;

@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(ResourceNotFoundException.class)
    public ResponseEntity<?> handleResourceNotFoundException(ResourceNotFoundException ex, WebRequest request) {
        ErrorDetails errorDetails = new ErrorDetails(HttpStatus.NOT_FOUND.value(), ex.getMessage(), request.getDescription(false));
        return new ResponseEntity<>(errorDetails, HttpStatus.NOT_FOUND);
    }

    // Other exception handlers...

    // Fallback method
    @ExceptionHandler(Exception.class)
    public ResponseEntity<?> handleGlobalException(Exception ex, WebRequest request) {
        ErrorDetails errorDetails = new ErrorDetails(HttpStatus.INTERNAL_SERVER_ERROR.value(), ex.getMessage(), request.getDescription(false));
        return new ResponseEntity<>(errorDetails, HttpStatus.INTERNAL_SERVER_ERROR);
    }
}
```

### 3. Define an Error Details Class

Create an `ErrorDetails` class to structure the error response.

```java
// src/main/java/com/example/demo/exception/ErrorDetails.java
package com.example.demo.exception;

public class ErrorDetails {
    private int statusCode;
    private String message;
    private String details;

    public ErrorDetails(int statusCode, String message, String details) {
        this.statusCode = statusCode;
        this.message = message;
        this.details = details;
    }

    // Getters and setters...

    public int getStatusCode() {
        return statusCode;
    }

    public void setStatusCode(int statusCode) {
        this.statusCode = statusCode;
    }

    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }

    public String getDetails() {
        return details;
    }

    public void setDetails(String details) {
        this.details = details;
    }
}
```

### 4. Use Custom Exceptions in Your Service Layer

In your service layer, throw the custom exceptions when necessary.

```java
// src/main/java/com/example/demo/service/UserService.java
package com.example.demo.service;

import com.example.demo.exception.ResourceNotFoundException;
import com.example.demo.model.User;
import com.example.demo.repository.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.Optional;

@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public User getUserById(Long id) {
        Optional<User> user = userRepository.findById(id);
        if (user.isEmpty()) {
            throw new ResourceNotFoundException("User not found with id " + id);
        }
        return user.get();
    }

    // Other service methods...
}
```

### 5. Update Controller to Use the Service

Ensure your controller uses the service layer, which will now throw the custom exceptions.

```java
// src/main/java/com/example/demo/controller/UserController.java
package com.example.demo.controller;

import com.example.demo.model.User;
import com.example.demo.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/users")
public class UserController {

    @Autowired
    private UserService userService;

    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        User user = userService.getUserById(id);
        return ResponseEntity.ok().body(user);
    }

    // Other endpoints...
}
```

### Summary

1. **Define Custom Exception Classes**: Create classes for each custom exception.
2. **Global Exception Handler**: Implement a global exception handler using `@ControllerAdvice`.
3. **Error Details Class**: Create a class to structure error details.
4. **Service Layer**: Use custom exceptions in your service layer.
5. **Controller Layer**: Ensure your controllers call the service layer methods.

## \*. Difference between Controller and RestController in Spring Boot.

In Spring Boot, both `@Controller` and `@RestController` annotations are used to define controllers, but they serve slightly different purposes and have different behaviors, especially in the context of web applications.

### `@Controller`

- **Purpose**: The `@Controller` annotation is used to mark a class as a Spring MVC controller. It is typically used for web applications that return views (usually HTML).
- **Behavior**: When you use `@Controller`, you often return view names (like JSP or Thymeleaf templates) from handler methods, which are resolved by a `ViewResolver` to render the appropriate view.
- **Usage Example**:

  ```java
  import org.springframework.stereotype.Controller;
  import org.springframework.ui.Model;
  import org.springframework.web.bind.annotation.GetMapping;

  @Controller
  public class MyController {

      @GetMapping("/greeting")
      public String greeting(Model model) {
          model.addAttribute("message", "Hello, World!");
          return "greeting";  // returns the view name "greeting"
      }
  }
  ```

In this example, the `greeting` method returns a view name `greeting`, which is resolved by a view resolver to a specific HTML page.

### `@RestController`

- **Purpose**: The `@RestController` annotation is a specialized version of the `@Controller` annotation. It is used to create RESTful web services. This annotation is essentially a combination of `@Controller` and `@ResponseBody`.
- **Behavior**: When you use `@RestController`, the return value of handler methods is automatically serialized to the HTTP response body as JSON or XML (depending on the configuration and request). This eliminates the need to annotate each method with `@ResponseBody`.
- **Usage Example**:

  ```java
  import org.springframework.web.bind.annotation.GetMapping;
  import org.springframework.web.bind.annotation.RequestMapping;
  import org.springframework.web.bind.annotation.RestController;

  @RestController
  @RequestMapping("/api")
  public class MyRestController {

      @GetMapping("/greeting")
      public String greeting() {
          return "Hello, World!";  // returns "Hello, World!" as a JSON response
      }
  }
  ```

In this example, the `greeting` method returns a plain string which is automatically converted to a JSON response (e.g., `"Hello, World!"`).

### Key Differences

1. **Return Type Handling**:

   - `@Controller`: Typically returns view names, which are resolved to HTML pages. Requires `@ResponseBody` for returning data directly.
   - `@RestController`: Directly returns data (e.g., JSON, XML) which is written to the HTTP response body.

2. **Annotation Composition**:

   - `@Controller`: Just a marker for Spring MVC controllers.
   - `@RestController`: Combines `@Controller` and `@ResponseBody`, simplifying the creation of RESTful endpoints.

3. **Usage Context**:
   - `@Controller`: Best suited for web applications where the server-side rendering of views (HTML) is needed.
   - `@RestController`: Best suited for RESTful APIs where the server provides data directly in the form of JSON or XML.

## \*. Explain where and whenservice annotation to use in Spring Boot. How repository and Hibernate ORM is connected. Demonstrate the code.

In Spring Boot, the `@Service` annotation is used to mark a class as a service layer component. This annotation indicates that the class contains business logic and can be used by Spring's component scanning to detect and register it as a Spring bean.

### When and Where to Use `@Service` Annotation

- **Business Logic Layer**: Use `@Service` to annotate classes that contain business logic. These classes typically perform operations such as calculations, data processing, and interactions with the repository layer.
- **Service Layer**: The service layer acts as an intermediary between the controller and repository layers, providing an abstraction over data access and business logic.

### Example of `@Service` Annotation

```java
// src/main/java/com/example/demo/service/UserService.java
package com.example.demo.service;

import com.example.demo.model.User;
import com.example.demo.repository.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.Optional;

@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public User getUserById(Long id) {
        Optional<User> user = userRepository.findById(id);
        if (user.isEmpty()) {
            throw new ResourceNotFoundException("User not found with id " + id);
        }
        return user.get();
    }

    // Other business methods...
}
```

In this example, `UserService` is marked with `@Service`, making it a Spring-managed bean. It uses a `UserRepository` to access data and contains business logic.

### Repository and Hibernate ORM Connection

The `@Repository` annotation in Spring is used to indicate that the class is a Data Access Object (DAO) that interacts with the database. Spring provides an implementation of the DAO pattern by extending the `JpaRepository` interface provided by Spring Data JPA. Hibernate ORM is used as the JPA provider to handle the object-relational mapping.

### Example of `@Repository` Annotation

```java
// src/main/java/com/example/demo/repository/UserRepository.java
package com.example.demo.repository;

import com.example.demo.model.User;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    // Custom query methods (if needed)
}
```

In this example, `UserRepository` extends `JpaRepository`, which provides CRUD operations and more for the `User` entity. The `@Repository` annotation is optional here because `JpaRepository` is already annotated with `@Repository`.

### Example of Hibernate ORM with Spring Data JPA

1. **Entity Class**:

   ```java
   // src/main/java/com/example/demo/model/User.java
   package com.example.demo.model;

   import javax.persistence.Entity;
   import javax.persistence.GeneratedValue;
   import javax.persistence.GenerationType;
   import javax.persistence.Id;

   @Entity
   public class User {

       @Id
       @GeneratedValue(strategy = GenerationType.IDENTITY)
       private Long id;

       private String name;
       private String email;

       // Getters and setters...

       public Long getId() {
           return id;
       }

       public void setId(Long id) {
           this.id = id;
       }

       public String getName() {
           return name;
       }

       public void setName(String name) {
           this.name = name;
       }

       public String getEmail() {
           return email;
       }

       public void setEmail(String email) {
           this.email = email;
       }
   }
   ```

2. **Service Layer** (Using the repository):

   ```java
   // src/main/java/com/example/demo/service/UserService.java
   package com.example.demo.service;

   import com.example.demo.model.User;
   import com.example.demo.repository.UserRepository;
   import org.springframework.beans.factory.annotation.Autowired;
   import org.springframework.stereotype.Service;

   import java.util.List;
   import java.util.Optional;

   @Service
   public class UserService {

       @Autowired
       private UserRepository userRepository;

       public User getUserById(Long id) {
           Optional<User> user = userRepository.findById(id);
           if (user.isEmpty()) {
               throw new ResourceNotFoundException("User not found with id " + id);
           }
           return user.get();
       }

       public List<User> getAllUsers() {
           return userRepository.findAll();
       }

       public User createUser(User user) {
           return userRepository.save(user);
       }

       public User updateUser(Long id, User userDetails) {
           User user = getUserById(id);
           user.setName(userDetails.getName());
           user.setEmail(userDetails.getEmail());
           return userRepository.save(user);
       }

       public void deleteUser(Long id) {
           User user = getUserById(id);
           userRepository.delete(user);
       }
   }
   ```

3. **Controller Layer** (Using the service):

   ```java
   // src/main/java/com/example/demo/controller/UserController.java
   package com.example.demo.controller;

   import com.example.demo.model.User;
   import com.example.demo.service.UserService;
   import org.springframework.beans.factory.annotation.Autowired;
   import org.springframework.http.ResponseEntity;
   import org.springframework.web.bind.annotation.*;

   import java.util.List;

   @RestController
   @RequestMapping("/api/users")
   public class UserController {

       @Autowired
       private UserService userService;

       @GetMapping
       public List<User> getAllUsers() {
           return userService.getAllUsers();
       }

       @GetMapping("/{id}")
       public ResponseEntity<User> getUserById(@PathVariable Long id) {
           User user = userService.getUserById(id);
           return ResponseEntity.ok().body(user);
       }

       @PostMapping
       public User createUser(@RequestBody User user) {
           return userService.createUser(user);
       }

       @PutMapping("/{id}")
       public ResponseEntity<User> updateUser(@PathVariable Long id, @RequestBody User userDetails) {
           User updatedUser = userService.updateUser(id, userDetails);
           return ResponseEntity.ok().body(updatedUser);
       }

       @DeleteMapping("/{id}")
       public ResponseEntity<Void> deleteUser(@PathVariable Long id) {
           userService.deleteUser(id);
           return ResponseEntity.noContent().build();
       }
   }
   ```

### Summary

- **`@Service`**: Used to mark a class as a service layer component, containing business logic.
- **`@Repository`**: Used to mark a class as a DAO component, interacting with the database.
- **Hibernate ORM**: Manages the object-relational mapping between Java objects and database tables, used as the JPA provider in Spring Data JPA.
