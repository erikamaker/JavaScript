# Data Types

This section of Odin is meant to each me the 8 types of data in JS. I should understand the difference between single, double, and backtick quotes. I should be able to embed a variable/expression in a string (like Ruby expression interpolation), understand what a method is, name three logical operators, understand what the comparison operators are, understand what conditionals are, understand what nesting is, and understand what "truthy" and "falsy" values are. 


# Starting with Strings

A string is a piece of text. It's a fundamental building block of the language, just like Ruby. HTML provides structure and content to our text, and CSS allows us to style it. JavaScript contains features for manipulating strings (including creating custom welcome messages and prompts), showing the right text labels when needed, sorting terms, and a lot more. 

Strings are dealt with similarly to numbers. For instance, I wrote this in my Chrome's console: 

```
const string = "The revolution will not be televised.";
console.log(string);
```

And it output just the same a number type would have. This is because we declared it as a constant, initialized it with a string value, and returned the value to the log. And, just like in Ruby, the big difference is that I had to use quotes. Same error behavior will apply to unclosed quotes. There is very little difference between single and double quotes, and is down to personal preference. However, differently quoted code can be confusing, so pick one and stick to it. 

That said, something like this: 

```
const bigmouth = 'I've got no right to take my place...'; 
```

will throw an error, since the single quote also represents the apostrophe in the string. Now it has 3 total single quotes to read. We can fix this with escape characters. In Ruby, I've used them (e.g. "\n"). Here's how we'd fix the above: 

```
const bigmouth = 'I\'ve got no right to take my place...'; 
```

For more escape sequences, check out: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#escape_sequences


# Concatenating Strings

Concatenate just means "join together". To concatenate strings in JS, you can use a specific type of string called a "template literal". This is different from a string literal, but uses backticks (like what I put at the start and end of code snippets in MD files). So, an example would be: 


```
const greeting = `Hello`;
```

It works like a normal string, with the benefit of including variables inside wrapped in `${}`. This is similar to how I use `#{}` in Ruby. Here is an example of implementation: 


```
const name = "Chris";
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"
```

or 

```
const one = "Hello, ";
const two = "how are you?";
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```

And HERE is a fun implementation for buttons that DO things :D 


```
// for HTML <button>Press me</button>

const button = document.querySelector("button");   // declare a constant named for the HTML element "button" 

function greet() {                                 // define a function `greet` that 
  const name = prompt("What is your name?");       // defines a variable `name` through the prompt function.
  alert(`Hello ${name}, nice to see you!`);        // returns the variable `name` as an alert, joined into a string
}

button.addEventListener("click", greet);
```


You can use the `+` operator to concatenate: 

`console.log(greeting + ", " + name); // "Hello, Erika"`


But it's better to use the template literal for readability: 

`console.log(`${greeting}, ${name}`); // "Hello, Erika"`


Or heck, try inserting entire expressions! 

```
const song = "Fight the Youth";
const score = 9;
const highestScore = 10;
const output = `I like the song ${song}. I gave it a score of ${
  (score / highestScore) * 100
}%.`;
console.log(output); // "I like the song Fight the Youth. I gave it a score of 90%."
```





# Numbers vs. Strings 

We can easily combine strings and numbers. Take for instance this concatenation example (just pretend you've declared / assigned to a string and number type): 


```
console.log(`${name}${number}`); // "Front 242"
```

This works because, while representing a string as a number doesn't make much sense (note from self: what about hashes?), representing a number as a string does. Use the following to easily convert between the two types! 

The Number() function converts anything passed to it into a number, if it can: 

```
const myString = "123";
const myNum = Number(myString);
console.log(typeof myNum);
```

Conversely, every number has a method called toString() that converts it to the equivalent string. Try this:


```
const myNum2 = 123;
const myString2 = myNum2.toString();
console.log(typeof myString2);
```


Oh, and it turns out that multiline strings are super easy to do! Check out these two equivalent implementations: 


```
const output = `I like the song.
I gave it a score of 90%.`;
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/
```

```
const output = "I like the song.\nI gave it a score of 90%.";
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/
```

Easily get the length of any JS string: 

```
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;
```



# JavaScript String Methods 

There are a lot of good references for quick syntax cheat sheets. You'll never run out of them. And ChatGPT will likely know the simplest ones too. 

Here's one such: https://www.w3schools.com/js/js_string_methods.asp

