# JS VARIABLES 


# HOW DO YOU CREATE A VARIABLE? 

A variable is a "storage container" for data. It holds a place in memory. There used to only be one way to create a variable in JavaScript (`var` statement). But there are more ways in the newest version-- `let` and `const`. 

console.log() is the command to print something to the developer console in your browser. Another way to include JavaScript in a webpage is through an external script. This requires linking it much like you would a CSS doc, however. I think the first way (see boilerplate.html in this folder) is easier, so I'm going to try and stick with that for simpler exerises (more complex scripts will require separate files). 


# THREE WAYS TO DECLARE: 

`let`, `const`,`var`. 

To create a variable, use the `let` keyword (we'll be sticking with the newest keywords): 


```
let message;   

message = 'Hello';   // store string to variable `message`
```


The string is now saved into the memory location associated with the variable. We can access it in various ways now, like an alert message on a webpage. 


```
alert(message); 
```

We can also declare this more concisely, or add other variables: 


```
let user = 'John', age = 25, message = 'Hello'; 
```

But, it's easier to read like this: 


```
let user = 'John';   // or using commas (ending with a semicolon) 
age = 25;
message = 'Hello'; 
```

Just like with Ruby, I can change the values of these variables anytime I like. When a value is changed, the old data is removed from the variable and replaced. We can also assign variables to other variables, like so :


```
let hello = "Hello, World!"; 
let message; 

message = hello; 

alert(hello) // Hello, World! 
alert(message) // Hello, World!
```

It is worth noting, however, that I am not able to DECLARE a variable twice (i.e. no `let hello = "hello,world"; let hello = "Nevermind.";`) 


# When should you use each? 

`const` and `let` are both relatiely new, so `var` is more common. In fact, `var` and `let` behave the same way in most cases (just... not ALL the time). But, Odin prescribes that we stick with `let` and `const`, so that's what we're doing. 


# HOW SHOULD VARIABLES IN JAVASCRIPT BE NAMED? 

This boils down to two limitations: they must contain only letters, digits, or the symbols `$` and `_` (these can also be used in The first character must not be a digit. What's cool is, the dollar sign and underscore can also be used within the characters of the name, and are functionally regular symbols just like letters. 

For convention's sake, when the name contains multiple words, use `camelCase`. Non-latin letters are allowed, but not recommended. This is because it's an international convention to use English in variable names. 

Some outlying words (like `let`, `class`, `return`, and `function` are reserved. Normally, to assign a variable, you need to define it first. Rather than using `let`, you could merely do something like `num = 5`. This is because `use strict` wasn't required of old files, but new ones use it. Trying that kind of assignment in strict mode would throw an error. 

There are constants just like in ruby. For these, we use `const` instead of `let`. You can't reassign constants (in Ruby, you'll just get a warning, but here you'll get a full-on error). Follow the naming convention that you do in Ruby for constants (ALL_CAPS_WITH_UNDERSCORES) after the keyword `const`. This is just the practice, it won't throw an error if you don't. In fact, constants that are calculated DURING run-time (rather than predefined at program start), can be written in typical camel case with a lowercase 0 index. TL;DR : capital-named constants are only used as aliases for "hard-coded" values. 

And, like with all variable-naming, it should represent its clear and obvious meaning for what data is stored. Always use human-redable names, and stay away from short abbreviations like `a`, `b`, or `c`. Make them maximally descriptive while as concise as possible. You'll ultimately be agreeing on the terms within your team and in your own mind. Use extra variables, don't reuse old ones. Surprisingly, doing so can optimize your code. 


# Declare two variables: admin and name.

let admin, name; 


# Assign the value "John" to name.

let name = "John"; 


# Copy the value from name to admin.

admin = name;


# Show the value of admin using alert (must output “John”).


alert(admin); // John 




# JS NUMBERS

Addition, subtraction, multiplication, exponentiation, division, modulus are all the same. Increment is `++` and decrement is `--`. Some examples below: 


```
<script>
let x = 23 + 50;
document.getElementById("demo").innerHTML = x;
</script>
```

```
let x = a + b;
```

```
let x = 5;
x++;
alert(x)
document.getElementById("demo").innerHTML = z;                  # This one is my favorite because I did the `alert(x)` bit from memory :) 
```

* The numbers (in an arithmetic operation) are called operands.

* The operation (to be performed between the two operands) is defined by an operator.

* x ** y produces the same result as Math.pow(x,y):

* PEMDAS should apply. 

* There is only one number type in JS, called simply Number. Any number, whether integer or decimal, will be of this type. 

* If data is declared using `form`, it's most likely a string. Sometimes, `let` will declare a string. 

* Note: 


```
let myNumber = "74";
myNumber += 3;
``` 

will return 743. To convert the "74" into a number, just do this: 


```
let myNumber = "74";
myNumber = Number(myNumber) + 3;
``` 

* For string concatenation: 


```
let s = "my" + "string";
alert(s); // mystring
```




# Fun Lil Cheat Sheets

If I ever want to round something to the nearest decimal: 

```
const lotsOfDecimal = 1.766584958675746364;
lotsOfDecimal;
const twoDecimalPlaces = lotsOfDecimal.toFixed(2);
twoDecimalPlaces;
```


image.png
image.png


```
const btn = document.querySelector("button");
const txt = document.querySelector("p");

btn.addEventListener("click", updateBtn);

function updateBtn() {
  if (btn.textContent === "Start machine") {
    btn.textContent = "Stop machine";
    txt.textContent = "The machine has started!";
  } else {
    btn.textContent = "Start machine";
    txt.textContent = "The machine is stopped.";
  }
}
```

* An operator is unary if it has one operand, binary if it has 2.

* In the unary form of `+` assigned to a single value, doesn't do anything to numbers. If it's not a number though, it converts it to a number. For instance `alert( +true )` will return "1". In fact, it's effectively doing the same thing as `Number()`, but shorter. You can even do this with concatenated strings, like so: 


```
let apples = "2";
let oranges = "3";
alert( apples + oranges ); // "23", the binary plus concatenates strings, so we need to have... 
```

```
let apples = "2";
let oranges = "3";
// both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5
// the longer variant
// alert( Number(apples) + Number(oranges) ); // 5
```

Unary operators have higher precedencethan the binary ones (the ones with two operands on either side). 


# Operator Precedence

See: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence


# Assignment 

The assignment operator `=` is listed in the precedence table with a low priority of 2. So, when we assign a variable like `x = 2 * 2 + 1`, the calculations are done first. 

Something obvious but noting anyway : all operators in JS return a value. `x = value` means that the `x` is assigned the value, and RETURNS it. 


# Chaining Assignments 

Chained assignments evaluate from right to left. For: 

```
let a, b, c;

a = b = c = 2 + 2;

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

`2+2` evaluates first, then assigns in the order c, b, and a. The above is the eqivalent as 

```
c = 2 + 2;
b = c;
a = c;
```

# Modifying In Place

Thankfully, modifying in place looks pretty identical to Ruby's implementation: 

` n = n + 5 ` == ` n += 5 `



# Increment / Decrement

Increasing / decreasing. Can only be done on a variable (like in `counter` below). 

```
let counter = 2;
counter++;        // works the same as counter = counter + 1, but is shorter
alert( counter ); // 3
```

These operators (see also: `--`) can go either at the beginning (prefix form) of or after (postfix form) a variable. They both do the same thing, except the prefix returns the number after it's incremented or decremented, while the postfix returns the original value. To illustrate this: 


```
let counter = 0;                              
counter++;                                               increment once and return the old value 0
++counter;                                               increment once and return the new value (1) incrementing to (2)
alert( counter ); // 2, the lines above did the same
```

# Bitwise Operators

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representations. They aren't specific to JS. For instance, I know at least some of these work in Ruby and Python. 

The comma operator allows us to evaluate several expressions by deliminating them. However, only the last one is returned. The comma has a low precedence. 