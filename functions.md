# Functions in JavaScript

- Functions are fundamental building blocks in JavaScript that encapsulate a set of statements and can be reused.

```
// Function with parameters
function greet(name) {
  console.log("Hello, " + name + "!");
}
```

- They are defined using the `function` keyword, followed by a name and a set of parentheses that may contain parameters.

```
// Function without parameters
function sayHello() {
  console.log("Hello!");
}
```

```
const myText = "I am a string";
const newString = myText.replace("string", "sausage");
```

- Functions can have multiple parameters or no parameters at all.

```
// Function invocation
greet("John"); // Output: Hello, John!
sayHello();    // Output: Hello!
```

- The code inside a function is executed when the function is called or invoked.

```
function myFunction() {
  alert("hello");
}

myFunction();
// calls the function once

```

- Functions can return values using the `return` statement.

```
// Function return value
// the return statement is crucial for outputting the value of a * b
function multiply(a, b) {
  return a * b;
}
```

- A function can be assigned to a variable, allowing it to be passed around and used as a value.

```
// Function assignment to a variable
const subtract = function(a, b) {
  return a - b;
};

// Function invocation and variable usage
console.log(add(2, 3));       // Output: 5
console.log(multiply(4, 5));  // Output: 20
console.log(subtract(8, 3));  // Output: 5
```

- JavaScript functions can be defined using function declarations or function expressions.

```
// Function declaration
function greet() {
  console.log("Hello!");
}
```

- Function declarations have a name and are hoisted to the top of their scope, meaning they can be called before they are defined.

- In JavaScript, function declarations are hoisted to the top of their scope, which means they can be called before they are defined in the code. This allows you to call a function declaration even if it appears later in the code.

- This behavior differs from Ruby, where methods are not hoisted. In Ruby, methods must be defined before they are called; otherwise, an error will occur. The only exception to this is when methods are defined within a class. In Ruby, methods defined within a class are available for use once the class is initialized, allowing you to call them on instances of that class.


```
// Function expression
const sayGoodbye = function() {
  console.log("Goodbye!");
};
```

- Function expressions are defined as part of a larger expression or assigned to a variable, and they are not hoisted.

```
greet();        // Output: Hello!
sayGoodbye();   // Output: Goodbye!
```

- Arrow functions provide a concise syntax for defining functions, using the `=>` operator.

```
// Arrow function
const multiply = (a, b) => a * b;
```

If you weren't aware of this nuance, you might have written it like so:

```
// Regular function
const multiply = function(a, b) {
  return a * b;
};
```

- Functions can also be nested within other functions, creating a concept called closures.

```
// Function with closure
function outerFunction() {
  const message = "Hello, ";

  function innerFunction(name) {
    console.log(message + name);
  }

  return innerFunction;
}

const greet = outerFunction();
greet("John"); // Output: Hello, John
```

In this example, we have the function outerFunction that defines an inner function called innerFunction. The outerFunction has a variable message which stores the string "Hello, ".

When outerFunction is called and executed, it returns the innerFunction without executing it. The returned innerFunction maintains access to the message variable due to closure, even after the outerFunction has completed execution.

By assigning the returned innerFunction to the variable greet, we can later invoke greet("John"), passing the name "John" as an argument. The inner function combines the message and the provided name, resulting in the output "Hello, John".

This demonstrates how closures allow inner functions to access variables from their outer functions, even after the outer functions have finished executing.

- Closures allow inner functions to access variables and parameters from their outer functions, even after the outer functions have completed execution. Another example

```
// Function that creates a greeting function
function createGreeting(name) {
  return function() {
    console.log("Hello, " + name);
  };
}

const greetErika = createGreeting("Erika");
greetErika(); // Output: Hello, Erika
```

In this updated example, we have a function createGreeting that takes a name parameter. Inside createGreeting, it returns an inner function that logs a greeting message using the name parameter from the outer scope.

By calling createGreeting("Erika"), it returns the inner function that still has access to the name variable, even though createGreeting has finished executing. We assign this returned inner function to the variable greetErika.

Finally, when we invoke greetErika(), it executes the inner function, which logs the greeting message "Hello, Erika" to the console. The inner function maintains access to the name variable in its outer scope, thanks to closure.

This example demonstrates closure by showing how the inner function preserves access to variables from its outer scope, even after the outer function has completed execution.


- Functions can also take other functions as parameters, enabling higher-order functions.

```
// Function that takes another function as a parameter
function higherOrderFunction(callback) {
  console.log("Executing higher-order function");
  callback();
}
```

```
// Function to be passed as a parameter
function callbackFunction() {
  console.log("Executing callback function");
}
```

```
higherOrderFunction(callbackFunction); // Output: Executing higher-order function
                                       //         Executing callback function
```

- The `this` keyword inside a function refers to the object that called the function, providing a way to access its properties and methods.

```
// Function accessing object properties using "this"
const person = {
  name: "John",
  greet: function() {
    console.log("Hello, " + this.name + "!");
  }
};
```

- JavaScript provides several built-in functions and methods, but you can also define your own custom functions.

```
person.greet(); // Output: Hello, John!

// Custom function
function customFunction() {
  console.log("Executing custom function");
}

customFunction(); // Output: Executing custom function
```



# Function is to JS as Method is to Ruby

- In JavaScript, the term "function" refers to a fundamental building block that encapsulates a set of statements and can be reused.
- In Ruby, the equivalent concept to a JavaScript function is called a "method."
- Functions in JavaScript are defined using the `function` keyword, while methods in Ruby are defined within classes and can be called on objects of that class.
- JavaScript functions can be assigned to variables and passed around as values, while Ruby methods are associated with specific classes and can only be called on objects of those classes.
- JavaScript functions can be defined using function declarations, function expressions, or arrow functions, while Ruby methods are typically defined within a class using the `def` keyword.
- Both functions in JavaScript and methods in Ruby can have parameters and return values.
- JavaScript functions have a special keyword `this` to refer to the object that called the function, while Ruby methods have the `self` keyword for the same purpose.
- While both JavaScript and Ruby provide built-in functions/methods, you can also define your own custom functions/methods in both languages.
- `this` is to JS as `self` is to Ruby.



# The difference between a JS Function and a JS Method (Despite my comparison above, JS does have both)

Here's a simple example illustrating the differences between functions and methods in JavaScript:

```
// Standalone function
function sayHello() {
  console.log("Hello!");
}

sayHello(); // Output: Hello!

// Object with a method
const person = {
  name: "John",
  greet: function() {
    console.log("Hello, my name is " + this.name);
  }
};

person.greet(); // Output: Hello, my name is John
```

In this example, we have a standalone function called sayHello. It is defined independently and can be called directly by its name sayHello(). The function has its own scope and can be invoked from anywhere in the code.

On the other hand, we have an object person with a method greet. The greet method is defined within the person object and is accessed using dot notation (person.greet()). When person.greet() is invoked, the function code inside the method is executed, and this.name refers to the name property of the person object.

The key differences between the standalone function and the method are:

1. Invocation: The standalone function is invoked directly by its name (sayHello()), while the method is invoked on the object (person.greet()).
2. Scope: The standalone function has its own scope, while the method can access the object's properties using this.
3. Relationship to Objects: The standalone function is not tied to any specific object, while the method is associated with and operates on the person object.

By understanding these differences, you can leverage functions as reusable code blocks and methods as behavior tied to specific objects.


# All About Scope

- Scope is an important concept in JavaScript that determines the accessibility of variables and other things defined within functions.
- When you create a function, the variables and other elements defined inside the function have their own separate scope and are not directly accessible from outside the function.
- The top-level scope, outside all functions, is called the global scope, and values defined in the global scope are accessible from anywhere in the code.
- JavaScript uses scope to provide security and organization. It prevents variables from being accessed and modified unintentionally by external scripts or conflicting with variable names in other parts of the code.

In summary, scope in JavaScript ensures that variables and elements are encapsulated within their respective functions, avoiding conflicts and unwanted modifications. The global scope allows for the accessibility of values across the code, while function scopes provide isolation and protection. The concept of scope in JavaScript is similar to other object-oriented programming languages like Ruby.

In both languages, scope determines the visibility and accessibility of variables and other elements within functions or methods. The global scope in JavaScript is akin to the top-level scope in Ruby, where variables and elements defined outside of any specific class or method can be accessed throughout the code. Similarly, both languages provide local scopes within functions or methods, where variables and elements are encapsulated and can only be accessed within their respective scopes. This helps prevent naming conflicts and provides a level of organization and security.

While the concept of scope is common across many programming languages, the specific rules and behaviors surrounding scope can vary. It's important to understand the nuances and specific scope rules of each language when working with variables and functions to avoid any unexpected behavior. So, although the concept of scope is not unique to JavaScript and can be found in other object-oriented languages like Ruby, the exact rules and syntax for scoping may differ.


# Return Values


Return Values are intuitively named-- they're the returned values of a function.

- Return values are the values that a function produces or sends back as the output after performing its operations.
- In JavaScript, you can use the `return` statement to specify the return value of a function.
- When a `return` statement is encountered, the function stops executing and immediately exits, returning the specified value.
- Functions can return different types of values, including numbers, strings, booleans, objects, or even other functions.
- You can capture and store the return value of a function by assigning it to a variable or using it directly.
- If a function does not have a `return` statement, it implicitly returns `undefined`.
- Multiple `return` statements can be used within a function, but only the first encountered `return` statement will be executed.
- Example code:

```
// Function with a return value
function add(a, b) {
  return a + b;
}

const result = add(3, 5);
console.log(result); // Output: 8

// Function with no return statement
function greet(name) {
  console.log("Hello, " + name);
}

const greeting = greet("John");
console.log(greeting); // Output: Hello, John
                        //        undefined
```

In this code example, we have a function `add` that takes two parameters and returns their sum using the `return` statement. The returned value is stored in the variable `result` and then printed to the console.

We also have a function `greet` that does not have a `return` statement. It simply logs a greeting message to the console. When invoking `greet("John")`, the message is displayed, but since there is no explicit return value, it implicitly returns `undefined`. This is assigned to the variable `greeting` and printed to the console.

These examples showcase how return values allow functions to produce output that can be used in further computations or stored for later use.




