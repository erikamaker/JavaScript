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

- Functions can have multiple parameters or no parameters at all.

```
// Function invocation
greet("John"); // Output: Hello, John!
sayHello();    // Output: Hello!
```

- The code inside a function is executed when the function is called or invoked.

```
// Function execution
function add(a, b) {
  return a + b;
}
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