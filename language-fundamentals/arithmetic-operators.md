# Arithmetic Operators

## Simple Math

There are six simple arithmetic operators, most of which should be familiar to you.

| **Operator** | **Description** |
| :--- | :--- |
| `+` | Addition operator. |
| `-` | Subtraction operator. |
| `*` | Multiplication operator. |
| `/` | Division operator. |
| `%` | Integer remainder operator. |
| `**` | Exponentiation operator. |

Addition works just like it would in math.

```javascript
let a = 1;
let b = 2;
let c = a + b;    // the sum of a and b is computed and stored in c
```

Subtraction is equally straightforward.

```javascript
let a = 3;
let b = 2;
let c = a - b;    // the difference between a and b is computed and stored
                  // in c
```

Multiplication, too, is as expected. No surprises here.

```javascript
let a = 2;
let b = 3;
let c = a * b;    // the product of a and b is computed and stored in c
```

Division isn't breaking the trend.

```javascript
let a = 3.0;
let b = 2.0;
let c = a / b;    // 1.5 is stored in c
```

You may or may not have come across the modulo operator, but it computes the remainder of two numbers. It only works with integers.

```javascript
let a = 3;
let b = 2;
let c = a % b;    // the remainder is 1
```

The exponentiation operator is a relatively new addition to the language, arriving in 2016 with the release of ES6.

```javascript
let a = 2;
let b = 3;
let c = a ** b;    // 2 raised to the 3rd power is 8
```

Sometimes it helps to visualize how this works in practice to really wrap your head around these concepts and how they're used. This video covers a bit more than we really need right now, so focus only on the arithmetic and assignment operators. We'll come back to the comparison operators soon.

{% embed url="https://www.youtube.com/watch?v=ScsXYh4yxew&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

### Shortcut Assignment

We've seen how to assign a value to a variable in the previous section.

```javascript
let x = 1;
```

It's pretty common to have to update a variable in terms of its current value.

```javascript
let x = 5;
x = x + 2;    // x is now 7
```

An expression like this is evaluated right to left. The current value of `x` is `2`. So, first the expression `x + 2` is evaluated. Since `x` is currently `5`, the expression results in `5 + 2`. This sum \(i.e., `7`\) is then stored in `x` \(overwriting its previous value\).

You can condense this using a shortcut operator. And this holds true for each of the six arithmetic operators.

```javascript
x += 2;     // equivalent to: x = x + 2
x -= 2;     // equivalent to: x = x - 2
x *= 2;     // equivalent to: x = x * 2
x /= 2;     // equivalent to: x = x / 2
x %= 2;     // equivalent to: x = x % 2
x **= 2;    // equivalent to: x = x ** 2
```

Just like last time, let's jump into some practice. Focus only on the first two minutes, which covers the arithmetic and assignment operators. We'll revisit the comparison and `string` operations in a later section.

{% embed url="https://youtu.be/iLuCD75TGvg" %}

### Increment and Decrement

Increasing or decreasing the value of a variable by 1 is a very common practice in programming. So common, in fact, that most languages provide a specific operator for doing this.

```javascript
let x = 1;
x++;               // equivalent to x = x + 1 (or x += 1)

console.log(x);    // prints 2
```

Likewise, the same can be done to decrease the vale of a variable.

```javascript
let y = 1;
y--;               // equivalent to x = x - 1 (or x -= 1)

console.log(y);    // prints 0
```

Let's take a closer look together.

{% embed url="https://www.youtube.com/watch?v=d4W6-mphL7c&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

#### Pre- and Post-Increment and Decrement

The `++` and `--` operator comes in two different flavors: pre-increment and decrement, as well as post-increment and decrement. The end result is the same, but there is an important distinction between them.

Pre-increment and decrement puts the operator before the operand, whereas post-increment and decrement places the operator after the operand. Consider the following code segment.

{% code title="increment.js" %}
```javascript
let a = 1;
console.log(++a);    // pre-increment
console.log(a);

let b = 1;
console.log(b++);    // post-increment
console.log(b);
```
{% endcode %}

At first glance, you might expect this code to produce the following output.

```text
$ node increment.js
2
2
2
2
```

Both `a` and `b` are, indeed, incremented. However, that incrementation takes place at different times. In the first code segment \(on lines 1-3\), the value of `a` is increased before the `console.log` statement is executed. However, in the second code segment \(on lines 5-7\), the value of `a` is increased after the `console.log` statement is executed.

{% code title="increment.js" %}
```javascript
let a = 1;
console.log(++a);    // prints 2 (because a is already incremented)
console.log(a);      // prints 2

let b = 1;
console.log(b++);    // prints 1 (because b hasn't yet been incremented)
console.log(b);      // prints 2 (because now be has been incremented)
```
{% endcode %}

```text
$ node increment.js
2
2
1
2
```

The same is, of course, true of decrementing a variable. And it also carries over into arithmetic expressions. Consider the following code segment.

{% code title="decrement.js" %}
```javascript
let a = 2;
let b = 3;
let c = a-- * --b;

console.log(c);
console.log(a);
console.log(b);
```
{% endcode %}

Because of the way the pre- versus post-decrementation works, the results might be a little surprising. `a` is only decreased after the expression is evaluated, but `b` is decreased beforehand.

```javascript
let c = 2 * 2;    // a is unchanged, but b is decreased by 1

// a is only decreased after the expression is done evaluating
```

Therefore, when we run this code, we see the following output.

```text
$ node decrement.js
4
1
2
```

## Conversions

JavaScript is pretty flexible about data types, and you can freely convert from one to the other. Sometimes this is even done for you automatically. If it isn't done automatically, you can use these explicit type conversion functions.

* `Number()`
* `String()`
* `Boolean()`

Inside of the parentheses, you put the value that you want to convert to that data type.

```javascript
let x = "7";          // "7"
let y = Number(x);    // 7
```

Originally, the value was saved as a string: `"7"`. After converting it, we changed its internal representation to a number. You can do similar things with strings and booleans, too.

```javascript
let x = 7;             // 7
let y = String(x);     // "7"
let z = Boolean(x);    // true
```

You might see some craftier ways of doing this, as well.

```javascript
let x = 7;          // 7
x = x + "";         // "7" -- this does the same as String(x)

let y = "7";        // "7"
y = +y;             // 7 -- this does the same as Number(y)

let z = "7";        // "7"
z = !!z;            // true -- this does the same as Boolean(z)
```

You'll learn more about these and other operators in the next section. For reference, here are some common conversions from the value on the left to the data types on the right.

| Value | Number | String | Boolean |
| :--- | :--- | :--- | :--- |
| `undefined` | `NaN` | `"undefined"` | `false` |
| `null` | `0` | `"null"` | `false` |
| `true` | `1` | `"true"` | N/A |
| `false` | `0` | `"false"` | N/A |
| `""` | `0` | N/A | `false` |
| `"1.2"` | `1.2` | N/A | `true` |
| `"one"` | `NaN` | N/A | `true` |
| `0` | N/A | `"0"` | `false` |
| `-0` | N/A | `"0"` | `false` |
| `NaN` | N/A | `"NaN"` | `false` |
| `Infinity` | N/A | `"Infinity"` | `true` |
| `-Infinity` | N/A | `"-Infinity"` | `true` |
| `1` | N/A | `"1"` | `true` |

## Determining Type

We'll learn about plenty of operators in the next section, but this one is concerned only with telling you what type a value or variable is. It's called the `typeof` operator.

```javascript
let x = 7;
let y = "hello";
let z = true;

let a = null;
let b;
```

If you're unsure of a variable's type before performing an operation, you can check first.

```javascript
typeof x    // "number"
typeof y    // "string"
typeof z    // "boolean"

typeof a    // "object" -- weird, right?
typeof b    // "undefined"
```

Everything is about as expected, with the exception of `typeof a`. The `typeof` operator returns `"object"` for `null` types. More generally, `null` refers to the absence of a value. Specifically, though, it refers to the absence of an `object`.

