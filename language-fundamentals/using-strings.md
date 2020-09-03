# Using Strings

## Strings, Revisited

We've already discussed strings in the context of JavaScript's seven primitive data types. Strings are special, in that while they are primitive data types, they are also objects. And objects come with a lot of cool built-in functionality.

{% embed url="https://youtu.be/Xxk9UP1uO5g" %}

As we've seen, `String` is a built-in object in JavaScript that provides some helpful properties and methods that you can use with strings. To use the `String` object, you reference a variable whose data type is `string`. From there, you can access whatever properties and methods you need.

```javascript
let str = "hello, world";

// now you can use properties and methods
//    str.property
//    str.someMethod()
```

### Properties

There's really only one property of strings that is useful, and that's the `length` property. This tells you how many characters are contained in a string.

```javascript
let str = "hello, world";
let len = str.length;        // len is 12
```

### Methods

There are quite a few methods available for strings, and we're going to walk through a few of the more commonly used ones.

* `charAt(index)`

The `charAt` method returns a single character located at the specific `index`. String indices are 0-based, which means the first character in the string is located at the 0th index.

```javascript
let word = "hello";
let letter = word.charAt(0);    // letter is "h"
```

* `concat(string1, ...)`

The `concat` method concatenates \(or combines\) one or more strings together. You can enter as many strings as you'd like, and each of them will be combined.

```javascript
let one = "hello, ";
let two = "world!";
let three = one.concat(two);    // "hello, world!"

// this doesn't change the values of one or two, it just uses them to
// create a new string that is stored in three
```

There are a couple more ways to concatenate strings, and some might argue they're easier and more intuitive. You can use the `+` operator to combine two or more strings.

```text
let one = "hello";
let two = "world";

console.log(one + ", " + world + "!");    // prints "hello, world!"
```

You can also use something called template strings. Until now, we've always wrapped our strings with double-quotes. And unless you're using template strings, you should continue to do that. A template string uses back tick characters.

```javascript
let template = `a string with back ticks`;
```

The benefit of template strings is that you can plug in values into placeholders without the need for repeated concatenation with the `+` operator. Consider the following code segment.

{% code title="strings.js" %}
```javascript
let furniture = "couch";
let capacity = 4;
let message = "My new " + furniture + " has seating for " + capacity + "!";

console.log(message);
```
{% endcode %}

```text
$ node strings.js
My new couch has seating for 4!
```

Simple enough, but all the concatenation can become tedious. Let's try it with a template string.

```javascript
let furniture = "couch";
let capacity = 4;
let message = `My new ${furniture} has seating for ${capacity}!`;

console.log(message);
```

We use back ticks instead of double-quotes, and we plug our values into the string directly. To do this, you use `${}` and put your variables or expressions inside of the braces. It seems trivial, but this can actually save you a lot of headaches when formatting printed messages to the console.

* `endsWith(suffix)`

The `endsWith` method returns `true` if the string ends with the `suffix` provided. If it doesn't, it returns `false`.

```javascript
let str = "Welcome to AP Computer Science Principles!";
let end1 = str.endsWith("Principles!");    // true
let end2 = str.endsWith("!");              // true
let end3 = str.endsWith("AP");             // false
```

* `includes(substring)`

The `includes` method returns `true` if the `substring` is found within the original string. If it isn't, it returns `false`. The `position` is optional, and tells the method where in the original string to start searching.

```javascript
let orig = "hello, world";
let substr = "world";
let doesInclude = orig.includes(substr);
```

* `indexOf(substring)`

The `indexOf` method returns the index of the first occurrence of `substring` in the original string. If the `substring` is not found, it returns `-1`.

```javascript
let orig = "AIT is located in Scotch Plains, NJ.";
let foundAt = orig.indexOf("Scotch Plains");        // index 18
```

* `lastIndexOf(substring)`

The `lastIndexOf` method returns the index of the last occurrence of `substring` in the original string. The search is performed from the end of the string, moving towards the beginning. If the `substring` is not found, it returns `-1`.

```javascript
let orig = "AIT is located in Scotch Plains, NJ."
let foundAt = orig.lastIndexOf("i");                // index 28
```

* `replace(substring, replacement)`

The `replace` method replaces the first occurrence of `substring` in the original string with `replacement`. You can modify this to use pattern-matching and replace all occurrences.

```javascript
let original = "hello";
let changed = original.replace("e", "x");    // "hxllo"
```

* `startsWith(prefix)`

The `startsWith` method returns `true` if the string starts with the `prefix` provided. If it doesn't, it returns `false`.

```javascript
let str = "Welcome to AP Computer Science Principles!";
let starts1 = str.startsWith("Welcome");    // true
let starts2 = str.startsWith("W");          // true
let starts3 = str.startsWith("AP");         // false
```

* `substring(start, end)`

The `substring` method returns the portion of the original string between the `start` and `stop` indices. If an `end` index isn't provided, the method uses the end of the string. The `start` index is inclusive, but the `end` index is not.

```javascript
let str = "hello, world";
let sub1 = str.substring(0, 5);    // "hello"
let sub2 = str.substring(7);       // "world"
```

* `toLowerCase()`

The `toLowerCase` method returns the original string to all lowercase letters. This is returned in a new string without modifying the original.

```javascript
let original = "HELLO, WORLD";
let lower = original.toLowerCase();    // "hello, world"
```

* `toUpperCase()`

The `toUpperCase` method returns the original string to all capital letters. This is returned in a new string without modifying the original.

```javascript
let original = "hello, world";
let upper = original.toUpperCase();    // "HELLO, WORLD"
```

* `trim()`

The `trim` method returns a string without any leading or trailing spaces. The original string is unchanged.

```javascript
let original = "   hello, world   ";
let trimmed = original.trim();            // "hello, world"
```

You can look at examples of these \(and many more\) methods in the [full documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

## Concatenation

Let's briefly revisit operators from the last section. We haphazardly worked our way through that video, as I highlighted the sections to focus on. We skipped the String operator segment at the end, but with our newfound knowledge of strings and the String object, it's time to circle back.

{% embed url="https://www.youtube.com/watch?v=ScsXYh4yxew&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla&t=376" %}

Concatenation is a pretty simple concept. It creates one `string` from two or more smaller ones.

```javascript
const first = "Ryan";
const space = " ";
const last = "Wilson";
const name = first + space + last;

console.log(name);    // logs "Ryan Wilson" to the console
```

There is a special type of string called a template string, which uses back ticks \(````````\) rather than single- or double-quotes. This allows you to insert variables directly into the string without concatenating.

{% embed url="https://www.youtube.com/watch?v=G3pULNtd3p8&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

```javascript
const name = "Paula";
const greeting = `Hello, ${name}!`;

// we use ${} and put a variable inside it to plug that value
// directly into the string

console.log(greeting);    // logs "Hello, Paula!" to the console
```

As always, let's get a little practice! 

{% embed url="https://www.youtube.com/watch?v=iLuCD75TGvg&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla&t=316" %}

Maybe a little more than usual. Sorry!

{% embed url="https://www.youtube.com/watch?v=edKu-Scx8F4&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

## Escape Sequences

Use this table to reference different escape sequences in JavaScript and the characters they represent.

| **Escape Sequence** | **Description** |
| :--- | :--- |
| `\t` | A tab character. |
| `\b` | A backspace character. |
| `\n` | A newline character. |
| `\'` | A single-quote character. |
| `\"` | A double-quote character. |
| `\\` | A backslash character. |

Time for more practice using `string`s! Yup, you guessed it...another problem set.

