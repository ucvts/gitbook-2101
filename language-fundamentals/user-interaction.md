# User Interaction

## Node.js

The environment we're working in is called [Node.js](https://nodejs.org/en/). It's a cross-platform JavaScript runtime environment designed to build scalable network applications. While we don't necessarily care about that, it does allow us to execute our code in the terminal. Later, we'll learn how to attach our JavaScript to websites and run it in the browser.

## Reading Input

Node.js comes with a package manager called Node Package Manager. You can use this to download and install packages and libraries to enhance your code. We're going to use a third-party library to help us read input from the user.

Let's walk through a simple tutorial. Create a directory called `basic-io` \(preferably in whatever folder you keep all of your code\). Navigate to that directory from the command line. I've created an `APCSP` folder on my Desktop, and all of the CLI commands will be based on this.

```text
$ cd ~/Desktop/APCSP
$ mkdir basic-io
$ cd basic-io
```

Once you're in your `basic-io` folder, download and install the `readline-sync` package.

```text
$ npm install --save readline-sync
```

You'll get a lot of output \(and probably some warnings, too\), most of which you can ignore.

```text
npm WARN saveError ENOENT: no such file or directory, open '~/Desktop/APCSP/basic-io/package.json'
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN enoent ENOENT: no such file or directory, open '~/Desktop/APCSP/basic-io/package.json'
npm WARN basic-io No description
npm WARN basic-io No repository field.
npm WARN basic-io No README data
npm WARN basic-io No license field.

+ readline-sync@1.4.10
added 1 package from 1 contributor and audited 1 package in 0.611s
found 0 vulnerabilities
```

All we really care about is the last three lines. If you have these, then you're good.

```text
+ readline-sync@1.4.10
added 1 package from 1 contributor and audited 1 package in 0.611s
found 0 vulnerabilities
```

If you run the `ls` command, you'll see that a couple files and folders were created.

```text
$ ls
node_modules    package-lock.json
```

Next, create a file in the `basic-io` folder called `read.js`. Open the `basic-io` folder in VSCode, and in the `read.js` file, enter the following text.

{% code title="read.js" %}
```javascript
const readlineSync = require("readline-sync");

const name = readlineSync.question("What is your name? ");
console.log("Hello, " + name + "!");

// remember template strings? this would have worked, too.
//
// console.log("Hello, ${name}!");
```
{% endcode %}

It's a simple program, but there are some pretty cool things going on here. The first line references the package we installed using `npm`. The next line calls a method called `question`, which prints a line of text to the console and waits for the user type something in response. That response is saved in the `name` variable, and printed in the `console.log` statement.

```text
$ node read.js
What is your name? Jason
Hello, Jason!
```

In the example, we used `const` to declare each of our variables. When declaring the `readline-sync` package, you should always use `const`. When declaring variables to store the user input, you can use either `const` or `let`. That will depend on whether or not the user input will or won't change.

There are plenty of options available to you to make your programs a little more fancy. Feel free to explore the [documentation](https://www.npmjs.com/package/readline-sync) in its entirety.

This was a pretty quick section. Time for an equally quick problem set.

{% page-ref page="../problem-sets/problem-set-4.md" %}

