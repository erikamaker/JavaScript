Comparisons follow the same conventions as Ruby regarding `>`,`>=`, and `==`. Boolean values seem similar so far (`true` means "positive", `false` means "negative").

```
alert( 2 > 1 ); // true
alert( 2 == 1 ); // false
alert( 2 != 1 ); // true
```

String comparison is very different in JS than in Ruby. It uses something called the "lexicographical" order, in which strings are compared letter-by-letter.

```
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee'); // true
alert('Bee' > 'Be'); // true
```

The algorithm is simply:

1. Compare the first characters of both strings.
2. If the first chracacter from the first string is greater (further along in the alphabet) or less than the other string's, then it's greater (or less) than the second.
3. Otherwise, if both strings' first characters are the same, compare the second characters similarly.
4. Repeat until end of either string.
5. If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.

Please note that lower case letters are not equal to their capital counterparts. In fact, the lowercase is greater, since it has a greater index in the overal lexicographical scheme, specifically Unicode.


# Comparing Different Types

JavaScript converts values of different types into numbers. For instance, a `2` will become an integer, and `01` would become `1` specifically. For boolean values, `true` is `1` and `false` is `0`.

Something funny about that: it's possible for two values to be equal, while one of them is `true` and the other is `false` as a boolean:

```
let a = 0;
alert( Boolean(a)); // false

let be = "0";
alert( Boolean(b)); // true

alert(a == b); true
```

It seems weird, but what's happening is that an equality check is converting values using the numeric conversion we discussed earlier, while the Boolean conversion is using a different set of rules.


# Strict Equality

A regular equality check `==` can't differentiate from `0` and `false`. If you try to check a `0` or an empty string against `false`, it will evaluate to `true`. This happens because operands of different types are all converted to numbers by the equality operator. So, an empty string, or negative boolean value, return `0`.

If we wanted to convert something like `0` with `false`, we'd use the strict equality operator: `===`. This effectively does the same thing as an equality operator, but it doesn't convert the types to integers first. So, in other words, if `a` and `b` are of different types, then ` a === b ` will return `false`:


```
alert(0 === false); // false, ya dingus--they're two different types.
```

Note: to use a string "non-equality" operator, just use `!==`. It's pretty intuitive to a Rubyist so far.

There is a special rule for `==`: `null` and `undefined` mean the same thing, but only in an equality operator (not a strict-equality operator).

`null/undefined` are converted to numbers. `null` becomes `0` while `undefined` becomes `NaN` ("Not a Number").

```
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true
```

The last return states that `null` is greater than or equal to zero, so we'd expect on eof the above comparisons to be true, except they're both false. This is because the equality check and comparisons work differently. Remember that comaprisons convert `null` to a number (`0`), which is why the top line is true (that is to say, it's true that it's false). At the same time, `null` and `undefined` equal each other and don't equal anything else, which is why `null == 0` returns false.

Comparisons 1 and 2 return `false` because `undefined` gets converted to `NaN`, which is a special numeric value that always returns `false` in comparisons. This makes sense, as logically `NaN` is the false value of trying to compare something that isn't a number. The equality check on 3 returns `false` because `undefined` only ever EQUALS (not returns, but EQUALS) `null`, itself, and nothing else.

The text says not to worry about remembering these peculiarities all the time, because they'll gradually bcome more familiar over time. The main rule of thumb is, treat any comparison with `undefined/null` except the `===` operator for now. Don't use comparisons with a variable that may be `null` or `undefined` for now. If a variable can potentially have these values in your code, check for them separately.


# Conditional Statements

In JS, we use `if`, `else`, `else if` and `switch`. Check out the following examples:



```
if (hour < 18) {
  greeting = "Good day";
}
```

```
if (hour < 18) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

```
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

Some boiler plates:

```
switch (expression) {
  case choice1:
    // code to run if expression matches choice1
    break;
  case choice2:
    // code to run if expression matches choice2
    break;
  // include as many cases as needed
  default:
    // code to run if none of the above cases match
}
```

```
if (condition1) {
  // code to run if condition1 is true
} else if (condition2) {
  // code to run if condition1 is false and condition2 is true
} else {
  // code to run if none of the above conditions are true
}
```

Oh, and the ternary operation is pretty much identical to Ruby.

```
condition ? expression-if-true : expression-if-false
```



Here's an example of what declaring a variable `days` that is assigned a number based on a string condition:

```
  let days = 31;
  if (choice === 'February') {
    days = 28;
  } else if (choice === 'April' || choice === 'June' || choice === 'September'|| choice === 'November') {
    days = 30;
  }
```

```
let year = prompt('In which year was ECMAScript-2015 specification published?', '');

if (year == 2015) alert( 'You are right!' );
```

```
let company = prompt('Which company created JavaScript?', '');

if (company == 'Netscape') {
  alert('Right!');
} else {
  alert('Wrong.');
}
```

```
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}
```


```
switch (browser) {
  case 'Edge':
    alert( "You've got the Edge!" );
    break;

  case 'Chrome':
  case 'Firefox':
  case 'Safari':
  case 'Opera':
    alert( 'Okay we support these browsers too' );
    break;

  default:
    alert( 'We hope that this page looks ok!' );
}
```

and

```
if(browser == 'Edge') {
  alert("You've got the Edge!");
} else if (browser == 'Chrome'
 || browser == 'Firefox'
 || browser == 'Safari'
 || browser == 'Opera') {
  alert( 'Okay we support these browsers too' );
} else {
  alert( 'We hope that this page looks ok!' );
}
```

Are virtually equivalent. So are these:



```
let a = +prompt('a?', '');

if (a == 0) {
  alert( 0 );
}
if (a == 1) {
  alert( 1 );
}

if (a == 2 || a == 3) {
  alert( '2,3' );
}
```

and

```
let a = +prompt('a?', '');

switch (a) {
  case 0:
    alert( 0 );
    break;

  case 1:
    alert( 1 );
    break;

  case 2:
  case 3:
    alert( '2,3' );
    break;
}
```


















Officially, JavaScript is called “ECMAScript”.