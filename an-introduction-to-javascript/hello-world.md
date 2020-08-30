# Hello, World

## JavaScript

Welcome to JavaScript! For many of you, this is your first introduction to a programming language. The learning curve can be steep at times, especially if you've never programmed before. Try not to compare yourself to your friend who started programming in the seventh grade. Everyone learns at their own pace, and there's nothing wrong with that!

{% embed url="https://www.youtube.com/watch?v=6X1kOo8AFtU&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

## Your First Program

In nearly every language you learn, you'll start with the classic Hello, World! program. It's a simple program that prints a message to the console. There are a few different ways to do this in JavaScript, but we're going to start with the simplest.

Create a folder \(ideally somewhere that you intend to keep all your files for this course\) and open that folder in VSCode. Open a new file called `hello-world.js` and enter the following line of code.

{% code title="hello-world.js" %}
```javascript
console.log("Hello, world!");
```
{% endcode %}

Told you it was simple! `console.log` is a function built into the JavaScript programming language. Inside the parentheses, this function will print the text you provide to the console \(i.e., `Hello, world!`\).

To execute your program, open up the terminal \(or use the terminal built into VSCode\) and enter the following command.

```text
$ node hello-world.js
```

Press enter, and you'll see the message logged to the console.

```text
$ node hello-world.js
Hello, world!
```

## Debugging

Although JavaScript tends to be more forgiving than others, the syntax is very important. Either way, you should get into the habit of writing strictly correct code.

`console` and `log` are case-sensitive. They are written in all lowercase letters, and must be separated by a period. If you break these rules, you'll get an error when you try to run the program.

{% code title="hello-world.js" %}
```javascript
Console.log("Hello, world!");    // the 'c' in console should be lowercase
```
{% endcode %}

```text
$ node hello-world.js
/Users/rwilson/principles/hello-world.js:1
Console.log("Hello, world!");
^

ReferenceError: Console is not defined
    at Object.<anonymous> (/Users/rwilson/principles/hello-world.js:1:1)
    at Module._compile (internal/modules/cjs/loader.js:776:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
    at startup (internal/bootstrap/node.js:283:19)
    at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
```

This is a stack trace and it's ugly. It's a lot of gibberish to tell you that there's no such thing as `Console`. JavaScript only understands this if it's written in all lowercase letters: `console`. The important things to note are error message, the name of the file, on which line the error occurred, and where in that line the error occurred.

* `ReferenceError: Console is not defined`
* `/Users/rwilson/principles/hello-world.js:1` \(this is the file and line number\)
* `Console.log("Hello, world!")` `^` \(this is where on this line the error occurred\)

{% code title="hello-world.js" %}
```javascript
console.Log("Hello, world!");    // the 'l' in log should be lowercase
```
{% endcode %}

```text
$ node hello-world.js
/Users/rwilson/principles/hello-world.js:1
console.Log("Hello, world!");
        ^

TypeError: console.Log is not a function
    at Object.<anonymous> (/Users/rwilson/principles/hello-world.js:1:9)
    at Module._compile (internal/modules/cjs/loader.js:776:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
    at startup (internal/bootstrap/node.js:283:19)
    at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
```

This is a similar error. We typed `console` just fine, and JavaScript recognized it. However, it didn't recognize the `Log` function because it shouldn't have been capitalized.

{% code title="hello-world.js" %}
```javascript
console.log"Hello, world!");    // missing the opening parenthesis
```
{% endcode %}

```text
$ node hello-world.js
/Users/rwilson/principles/hello-world.js:1
console.log"Hello, world!");
           ^^^^^^^^^^^^^^^

SyntaxError: Unexpected string
    at Module._compile (internal/modules/cjs/loader.js:721:23)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
    at startup (internal/bootstrap/node.js:283:19)
    at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
```

This time, JavaScript is telling us that it didn't expect our string to appear there. We need to wrap it in parentheses, and we're missing the opening parenthesis.

{% code title="hello-world.js" %}
```javascript
console.log(Hello, world!);
```
{% endcode %}

```text
$ node hello-world.js
/Users/rwilson/principles/hello-world.js:1
console.log(Hello, world!);
                   ^^^^^

SyntaxError: missing ) after argument list
    at Module._compile (internal/modules/cjs/loader.js:721:23)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
    at startup (internal/bootstrap/node.js:283:19)
    at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
```

Sometimes JavaScript gives misleading error messages, and this is one of them. We're not missing a closing parenthesis. JavaScript is just confused because we didn't wrap our text in double-quotes. Strings of text always need to be surrounded by quotes.

You'll need to get comfortable reading, understanding, and acting upon the stack traces and error messages your code generates. Debugging is a huge part of programming, so you better get used to it!

## Our First Repository

We're going to take a look at how to convert any existing project into a Git repository. And from there, we're going to push our changes up to GitHub. If that still sounds like gibberish, review the [Git and GitHub](git-and-github.md) section.

This isn't JavaScript-specific, but it demonstrates the necessary skills and steps to create a project in VSCode, initialize it as a Git repository, create a repository on GitHub, and push our VSCode project to that remote GitHub repository.

{% embed url="https://www.youtube.com/watch?v=vbQ2bYHxxEA" %}

Alright, enough show-and-tell. Time to get our hands dirty!

{% page-ref page="../problem-sets/problem-set-0.md" %}

{% page-ref page="../problem-sets/problem-set-1.md" %}

