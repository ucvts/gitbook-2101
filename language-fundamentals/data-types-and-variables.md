# Data Types and Variables

## Data Types

JavaScript is a loosely typed language, which means that you don't need to specify the type of data that will be stored in a variable. Likewise, you can always change your mind later about what type of data a variable stores. That being said, there are seven primitive data types.

* `number`
* `string`
* `boolean`
* `null`
* `undefined`
* `object`
* `symbol`

### Numbers

JavaScript is unique in that it doesn't distinguish between integers and floating-point values. Most languages have separate data types for each, but JavaScript has only one: `number`. 

| Range of Values |
| :--- |
| −9,007,199,254,740,992 to 9,007,199,254,740,992 |

```javascript
1        // these are numeric literals
1.2
```

### Strings

A `string` is a sequence of characters. These characters can be any combination of letters, numbers, symbols, and whitespace.

```javascript
"hello"        // these are string literals
"goodbye"
"123"
"abc 123"
""             // this is an empty string, but a string nonetheless
```

Strings need to be surrounded by quotes. And while single quotes are acceptable, it's better practice to use double-quotes.

### Booleans

A `boolean` represents either `true` or `false`. These reserved words are written directly into your code to convey these meanings.

```javascript
true
false
```

All variables can be implicitly converted to a `boolean` value, which we'll see in more detail later. We'll also get more familiar with these variables as we learn about control structures and expressions in the next couple sections.

### Null and Undefined

`null` is a special value that implies the absence of a value. Although sometimes referred to as a special `object` type \(meaning no object at all\), `null` is more accurately categorized as the only member of its own type.

`undefined` implies the absence of a value, too, but to a greater extent. It represents the value of a variable that has not yet been initialized. While they often mean the same thing, this is an important difference between `null` and `undefined`. `null` is a program-level absence of a value \(usually by design\), while `undefined` is a system-level absence of a value \(usually unexpected\).

## Literals

A literal is a value that is written directly into the source code of a program. Literals can be numbers, booleans, strings, or other less traditional values. As we'll soon see, literals are raw values that are not stored in a variable.

```javascript
12         // a number (the integer 12)
1.2        // a number (the real number 1.2)
"hello"    // a string of text
true       // a boolean
null       // the absence of a value
```

## Variables

A variable is an identifier that refers to information that your program stores. You can create variables and assign certain values to them, which you can later use throughout the course of your program.

{% embed url="https://www.youtube.com/watch?v=QegiVRg0HTE&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

The video touches on a few concepts that we haven't seen yet. Don't worry about the mathematical operators \(we'll see those next!\) or conditional logic. Just focus on how to declare and assign values to variables.

### Declaring Variables

To create a variable, you must first declare it. Then, you have to initialize it. There are three ways in which you can declare a variable in JavaScript.

* `const`
* `let`
* `var`

Each of these declares a variable in a slightly different way.

```javascript
const variableName;
```

`const` is used when you're declaring a read-only variable, which is a variable whose value is set once and never changed.

```javascript
const readOnlyVariable;
const FORMAL_CONSTANT;
```

There's a slight difference between a read-only variable and a formal constant. A constant is something like Pi, whose value is fixed. A read-only variable, once set, shouldn't change; that does not necessarily make it a formal constant.

Formal constants are written in all capital letters \(with words separated by underscores\) to distinguish them from read-only variables.

```javascript
let variableName;
var anotherVariableName;
```

`let` and `var` are used to declare variable whose values might change over time. For now, we'll hold off on the difference between these. Unless you have a good reason, you should avoid using `var`. Stick to using `const` and `let` for your variable declarations.

{% hint style="danger" %}
Do not use `var` unless you have a good reason for doing so. In almost all circumstances, `let` is preferable to `var`. And whenever you're creating a read-only variable, you should be using `const`. If you choose to use `var`, be prepared to justify your rationale!
{% endhint %}

### Initializing Variables

The initialization step involves providing your variables with a starting value. To do so, we use the assignment operators \(i.e., the `=` sign\).

```javascript
const DAYS_PER_WEEK = 7;    // number

let testScore = 94.2;       // number
let studentName = "Sam";    // string
let isSophomore = true;     // boolean

let gpa = null;             // null
let graduationStatus;       // undefined
```

All of these values can be changed or re-assigned in the same way, with the exception of `DAYS_PER_WEEK`. That is a constant, which is read-only.

### Naming Conventions

A variable name should begin with a lowercase letter \(the lone exception being constants\). It should adhere to camel casing, which means that subsequent words after the first are individually capitalized.

```javascript
let elapsedTimeInDays;
```

Take note of the words in the variable: _elapsed_, _time_, _in_, and _days_. Elapsed is all lowercase, and each subsequent word has its first letter capitalized.

Constants, of course, are different. All words are capitalized, but are separated with underscores.

#### Revealing Intent

Either way, though, the variable name should convey meaning.

```javascript
let x;    // elapsed time in days
```

The variable name, `x`, offers nothing in terms of intent or meaning. A much cleaner name would communicate the purpose of the variable and its contents.

```javascript
let elapsedTimeInDays;
```

Sometimes a compiler might complain about using the same variable. Once you declare a variable, you cannot reuse that name for another variable in the same scope. It can be tempting to alter the variable names in an arbitrary way to satisfy the compiler. Consider the following example.

```javascript
let distance1;    // in inches
let distance2;    // in centimeters
```

You have two different variables. So, you should have two different names that convey two different meanings. A better decision would be to clarify the intent.

```javascript
let distanceInInches;
let distanceInCentimeters;
```

Now, you won't be confused if you encounter these variables hundreds of lines of code later. Their purpose and the values they hold will be abundantly clear.

#### Pronounceable and Searchable

Favor variable names that are human-readable and pronounceable.

```javascript
let cmperhr;    // centimeters per hour
```

Maybe you can figure out the intention behind this name, but it certainly would take a second or two. Cut out the ambiguity and potential misinterpretation.

```javascript
let centimetersPerHour;
```

You should also choose variable names that are easily searchable in a potentially large codebase.

```javascript
let i;    // test score
```

If you need to find a variable, you can use `Ctrl+F` or `Cmd+F` to make your life easier. However, a variable like `i` will likely show up in a number of phrases other than the variable itself. Choose a more distinct and search-friendly name.

```javascript
let testScore;
```

Let's try out some of the skills we've covered. If this feels easy and redundant, that's great! It means you're picking up the material quickly. If you're still a little confused, that's alright, too. Re-read this page and re-watch these videos as many times as it takes for the information to stick!

{% embed url="https://www.youtube.com/watch?v=PaT7tLfpZEI&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

Remember, `var` is outdated. The concepts covered in this video are important, but it's showing its age a bit in its use of `var`. Always use `let` and `const` unless you have a really good reason not to.

## Comments

Comments serve to clarify the meaning behind one or more lines of code. Like whitespace, comments are ignored by the interpreter and they have no effect on the execution of the program. They're strictly for human consumption. There are two types of comments: single-line comments, and multi-line comments.

### Single-line Comments

A single-line comment is typically used for concise descriptions. Single-line comments begin with the `//` compound symbol.

```java
// this is a single-line comment
```

Of course, you can use consecutive single-line comments to span multiple lines.

```java
// now this is a multi-line comment
// made from two single-line comments
```

Perfectly valid, but there's already a multi-line comment for that purpose.

### Multi-line Comments

A multi-line comment is typically used for longer descriptions of more complex segments of code. Unlike a single-line comment that has just an opening marker, multi-line comments have both opening and closing markers. It starts with `/*` and ends with `*/`.

```java
/*
 * this comment spans
 * multiple lines
 */
```

Some software developers have argued that good code is self-documenting, and to some extent that is true. Poorly written code is often unclear or cluttered, while high quality code doesn't require an abundance of comments occupying the vertical real estate. If it's written well, its meaning will be clear. Comments do, however, add value when used appropriately. If the code itself documents the how, then the comments help to communicate the why. Sample usages, expected inputs and outputs, possible future improvements, and implementation-specific tradeoffs are all great examples of informative and clarifying comments.

