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
```

- Closures allow inner functions to access variables and parameters from their outer functions, even after the outer functions have completed execution.

```
const greet = outerFunction();
greet("John"); // Output: Hello, John
```



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