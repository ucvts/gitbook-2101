# Number Systems

## What is Digital Information?

Computers don't understand thoughts, ideas, pictures, or text the way a person does. Computers are essentially vey fast calculators. They deal in numbers. If we want them to be able to work with more abstract concepts, we need to speak in their language.

{% embed url="https://www.youtube.com/watch?v=N5SU4RW9opc&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

The first step to speaking in their language is figuring out a way for them to store our ideas in a way that makes sense to them: numbers \(specifically, binary numbers\).

### Encoding Data

Encoding data is the process by which we take complicated things and convert them to something much more simple. We see this every day in the world around us.

We use red, yellow, and green in our traffic signals to encode stop, slow down, and go. Postal codes are used to determine the city and state of origin \(or destination\) in mail delivery. Even fast food restaurants use numbers on their menus to simplify the ordering process.

With computers, we're going to be working in the other direction. Encoding things at a lower and lower level until we reach a point where computers can store and understand their meaning. Let's start with a simple sentence.

* _My name is Mr. Wilson._

This is pretty straightforward for a human to read and understand, but less so for a computer. Computers need to do some work \(with our help, of course\) to understand this.

* Each character in the sentence needs to be encoded as a number \(using [the ASCII table](https://www.ascii-code.com/)\).
* Each decimal value must encoded as a binary number \(a series of 1s and 0s\).
* Each binary digit must be represented in some by the physical hardware.

The physical hardware can use a number of means by which it represents 1s and 0s. This can be electrical impulses \(on or off\), bumps or valleys on a disc, or even holes in a punchcard.

### Data Abstraction

An important concept in this process is how this information is represented in its various layers of abstraction. An abstraction is a way by which we simplify complex data into smaller, simpler, and more manageable chunks of information.

Consider the human body. Certainly, we are vastly complex organisms; however, we can use abstraction and encoding to simplify our own bodies.

* We start with a human body.
* We are a collection of cells \(trillions of them\) all interacting with each other.
* Our cells are made up of proteins \(among other things\).
* These proteins are comprised of chains of amino acids.
* Our DNA provides the instructions to build these amino acids.

We, as the people we are, aren't all that concerned with the specific DNA sequence that encodes our underlying love of soccer, music, or programming. In much the same way, our amino acids don't need to worry about the expression of our genes at the macro level. They just need to chain together and build some proteins.

Every layer in the abstraction of our bodies has a specific job, and it's the only job that matters. The upstream details or downstream manifestations of those details are abstracted away so that each layer can focus on its specific task.

The same is true in programming. If we're tasked with writing a Tic-Tac-Toe application, we need to work a different layers of abstraction. A function that marks the board with either an X or an O doesn't care \(nor should it\) about the logic behind determining a winner. It has one job: put a letter in a square.

### Processing Data

Once we've encoded data digitally, it opens up a world of possibilities regarding what we can do with that data. We can manipulate it, filter it, analyze it, or even transmit it.

#### Manipulation

An image that is encoded as a series of 1s and 0s is easily modified by manipulating the underlying 1s and 0s of the original image. This lets graphic designers add filters, lighten or darken the image, or in some other way alter its presentation. Those in the music and film industries undoubtedly manipulate these 1s and 0s \(even if they're unaware that that's what their application of choice is doing\) to edit songs and movies.

Business intelligence applications analyze enormous amounts of data in order to identify trends \(and make business decisions based on those trends\). Facebook and other social media companies harvest our data, analyze it, and use to to produce targeted advertisements based on our predicted interests.

#### Transmission

In this day and age, we are sending and receiving data almost constantly \(and instantly\). Every text message you send to your friend is an example of data transmission, along with the various steps of encoding and decoding that make this possible.

You type out a simple text message to your friend. You tap the keys and letters appear on the screen. Hit send and off your message goes. But what's actually happening under the hood?

Well, first, your message needs to be encoded as a sequence of binary digits. Your cell phone then encodes those digits are radio waves, and fires them off to the nearest cell tower. The message is repeated back from the tower to your friend's phone, where the process is reversed. The radio waves are decoded to binary digits, which, in turn, are decoded to words and sentences.

## Binary

We're all familiar with the decimal number system. It's the number system you've probably used since you learned to count. There are a number of other number systems that are common in computer science: binary, octal, and hexadecimal.

{% embed url="https://www.youtube.com/watch?v=v9agiJWWUio&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

We're going to start with binary, because it's the number system computers use to store and interpret data. Unlike the decimal system, which uses 10 digits \(0-9\), the binary system uses only 2 digits \(0 and 1\).

### Decimal Places

All number systems are the same, as you'll see. The only difference is the base being used \(for decimal, the base is 10; and for binary, the base is 2\).

Suppose we have the number 211 \(in decimal\). Let's break down how this is represented.

| 100s | 10s | 1s |
| :--- | :--- | :--- |
| 2 | 1 | 1 |

We can think of these as groupings. We have 2 groups of 100, 1 groups of 10, and 1 group of 1. To get the value of the number, we multiple the group by the place value and add the products.

`(2 * 100) + (1 * 10) + (1 * 1) = 200 + 10 + 1 = 211`

We're so comfortable with the decimal system that this level of detail isn't necessary. It'll sure be helpful when we need to interpret binary numbers, though.

### Binary Places

The binary value for 211 is 11010011. Let's break this down in the same way we did with the decimal number. Our place values, of course, will be different. It'll still start with 1, but will increase by a factor of 2 each time \(rather than 10\).

| 128s | 64s | 32s | 16s | 8s | 4s | 2s | 1s |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 1 | 0 | 1 | 0 | 0 | 1 | 1 |

Again, we'll think in terms of groups. Since we're working in binary, we'll either have a group \(of 1\) or we won't have any group at all.

We have a group of 128 and 64, no groups of 32, a group of 16, no groups of 8 or 4, and a group of 2 and 1. Just like last time, we multiply and add.

`(1 * 128) + (1 * 64) + (0 * 32) + (1 * 16) + (0 * 8) + (0 * 4) + (1 * 2) + (1 * 1)`

We can simplify this a bit. The 0s aren't going to impact the sum, so we can leave them out.

`(1 * 128) + (1 * 64) + (1 * 16) + (1 * 2) + (1 * 1) = 128 + 64 + 16 + 2 + 1 = 211`

Those of you who are more mathematically inclined might prefer to use exponents to represent these same values. For example, 1st is the same as 2 raised to the 0th power and 128s is the same as 2 raised to the 7th power.

## Conversions

It's pretty straightforward to convert between bases. You just need to figure out your starting point, and work backwards from there. Let's take a look at a few examples.

{% embed url="https://www.youtube.com/watch?v=f1fK6GGYg-0&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

### Decimal to Binary

Suppose we wanted to convert 27 \(in decimal\) to its binary equivalent. First, how many positions will we need? Counting the place values we have 1, 2, 4, 8, 16, 32...oops, 32 is too big. We'll start with 16.

| 16s | 8s | 4s | 2s | 1s |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 1 | 0 | 1 | 1 |

We work backwards, starting with our 16. Subtract that from 27 and we have 11 left, which means we can grab an 8. Now we have 3 left over, so no 4. We grab a 2 and there's just the 1 left.

### Binary to Decimal

Let's try one in the other direction. We'll use the same example.

Suppose we have 11011 \(in binary\) and want to convert to its decimal equivalent. First, we count the positions. There are 5, which means our largest place value will be 16 \(followed by 8, 4, 2, and 1\). Let's add up the numbers where we have a 1 and ignore those with a 0.

`16 + 8 + 2 + 1 = 27`

See? Not so hard.

## Encoding Text

We've already seen that all data can be encoded as a series of 1s and 0s. These binary digits are often referred to as bits \(**bi**nary digi**t**, get it?\).

{% embed url="https://www.youtube.com/watch?v=YgewWP0UtB0&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Computers always store data in binary, even if we're writing that data in a different format.

```javascript
const letter = "A";
```

As humans, we see the variable `letter` has holding the value `A`. But the computer stores something much different: 01000001.

As computer scientists, we have devised a set of groupings for bits to help us understand their capacities.

| Name | Size | Example |
| :--- | :--- | :--- |
| bit | A single 1 or 0 | `true` or `false` |
| byte | 8 bits | A character of text |
| kilobyte \(kB\) | 1024 bytes | A paragraph of text |
| megabyte \(MB\) | 1024 kilobytes | A 3-minute song \(~3 MB\) |
| gigabyte \(GB\) | 1024 megabytes | Storage on an iPad \(32 GB\) |
| terabyte \(TB\) | 1024 gigabytes | Library of Congress |
| petabyte \(PB\) | 1024 terabytes | 10 billion Facebook pictures |

We can generalize how many possible values a number of bits can store.

* 1 bit can store 2 possible values \(1 or 0\).
* 2 bits can store 4 possible values \(11, 10, 01, or 00\).
* 3 bits can store 8 possible values \(see the pattern?\).

The pattern that emerges is that _n_ bits can store _2 raised to the power of n_ possible values.

### Binary Mappings

In order to use bits to represent data, we need to agree upon an encoding scheme. Just making up our own \(while it would work\) is a bad idea because it's not widely accepted.

Morse code, for example, is a widely accepted binary encoding scheme. It uses dots and dashes \(i.e., 0s and 1s\). Another popular encoding scheme, particularly for text, is ASCII. It uses a byte \(or 8 bits\) to encode every possible character.

The ASCII table is a listing of each character, along with its decimal, octal, hexadecimal, and binary values. Computers all understand this encoding scheme, which is why text can be interpreted in the same way across different devices.

