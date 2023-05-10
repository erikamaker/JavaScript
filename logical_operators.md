# OR ( || )

There are four logical operators in JS. They look similar to Ruby's (`||` / `OR`, `&&` / `AND`, `!` / `NOT`), with one new one that I've not used before: `??`, or "nullish coalescing" (which we're not even covering today).

Though these are "logical" operators, they're applicable across value types, not just booleans. Consider the following:

```
result = a || b;
```

In classical programming (also known as procedural programming, focused on functions rather than object models), the `OR` operator manipulates only boolean values. If any arguments are true, it'll return `true`, else `false`.

In JS, it's a little different, and has more applications. Consider the following examples:

```
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
```

If an operand isn't a boolean, it's converted to one. For instance, `1` is `true`, and `0` is `false` (just as I suspected).

Example using `if`

```
let hour = 9;

if (hour < 10 || hour > 18) {
  alert( 'The office is closed.' );
}
```

And using multiple operands and conditions:

```
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert( 'The office is closed.' ); // it is the weekend
}
```

The `OR` operator finds the first "truthy" value.

In JavaScript, a "truthy" value is a value that is considered true when evaluated in a boolean context. This means that a truthy value is any value that is not explicitly false, such as the boolean value false, null, undefined, 0, -0, NaN, or an empty string (''). `Null` is considered falsy in JavaScript, along with `false`, `0`, `undefined`, `NaN`, and the empty string `('')`. Any other value that is not strictly equal to one of these falsy values is considered truthy.

In a chain of several `OR`ed values, like `result = value1 || value 2 || value3;`, the compiler returns the first true value. If they're all false, the last `false` value will return (e.g. / i.e. `value3`)

For instance:

```
alert( 1 || 0 ); // 1 (1 is truthy)

alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)

alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
```


This uniqueness in JS leads to some interesting usage compared with procedural program's `OR`. For instance, you could have variables that are optional, like:

```
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
```

In the above example, you'd expect a value like someone's first and last name to be obligatory, or truthy, but the programmer decides what matters at the end of the day. As we can see here, the first truthy value is `"SuperCorder"`. If all variables, including the nickName, were falsy, then `"Anonymous"` would have shown up instead.

A "short-circuit" evaluation is when || processes its arguments until the first truthy value is reached, and then the value is returned immediately, without even touching the other argument. For instance:

```
true || alert("not printed");
false || alert("printed");
```

Only the second line of this example would return, because the first one stops at `true` before `"not printed"` can be passed to the `alert` function.


# AND ( && )


