# FUNCTIONS

We can predefine a block of code to execute later. Anytime we've used `()` in JavaScript browser functions (and not calling another common standard language feature like iterators), we've been calling a function.

We've used functions built in to the browser a lot in this course.

Every time we manipulated a text string, for example:

```
const myText = "I am a string";
const newString = myText.replace("string", "sausage");
console.log(newString);
// the replace() string function takes a source string,
// and a target string and replaces the source string,
// with the target string, and returns the newly formed string
```


# FUNCTION DECLARATION

A function declaration is created with the function keyword, followed by the function name and a list of parameters in parentheses.
The function body is enclosed in curly braces {}. Function declarations are hoisted, meaning they can be called before they are declared in the code.


# LOCAL VARIABLES


Variables declared inside a function using the `let` or `const` keywords are called local variables.
Local variables are only accessible within the function where they are declared.
Local variables have their own scope, separate from variables declared outside the function.


# OUTER VARIABLES

Functions can access variables declared in the outer scope, such as variables declared outside the function.
When a function tries to access a variable, it first looks for it in its own local scope. If not found, it looks in the outer scope, and so on, up to the global scope.


# ANONYMOUS FUNCTIONS

The above example shows how `replace` is a named function. We can also implement anonymous functions:

```
(function () {
  alert("hello");
});
```

I'll often see anonymous functions when a function expects to receive another function as a parameter.

The following two blocks are equivalent:

```
function logKey(event) {
  console.log(`You pressed "${event.key}".`);
}

textBox.addEventListener("keydown", logKey);
```

```
textBox.addEventListener("keydown", function (event) {
  console.log(`You pressed "${event.key}".`);
});
```


# METHODS

In Ruby, we use methods. They can be singleton methods, class methods, or even instance methods. Similarly, in JavaScript, functions that are part of an object are called methods. For now, we just wanted to clear up any possible confusion of method versus function — I'm likely to meet both terms as I look at the available related resources across the Web. Custom functions are defined in my code, rather than the browser. For instance, when I wrote methods in JS for my chatbot, I was writing custom functions.

In the following code, the `random` function is being invoked in the function `draw`:

```
function draw() {
  ctx.clearRect(0, 0, WIDTH, HEIGHT);
  for (let i = 0; i < 100; i++) {
    ctx.beginPath();
    ctx.fillStyle = "rgba(255,0,0,0.5)";
    ctx.arc(random(WIDTH), random(HEIGHT), random(50), 0, 2 * Math.PI);
    ctx.fill();
  }
}
```

`random` happens to be implemented like so:

```
function random(number) {
  return Math.floor(Math.random() * number);
}
```


# PARAMETERS

Note: Parameters are sometimes called arguments, properties, or even attributes.

Some functions require parameters to be specified when you are invoking them — these are values that need to be included inside the function parentheses. Very similar to Ruby.

And, sometimes, just as in Ruby, parameters can be optional (defaulting to certain behavior instead, or where `nil` is appropriate for remainder of the function). As an example, the array join() function's parameter is optional:

```
const myArray = ["I", "love", "chocolate", "frogs"];
const madeAString = myArray.join(" ");
console.log(madeAString);
// returns 'I love chocolate frogs'

const madeAnotherString = myArray.join();
console.log(madeAnotherString);
// returns 'I,love,chocolate,frogs'
```

And here is the implementation for including a default value if another isn't given:


```
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
```

In JavaScript, parameters are the items listed between the parentheses in the function declaration. Function arguments are the actual values we decide to pass to the function.

```
function favoriteAnimal(animal) {
   return animal + " is my favorite animal!"
 }

 console.log(favoriteAnimal('Goat'))
 ```

In the example above, the function definition is written on the first line: function favoriteAnimal(animal). The parameter, animal, is found inside the parentheses. We could just as easily replace animal with pet, x, or blah. But in this case, naming the parameter animal gives someone reading our code a bit of context so that they don’t have to guess what animal may eventually contain.
Make note of the fact that by calling favoriteAnimal() inside of console.log() with the argument 'Goat' we get the return value of the function, string of "Goat is my favorite animal!", printed to the console. We’re passing in a function call favoriteAnimal('Goat') as an argument in a different function call - log().


# DEFAULT VALUES

Function parameters can have default values assigned to them, which are used if no value is passed when calling the function.
Default values are specified using the assignment operator (=) in the parameter list.
If an argument is provided when calling the function, it overrides the default value.


# ARROW FUNCTIONS

If you pass an anonymous function like this, there's an alternative form you can use, called an arrow function. Instead of function(event), you write (event) =>. We recommend that you use arrow functions, as they can make your code shorter and more readable. Arrow functions, introduced in ECMAScript 6 (ES6), provide a concise syntax for writing functions. They are often used when defining functions that are passed as arguments to other functions or when creating shorter and more readable function expressions.

Here's a simple example to illustrate the core concepts of arrow functions:

```
textBox.addEventListener("keydown", function (event) {
  console.log(`You pressed "${event.key}".`);
});
```

is equivalent to

```
textBox.addEventListener("keydown", event => {
  console.log(`You pressed "${event.key}".`);
});
```

```
const originals = [1, 2, 3];

const doubled = originals.map(item => item * 2);

console.log(doubled); // [2, 4, 6]
```

The parameter of `item => item * 2` being passed is the equivalent to

```
function doubleItem(item) {
  return item * 2;
}
```


# ARROW FUNCTIONS


# OTHER SCOPE-RELATED SHORTCUTS

```
function checkAge(age) {
  if (age > 18) {
    return true;
  } else {
    // ...
    return confirm('Did parents allow you?');
  }
}
```

and

```
function checkAge(age) {
  if (age > 18) {
    return true;
  }
  // ...
  return confirm('Did parents allow you?');
}
```

are equivalent. There is no need for the `else` line! Personally, I think it makes it more readable.


```
function checkAge(age) {
  if (age > 18) {
    return true;
  } else {
    return confirm('Did parents allow you?');
  }
}
```

and

```
function checkAge(age) {
  return (age > 18) ? true : confirm('Did parents allow you?');
}
```

or

```
function checkAge(age) {
  return (age > 18) || confirm('Did parents allow you?');
}
```

are also equivalent.



# FUNCTION SCOPE AND CONFLICTS

The top level outside all your functions is called the global scope. Values defined in the global scope are accessible from everywhere in the code.

JavaScript is set up like this for various reasons — but mainly because of security and organization. Sometimes you don't want variables to be accessible from everywhere in the code — external scripts that you call in from elsewhere could start to mess with your code and cause problems because they happen to be using the same variable names as other parts of the code, causing conflicts. This might be done maliciously, or just by accident.

Keeping parts of your code locked away in functions avoids such problems, and is considered the best practice.

A function can have side effects, which are modifications or interactions with the outside world.
Side effects can include modifying variables outside the function, interacting with the DOM, making network requests, etc.
Pure functions are functions that do not have side effects and only depend on their arguments.


# RETURN VALUES

A function can return a value using the return statement followed by the value to be returned.
The return statement ends the function execution and passes the value back to the calling code.
If no return statement is specified, the function returns undefined by default.



# NAMING FUNCTIONS

Function names should be descriptive and represent what the function does.
Function names must be valid identifiers and follow the same naming rules as variable names.




# FUNCTION DECLARATION vs. FUNCTION EXPRESSION

There is a difference between the two. A declaration looks like this:

```
function sayHi() {
  alert( "Hello" );
}
```

while an expression looks like this:

```
let sayHi = function() {
  alert( "Hello" );
};
```

The latter of the two allows us to create a new function in the middle of any expression. As the function creation happens in the context of the assignment expression (to the right side of =), this is a Function Expression. Please note, there’s no name after the function keyword. Omitting a name is allowed for Function Expressions.

Here are the core concepts of Function Expressions vs Function Declarations:

1. Function Declarations:
   - Function declarations are statements that define a named function using the `function` keyword.
   - They are hoisted, meaning they can be called before they are declared in the code.
   - The function name is mandatory and can be used to call the function from anywhere in the scope.

2. Function Expressions:
   - Function expressions define a function as part of a larger expression, usually by assigning it to a variable.
   - They are not hoisted, so they can only be called after they have been defined.
   - The function can be anonymous (no name) or have a name, although the name is usually not used to call the function.

3. Usage and Syntax:
   - Function Declarations can be used as standalone functions or as methods on objects.
   - Function Expressions can be used as function arguments, assigned to variables, or used as IIFE (Immediately Invoked Function Expressions).
   - The syntax for a Function Declaration is: `function functionName() { /* function body */ }`.
   - The syntax for a Function Expression is: `const functionName = function() { /* function body */ }`.

4. Differences:
   - Hoisting: Function Declarations are hoisted, so they can be called before they are declared. Function Expressions are not hoisted and cannot be called before they are assigned.
   - Names: Function Declarations require a name, which can be used to call the function. Function Expressions can be anonymous or have a name, but the name is typically not used for calling.
   - Usage: Function Declarations can be used as standalone functions or as methods on objects. Function Expressions are often used as function arguments, assigned to variables, or used as IIFE.



# A FUNCTION IS A VALUE

No matter how the function is created, a function is a value. Both examples above store a function in the sayHi variable.

For instance, if you run this code, the alert will show the method syntax itself.

```
function sayHi() {
  alert( "Hello" );
}

alert( sayHi ); // shows the function code
```

Please note that the last line does not run the function, because there are no parentheses after sayHi. There are programming languages where any mention of a function name causes its execution, but JavaScript is not like that.

Because a function is a value, we can copy it to another variable and both would yield the same value:

```
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```

We also could use a function expression to declare `sayHi`:

```
let sayHi = function() { // (1) create
  alert( "Hello" );
};

let func = sayHi;
// ...
```


# A NOTE ABOUT SEMICOLONS

You might wonder, why do Function Expressions have a semicolon ; at the end, but Function Declarations do not: this is because a Function Expression is created as function(…) {…} inside the assignment statement: let sayHi = …;. The semicolon ; is recommended at the end of the statement, it’s not a part of the function syntax. The semicolon would be there for a simpler assignment, such as let sayHi = 5;, and it’s also there for a function assignment.



# CALL STACKS


1. Call Stack:
   - The call stack is a data structure used by JavaScript to keep track of function calls.
   - It follows the Last-In-First-Out (LIFO) principle, meaning that the last function called is the first one to be executed and completed.
   - Whenever a function is called, a new frame is created and pushed onto the call stack. When a function completes, its frame is popped from the stack.

Think of the call stack as a stack of plates. When you call a function, you put a new plate on top of the stack. When the function finishes, its plate is removed from the top.

2. Function Invocation and Execution:
   - When a function is invoked (called), a new frame is created and pushed onto the call stack.
   - The function's code is then executed sequentially, and any nested function calls also result in new frames being pushed onto the call stack.
   - Each frame represents a function call and contains information such as the function's arguments, local variables, and the location to return to after the function completes.

Picture a line of people waiting to go down a slide. When it's your turn, you slide down, and others wait until you finish. Inside the slide, there might be more slides that people use one after another.

3. Stack Overflow:
   - A stack overflow occurs when the call stack exceeds its maximum size.
   - This can happen if there is excessive recursion (a function calling itself repeatedly) or if there is an infinite loop that doesn't terminate.
   - When a stack overflow occurs, the browser or JavaScript engine throws an error, indicating that the call stack has exceeded its capacity.

Imagine building a tower with blocks, but you keep adding blocks without stopping. Eventually, the tower gets so tall that it falls over because it can't support its own weight.

4. Asynchronous Operations and Callback Queue:
   - JavaScript supports asynchronous operations such as setTimeout, AJAX requests, and event handlers.
   - When an asynchronous operation is encountered, it is offloaded to the browser or JavaScript engine, and the function immediately continues executing without waiting for the operation to complete.
   - Once the asynchronous operation is finished, a callback function is added to the callback queue.
   - The event loop continuously checks the call stack and if it's empty, it takes the next callback from the callback queue and pushes it onto the call stack for execution.

Think of it as cooking multiple dishes simultaneously. While one dish is simmering on the stove, you can start preparing another dish.

5. Debugging the Call Stack:
   - Understanding the call stack is essential for debugging JavaScript code.
   - By examining the call stack, you can trace the order in which functions were called and identify any errors or unexpected behavior.
   - Most modern browsers provide developer tools with a built-in debugger that allows you to pause the execution at a specific point and inspect the call stack.

Debugging the call stack is like following a treasure map with clues to find a hidden treasure. You carefully check each clue to see where it leads.







ALL DONE STUDYING THIS SECTION. PICK UP ON THE ASSIGNMENTS SECTION AT:

https://www.theodinproject.com/lessons/foundations-fundamentals-part-3