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

# ANONYMOUS FUNCTIONS

The above example shows how `replace` is a named function. We can also implement anonymous functions:

```
(function () {
  alert("hello");
});
```

I'll often see anonymous functions when a function expects to receive another function as a parameter.


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




Pick up at Anonymous function example
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions