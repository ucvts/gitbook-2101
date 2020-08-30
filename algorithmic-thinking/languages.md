# Languages

## Representing Algorithms

We have a few different options to represent the algorithms we write.

* Natural languages
* Programming languages
* Pseudocode

We'll get to each of these over the course of the next couple sections.

### Natural Languages

A natural language is one we use to speak, read, and write every day. English is a natural language, as well as any other spoken dialect. These are not good candidates for algorithms.

Because of their richness of expression, natural languages inherently possess some degree of ambiguity. And as we've already see, algorithmic instructions should be unambiguous. The verbosity of a natural languages isn't well suited to drafting clear and concise steps.

### Programming Languages

Programming languages are the logical opposites of natural languages. They use strict grammars and vocabularies, and do not have the ambiguous and verbose expressionism that natural languages do.

We need to translate our algorithms to some programming language before we can execute it on a computer. So why not just skip the middle man and start with programming languages with representing our algorithms?

When designing algorithms, we tend to think at a higher level of abstraction. And since programming languages have specific syntaxes and grammars, developing our algorithms in these languages requires us to deal with these nuances immediately.

### Pseudocode

Pseudocode is an intermediary language between natural and programming languages. It is concise, direct, and clear, but there is no set syntax to follow. It gives you the freedom to gloss over the strictness of programming languages, without having to navigate the verbosity of natural languages.

## AP Format

The AP exam uses its own code format. It does not align with a specific programming language, nor is it a natural language. It's kind of like a pseudocode, except it has a structured syntax.

You'll get a reference sheet that outlines each component of the AP format. Please review these thoroughly, as you'll be expected to read and interpret code segments written in this format.

### Assignment, Display, and Input

| Instruction | Explanation |
| :--- | :--- |
| `a ← expression` | Evaluates `expression` and assigns the result to the variable `a`. |
| `DISPLAY (expression)` | Displays the value of `expression`, followed by a space. |
| `INPUT ()` | Accepts a value from the user and returns it. |

### Arithmetic Operations and Numeric Procedures

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>a + b</code>
        </p>
        <p><code>a - b</code>
        </p>
        <p><code>a * b</code>
        </p>
        <p><code>a / b</code>
        </p>
      </td>
      <td style="text-align:left">The arithmetic operators <code>+</code>, <code>-</code>, <code>*</code>,
        and <code>/</code> are used to perform arithmetic on <code>a</code> and <code>b</code>.
        For example, <code>3 / 2</code> evaluates to <code>1.5</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>a MOD b</code>
      </td>
      <td style="text-align:left">Evaluates to the remainder when <code>a</code> is divided by <code>b</code>.
        Assume that <code>a</code> and <code>b</code> are positive integers. For example, <code>17 MOD 5</code> evaluates
        to <code>2</code>.</td>
    </tr>
  </tbody>
</table>

### Relational and Boolean Operators

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>a = b</code>
        </p>
        <p><code>a &#x2260; b</code>
        </p>
        <p><code>a &gt; b</code>
        </p>
        <p><code>a &lt; b</code>
        </p>
        <p><code>a &#x2265; b</code>
        </p>
        <p><code>a &#x2264; b</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The relational operators <code>=</code>, <code>&#x2260;</code>, <code>&gt;</code>, <code>&lt;</code>, <code>&#x2265;</code>,</p>
        <p>and <code>&#x2264;</code> are used to test the relationship between</p>
        <p>two variables, expressions, or values. For example,</p>
        <p><code>a = b</code> evaluates to <code>true</code> if <code>a</code> and <code>b</code> are
          equal;</p>
        <p>otherwise, it evaluates to <code>false</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>NOT condition</code>
      </td>
      <td style="text-align:left">
        <p>Evaluates to <code>true</code> if condition is false;</p>
        <p>otherwise evaluates to <code>false</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>condition1 AND condition2</code>
      </td>
      <td style="text-align:left">
        <p>Evaluates to <code>true</code> if both <code>condition1</code>
        </p>
        <p>and <code>condition2</code> are <code>true</code>; otherwise,</p>
        <p>evaluates to <code>false</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>condition1 OR condition2</code>
      </td>
      <td style="text-align:left">
        <p>Evaluates to <code>true</code> if <code>condition1</code> is</p>
        <p><code>true</code> or if <code>condition2</code> is <code>true</code> or if
          both</p>
        <p><code>condition1</code> and <code>condition2</code> are <code>true</code>;</p>
        <p>otherwise, evaluates to <code>false</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

### Selection

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>IF (condition){</code>
        </p>
        <p><code>   &lt;block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The code in <code>block of statements</code>
        </p>
        <p>is executed<code> </code>if the Boolean expression</p>
        <p>condition evaluates to <code>true</code>; no action</p>
        <p>is taken if condition evaluates to <code>false</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>IF (condition) {</code>
        </p>
        <p><code>   &lt;first block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
        <p><code>ELSE</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>    &lt;second block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The code in <code>first block of statements</code>
        </p>
        <p>is executed if the Boolean expression</p>
        <p>condition evaluates to <code>true</code>; otherwise,</p>
        <p>the code in <code>second block of statements</code>
        </p>
        <p>is executed.</p>
      </td>
    </tr>
  </tbody>
</table>

### Iteration

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>REPEAT n TIMES</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>   &lt;block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The code in <code>block of statements</code>
        </p>
        <p>is executed <code>n</code> times.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>REPEAT UNTIL (condition)</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>    &lt;block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The code in <code>block of statements</code>
        </p>
        <p>is repeated until the Boolean expression</p>
        <p><code>condition</code> evaluates to <code>true</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

### List Operations

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>list[i]</code>
      </td>
      <td style="text-align:left">
        <p>Refers to the element of <code>list</code> at index</p>
        <p><code>i</code>. The first element of <code>list</code> is at index 1.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>list[i] &#x2190; list[j]</code>
      </td>
      <td style="text-align:left">Assigns the value of <code>list[j]</code> to <code>list[i]</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>list &#x2190; [value1, value2, value3]</code>
      </td>
      <td style="text-align:left">
        <p>Assigns <code>value1</code>, <code>value2</code>, and <code>value3</code>
        </p>
        <p>to <code>list[1]</code>, <code>list[2]</code>, and <code>list[3]</code>,
          respectively.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>FOR EACH item IN list</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>   &lt;block of statements&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>The variable <code>item</code> is assigned the value</p>
        <p>of each element of <code>list</code> sequentially, in</p>
        <p>order from the first element to the last</p>
        <p>element. The code in <code>block of statements</code>
        </p>
        <p>is executed once for each assignment of <code>item</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>INSERT (list, i, value)</code>
      </td>
      <td style="text-align:left">
        <p>Any values in <code>list</code> at indices greater than or</p>
        <p>equal to <code>i</code> are shifted to the right. The length</p>
        <p>of <code>list</code> is increased by 1, and <code>value</code> is placed</p>
        <p>at index <code>i</code> in <code>list</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>APPEND (list, value)</code>
      </td>
      <td style="text-align:left">
        <p>The length of <code>list</code> is increased by 1, and</p>
        <p><code>value</code> is placed at the end of <code>list</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>REMOVE (list, i)</code>
      </td>
      <td style="text-align:left">
        <p>Removes the item at index <code>i</code> in <code>list</code> and</p>
        <p>shifts to the left any values at indices greater</p>
        <p>than <code>i</code>. The length of <code>list</code> is decreased by 1.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>LENGTH (list)</code>
      </td>
      <td style="text-align:left">Evaluates to the number of elements in <code>list</code>.</td>
    </tr>
  </tbody>
</table>

### Procedures

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>PROCEDURE name (parameter1,</code>
        </p>
        <p><code>                parameter2, ...)</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>   &lt;instructions&gt;</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>A procedure, <code>name</code>, takes zero or more</p>
        <p>parameters. The procedure contains</p>
        <p>programming instructions.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>PROCEDURE name (parameter1,</code>
        </p>
        <p><code>                parameter2, ...)</code>
        </p>
        <p><code>{</code>
        </p>
        <p><code>    &lt;instructions&gt;</code>
        </p>
        <p><code>    RETURN (expression)</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>A procedure, <code>name</code>, takes zero or more</p>
        <p>parameters. The procedure contains</p>
        <p>programming instructions and returns the</p>
        <p>value of <code>expression</code>. The <code>RETURN</code>
        </p>
        <p>statement may appear at any point inside</p>
        <p>the procedure and cause an immediate</p>
        <p>return from the procedure back to the</p>
        <p>calling program.</p>
      </td>
    </tr>
  </tbody>
</table>

### Robot

<table>
  <thead>
    <tr>
      <th style="text-align:left">Instruction</th>
      <th style="text-align:left">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>MOVE_FORWARD ()</code>
      </td>
      <td style="text-align:left">
        <p>The robot moves one square forward</p>
        <p>in the direction it is facing</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ROTATE_LEFT ()</code>
      </td>
      <td style="text-align:left">
        <p>The robot rotates in place 90 degrees</p>
        <p>counterclockwise (i.e., makes an in-place</p>
        <p>left turn).</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ROTATE_RIGHT ()</code>
      </td>
      <td style="text-align:left">
        <p>The robot rotates in place 90 degrees</p>
        <p>clockwise (i.e., makes an in-place right turn).</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>CAN_MOVE (direction)</code>
      </td>
      <td style="text-align:left">
        <p>Evaluates to <code>true</code> if there is an open</p>
        <p>square one square in the direction relative to</p>
        <p>where the robot is facing; otherwise evaluates</p>
        <p>to <code>false</code>. The value of direction can be</p>
        <p><code>left</code>, <code>right</code>, <code>forward</code>, or <code>backward</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

### Dialects

The AP format is broken into text and block-based dialects. This is the textual dialect. The AP Reference Sheet also details the specifics of the block-based dialect, so please be sure to familiarize yourself with both.

{% file src="../.gitbook/assets/ap-reference-sheet.pdf" caption="AP Computer Science Principles Reference Sheet" %}

## Code

A code is simply a set of symbols used to convey a message. Traffic lights use a three-color code to convey messages to drivers: stop, go, slow down. Morse Code is a way in which we can encode English letters \(a code in and of themselves\) into dots and dashes.

With computers, code takes on the form of programming languages. Programming languages contain a set of symbols that can be used to instruct the computer to do certain things.

* C
* C++
* Java
* JavaScript
* Python

In this course, we'll be focusing on the JavaScript programming language.

## Abstraction

An abstraction is a means by which we can focus on the bigger picture ideas rather than the smaller details that make those ideas possible. Programming languages provide abstractions that allow us to more easily create meaningful applications without having to deal with the low-level details underlying our programs.

## High v. Low

Programming languages are loosely categorized into high- and low-level languages. Of course, there are degrees within these categories.

### High

Humans typically work with higher level languages, as they provide more abstractions and do a lot of the lower-level tasks for us. Taking advantage of these abstractions allow us to write code in ways that more closely resemble the larger ideas we want to convey. Computers must break down our high-level instructions into increasingly lower levels before they can be understood and executed.

High-level languages include many of the popular ones you've probably heard of or used.

* C++
* Java
* JavaScript
* Python

### Low

A low-level language more closely resembles the underlying architecture of the computer's machine code. It's called assembly code, and it might look something like this.

```text
lea di, buffer
mov dx, size
putc 13d
```

This is clearly much more difficult to read, write, and understand.

C is an interesting case. It's sometimes categorized as a low-level language; otherwise, it's categorized as a high-level one. C is well-suited to perform low-level operations because it has access to operating system-level functions. However, compared to assembly code, C is still a relatively higher level language.

## Compiled

Although we write our code in higher level languages, it must always first be transformed to a lower level language before a computer can execute it. This process is called compilation. When code is compiled, it is converted from the high-level language in which it was written to the binary 1s and 0s a computer can understand. These 1s and 0s are the lowest of the languages, called machine code.

### Programs

A program is many things. It’s a single line of code, or maybe a few million lines. It’s an application on your phone or laptop. But at its core, it is the implementation of an algorithm in a specific language.

We can solve a problem by designing and writing an algorithm. Until we translate that algorithm into a programming language, we do not yet have a program.

