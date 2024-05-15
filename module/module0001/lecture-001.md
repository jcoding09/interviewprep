## title: JavaScript

<br>

1. **Call Stack**: A data structure used by programming languages to manage function invocation. When a function is called, it's added to the top of the stack, and when it returns, it's removed from the stack.

2. **Primitive Types**: Basic data types in a programming language that are not objects. Examples include numbers, strings, booleans, null, and undefined.

3. **Implicit, Explicit, Nominal, Structuring, Duck Typing**: These are different approaches to type checking and type inference in programming languages. Implicit typing infers types based on context, explicit typing requires explicit declaration of types, nominal typing checks for compatibility based on explicit type names, structural typing checks for compatibility based on the structure of types, and duck typing checks for compatibility based on the presence of certain methods or properties.

4. **== vs === vs typeof**: These are operators used for comparison and type checking in JavaScript. "==" checks for equality with type coercion, "===" checks for strict equality without type coercion, and "typeof" is an operator that returns the type of a variable or expression as a string.

5. **Function Scope, Block Scope, and Lexical Scope**: These refer to the rules governing the visibility and lifetime of variables in different parts of a program. Function scope means variables are visible only within the function they're declared in, block scope means variables are visible only within the block they're declared in (like within curly braces in JavaScript), and lexical scope means variables are visible within the lexical scope they're defined in, including any nested scopes.

6. **Expression vs Statement**: An expression is any valid unit of code that evaluates to a value, while a statement is a standalone unit of code that performs some action.

7. **IIFE, Modules, and Namespaces**: These are different techniques used for organizing and encapsulating code in JavaScript. IIFE (Immediately Invoked Function Expression) is a function that is executed immediately after it's defined, modules are self-contained units of code that can export and import functionality, and namespaces are objects used to group related functionality under a single object.

8. **Message Queue and Event Loop**: These are mechanisms used in JavaScript for handling asynchronous code execution. The event loop continuously checks the call stack and message queue, and when the call stack is empty, it takes the first message in the queue and executes it.

9. **setTimeout, setInterval & requestAnimationFrame**: These are functions used for scheduling code execution in JavaScript. setTimeout and setInterval are used to execute code after a specified delay or at regular intervals, while requestAnimationFrame is a function optimized for executing animations and other visual updates.

10. **JavaScript Engines**: These are programs that execute JavaScript code. They typically include a parser, an interpreter, and a just-in-time compiler.

11. **DOM and Layout Trees**: The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of objects. The layout tree is a representation of how elements are displayed on the screen.

12. **Factories and Classes**: These are two different approaches to creating objects in JavaScript. Factories are functions that create and return objects, while classes are blueprints for creating objects using the "class" keyword introduced in ES6.

13. **this, call, apply, and bind**: These are mechanisms used in JavaScript for managing the context of function execution. "this" refers to the current execution context, "call" and "apply" are methods that allow you to explicitly set the value of "this" when calling a function, and "bind" is a method that returns a new function with a fixed value for "this".

14. **new, Constructor, instanceof, and Instances**: These are related to object instantiation in JavaScript. "new" is an operator used to create instances of objects, constructors are functions used to initialize new objects created with "new", "instanceof" is an operator used to check if an object is an instance of a particular class or constructor function, and instances are individual objects created from a constructor function.

15. **Prototype Inheritance and Prototype Chain**: In JavaScript, objects inherit properties and methods from a prototype object. Each object has an internal link to its prototype, forming a chain of prototypes.

16. **Object.create and Object.assign**: These are methods used for creating new objects in JavaScript. Object.create creates a new object with the specified prototype object, while Object.assign copies the properties of one or more source objects to a target object.

17. **map, reduce, filter**: These are higher-order functions commonly used with arrays in JavaScript. "map" applies a function to each element of an array and returns a new array with the results, "reduce" applies a function to each element of an array, accumulating a single result, and "filter" creates a new array containing only the elements that pass a test function.

18. **Pure Functions, Side Effects & State Mutation**: These are concepts related to functional programming. Pure functions are functions that always return the same result given the same inputs and have no side effects. Side effects are changes to the state of the program or external environment caused by a function. State mutation refers to changing the state of variables or objects.

19. **Closures**: A closure is a function that has access to its own scope, the scope of its outer function, and the global scope, even after the outer function has finished executing.

20. **High Order Functions**: These are functions that take other functions as arguments or return functions as results.

21. **Event Propagation**: This refers to the process by which events are handled in the DOM. Events can propagate either through capturing (from the outermost element to the target element) or bubbling (from the target element to the outermost element).

22. **Promises**: Promises are objects representing the eventual completion or failure of an asynchronous operation. They allow you to handle asynchronous operations in a more elegant and concise way than traditional callback-based approaches.

23. **async/await**: These are keywords introduced in ES8 (ECMAScript 2017) for working with asynchronous code in a more synchronous-like manner. "async" is used to define asynchronous functions, and "await" is used to pause the execution of an asynchronous function until a promise is resolved.
