# Functions

## Black Boxes

Functions go by a host of different names depending on the manner in which you're using them or the language in which you're programming. Many developers use these overlapping terminologies interchangeably, so it is important you understand they're more or less referring to the same idea.

* Functions
* Methods
* Procedures
* Subroutines

Although there are sometimes subtle differences between these terms, we're going to use them interchangeably for now. These terms all refer to predefined blocks of code that can be executed any number of times within a program. When we _use_ a function, we are said to be _calling_ or invoking it. Functions are designed to perform very specific, but also very customizable tasks.

Functions are often referred to as black boxes. Let's take a look at some built-in functions we've already seen and used.

* `log` \(as in, `console.log`\)
* `toLocaleString`
* `isNaN`
* `isInteger`

We've all used these functions. Do we know how they work, though? Sure, we understand what they're supposed to do and how we can use them in our programs. Everyone knows that `console.log` prints text to the screen, but very few people truly understand the implementation details behind doing this. Is it really necessary to understand the inner workings of `console.log` to use it? Of course not!

And that's exactly what we mean when we refer to functions as black boxes. Some input goes into the box, and some output comes out of the box. We don't really need to know what happens inside of the box to produce that output.

Next, we'll learn how to create our own functions. And, naturally, the implementation details of these will take on a much greater importance.

## Built-in Functions

Most built-in functions are defined in an object. Technically, this makes them methods, but that's not a critical detail. Functions that we define in our source files are called exactly that: functions. Functions that are defined as properties of an object are called methods.

### String

There are a great deal of `String` methods available to us. You don't need to memorize each and every one of them, but you should be familiar with the more common ones. We've already used several of these!

* `charAt`
* `endsWith`
* `includes`
* `indexOf`
* `lastIndexOf`
* `replace`
* `split`
* `substring`
* `toLowerCase`
* `toUpperCase`
* `trim`

You can check out [the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) for these and many more methods.

### Number

Number methods shouldn't be entirely foreign, either. We've used quite a few of these already. Familiarize yourself with their usage.

* `isInteger`
* `isNaN`
* `isSafeInteger`
* `parseFloat`
* `parseInt`
* `toLocaleString`

You can check out [the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) of these and many more methods.

## Defining Functions

Remember, a function is a reusable block of code that performs a specific task. Before we dive into how to create our own functions, let's take a minute to discuss when it makes sense to do so.

Reusable is an important keyword. If you recognize that you're doing the same thing \(or very similar things\) over and over in a program, then you can probably capture that behavior in a function. This would allow you to write the code once, and then reference that block of code by name.

Next, we have specificity. Functions are designed to perform a specific task. As you're defining a function, it's important to make sure you aren't being too ambitious. The more things your function does, the less modular and reusable it becomes. To paraphrase the Unix philosophy, write functions that do one thing and do it well.

{% embed url="https://www.youtube.com/watch?v=N8ap4k\_1QEQ" %}

### Function Declarations

The simplest way to create a function is using the function declaration syntax.

```javascript
function sayHello() {
    console.log("hello!");
}
```

Just like variables are declared using `let` or `const`, functions are declared using the `function` keyword. After the `function` keyword, we give our function a name just like we would a variable. We can use this name to reference or call our function from somewhere else in our code. The parentheses are empty for now, but later we'll learn how to use them to allow our functions to accept input.

Suppose we declared our sayHello function, we could use it any number of times and the code would execute the same each time.

```javascript
function sayHello() {
    console.log("hello!");
}

for (let i = 0; i < 5; i++) {
    sayHello();
}
```

If we run this code, what's going to happen?

```text
hello!
hello!
hello!
hello!
hello!
```

The `for` loop executes five times, and each time it calls the say`H`ello function. The `sayHello` function, in turn, prints `hello!` to the console.

Interestingly, we could have declared the `sayHello` function anywhere we wanted and the code would have worked the same.

```javascript
for (let i = 0; i < 5; i++) {
    sayHello();
}

function sayHello() {
    console.log("hello!");
}
```

Like `var`, function declarations are hoisted to the top of the file, too.

### Function Expressions

Function expressions do a lot of the same things as function declarations. They're created a little differently, though, and there are a few subtleties we'll need to address.

```javascript
let sayHello = function() {
    console.log("hello!");
};
```

From a behavioral standpoint, this is almost the same. We can still reference this function by its name \(`sayHello`\), and it'll still print `hello!` to the console. Syntactically, there are a few differences.

First, we're declaring this function as if it were a variable. We use the `let` keyword and give it a name. When we define the function itself, we don't need to rename it. We just use the `function` keyword along with the parentheses. Lastly, we end the expression with a semicolon just like any other variable declaration.

Let's use the function and see if there's any difference. We'll add in our `for` loop.

```javascript
let sayHello = function() {
    console.log("hello!");
};

for (let i = 0; i < 5; i++) {
    sayHello();
}
```

And now we'll run our code.

```text
hello!
hello!
hello!
hello!
hello!
```

Nope! Looks exactly the same. So what's the difference? And more importantly, what's the point in having these two formats for defining functions?

Remember how function declarations were hoisted?

```javascript
for (let i = 0; i < 5; i++) {
    sayHello();
}

let sayHello = function() {
    console.log("hello!");
};
```

Well, function expressions are not. This program would crash because the `sayHello` function cannot be invoked before it is defined.

In most cases, it's better practice to use function declarations. They're syntactically more visually appealing, and usually do the job just as well as an expression would. However, there are a couple cases where a function expression is a better fit.

* As arguments to other functions \(more on this later\)
* When we need to conditionally define a function

Let's take a look at an example of the latter.

```javascript
const day = /* some user input, either A or B */;

let printReminder = (day === "A")
    ? function() {
        console.log("Bring your math textbook!");
    }
    : function() {
        console.log("Leave your math textbook at home.");
    };
```

This could not have been achieved using a function declaration, so an expression is more suitable to the task at hand.

## Parameters

Parameters provide a way for us to let our functions accept input. It makes our functions more customizable, and far more dynamic. Remember the sayHello function? It was pretty simple, and also pretty boring.

What if we wanted to print something other than `hello!` to the screen? Sure, we can create a few more functions that printed other messages, but this isn't scalable. Instead, we can create a single function that prints any number of messages to the console.

```javascript
function printMessage(message) {

}
```

`message` is a parameter, which serves as a placeholder for some value that will be passed into our function. Within our function, message is just a variable and we can treat it and use it as such.

```javascript
function printMessage(message) {
    console.log(message);
}
```

Now, whatever value is passed to our function will be printed to the console.

```javascript
function printMessage(message) {
    console.log(message);
}

printMessage("hello.");
printMessage("how are you?");
printMessage("goodbye.");
```

We passed three different values \(called arguments\) to our function, and each time our function printed that value to the console. Its behavior is predictable, but also dynamic. It can handle whatever input we decide to give it.

```text
hello.
how are you?
goodbye.
```

If we want to allow our function to accept multiple input values, we can setup multiple parameters separated by commas.

```javascript
function add(a, b, c) {
    let sum = a + b + c;
    
    console.log(sum);
}
```

We can pass any combination of numbers to our `add` function.

```javascript
function add(a, b, c) {
    let sum = a + b + c;
    
    console.log(sum);
}

add(1, 2, 3);
add(10, 20, 30);
add(-1, -3, -3);
```

And it'll happily print the sum.

```text
6
60
-7
```

## Return Statements

Functions can accept input via parameters. It's only logical that they can produce some form of output, too. The way in which functions do this is via return statements.

A return statement transfers some value to the point in the code where the function was called. Let's refactor our `add` function.

```javascript
function add(a, b, c) {
    return a + b + c;
}
```

Our add function still computes the sum, but it no longer prints that value to the console. Instead, it returns the value to the caller. It's the responsibility of the caller of the function to use the return value.

```javascript
function add(a, b, c) {
    return a + b + c;
}

add(1, 2, 3);              // function returns but does nothing with return value

let sum = add(2, 4, 6);    // function saves return value in variable

// now our program can do whatever it needs to do with sum
```

{% embed url="https://www.youtube.com/watch?v=ZAd0KY9Ps-k&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

## Variable Scope

We've gone through global and block scope, but we'll review them again here. There is a third type called function scope, which applies to code written within a single function.

```javascript
var a = "a";
let b = "b";
const c = "c";

function doSomething(x, y) {
    var d = "d";
    const e = "e";
    let f = "f";
    
    if (name === "Ryan") {
        var g = "g";
        const h = "h";
        let i = "i"; 
    }
}
```

We have a bunch of arbitrary variables. Their values aren't important; how and where they are declared, though, is the focal point here.

`a`, `b`, and `c` are all global variables. They are accessible from anywhere. `d`, `e`, and `f`, on the other hand, are accessible only from within the `doSomething` function. Likewise, `x` and `y` are parameters of the `doSomething` function, and are accessible only within the function itself.

`g`, `h`, and `i` is where it gets interesting. `h` and `i` use `const` and `let`, respectively. They respect block scoping, and are only available within the `if` statement. `g` uses `var`, and it is hoisted to the top of the function. It is available anywhere inside of the `doSomething` function.

{% embed url="https://www.youtube.com/watch?v=dzEieWaOJE0" %}

This is why it's important to use `let` and `const` in favor of `var`. Your code can become confusing and buggy if you're using `var` and not fully understanding the scoping implications of doing so.

Alright, let's dive back into writing code. Learning by doing is really the only way to become a programmer. So let's get to doing!

{% page-ref page="../problem-sets/problem-set-8.md" %}

