# Objects

## Creating Objects

An object is a fundamental data type in JavaScript. They are unordered collections of properties, where each property has a name and value. Using objects, we can access these properties by name. We can store whatever we want in our objects: strings, numbers, booleans, other objects, or even functions.

There are three ways in which we can create an object.

* Using an object literal
* Using the `new` operator
* Using the `Object.create` function

### Object Literals

An object literal is a comma-separated list of _name: value_ pairs enclosed in curly braces. We can declare variables whose data type is `object` in the same way we would for `string`s or `number`s.

```javascript
let empty = {};
```

This creates an empty object. It's not of much use to us, but there are situations which you might want to start with a clean slate and build from there.

Suppose we wanted to create an object to represent a student. What are some traits we can use to describe a student?

* A first name
* A last name
* A student identification number
* A grade level
* A grade point average

Sure, we can probably think of more, but that'll suffice for now.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};
```

Each of the property names represents a valid JavaScript identifier. If you need to use a property name that isn't a valid JavaScript identifier, you'll need to wrap that property name in quotes.

```javascript
let example = {
    "invalid identifier": "see the quotes in the property name?"
};
```

Go ahead and print `student` to the console. Let's see what we get.

```javascript
console.log(student);
```

Each of the object properties \(names and values\) are printed.

```text
{ id: 1010203,
  firstName: 'Jonathan',
  lastName: 'Parker',
  gradeLevel: 12,
  gpa: 3.87 }
```

We'll see how to do a lot more with our objects later.

### The `new` Operator

Alternatively, we can use the new operator in conjunction with a special function called a constructor.

```javascript
let obj = new Object();
```

This creates an empty object. It is functionally equivalent to `let obj = {};`.

While something like this isn't all that common \(or useful\), it is typical for programmers to create their own functions to serve as constructors for custom objects. You can use parameters to pass in default values for your properties.

### The `Object.create` Function

Lastly, we can use the create function to build an object. Its usage is pretty straightforward, and looks a lot like the object literal syntax we saw earlier.

```javascript
let student = Object.create({
    id: 1020304,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
});
```

This isn't all that different than using the literal syntax. In more advanced cases, you can pass a second argument to the `create` function that sets certain configurations for the properties \(such as whether it is read-only or writable\).

## Object Properties

Let's dive into properties a little more deeply. We've created a few objects, and even printed one out to the console. All we got was our object definition repeated back to us.

{% embed url="https://www.youtube.com/watch?v=jn\_F2wJkzjY&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

### Getting

If we need to access a single property of an object, we can do so by name using either dot or bracket notation. Let's see what this looks like.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

// we need to access the student's grade point average only

const studentGpa = student.gpa;    // dot notation

console.log(studentGpa);
```

This is called dot notation, and it prints `3.87` to the console. We can also use something called bracket notation, which will make much more sense when we get to the [Arrays]() section.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

// we need to access the student's grade point average only

const studentGpa = student["gpa"];    // bracket notation

console.log(studentGpa);
```

Notice the use of double-quotes around `gpa`, which explicitly tells JavaScript that `gpa` is the name of a property of the `student` object and not a variable itself.

### Setting

In much the same way, we can assign values to our properties.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

console.log(student);    // before change

// we are going to increase the student's gpa

student.gpa = 4.0;       // now gpa is 4.0

console.log(student);    // after change
```

We printed the `student` object before and after our change. Here's what we got before.

```text
{ id: 1010203,
  firstName: 'Jonathan',
  lastName: 'Parker',
  gradeLevel: 12,
  gpa: 3.87 }
```

And now after.

```text
{ id: 1010203,
  firstName: 'Jonathan',
  lastName: 'Parker',
  gradeLevel: 12,
  gpa: 4 }
```

### Deleting

There's a difference between clearing a value one of our properties and getting rid of the property altogether. We need to be sure of which one we want to do.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};
```

If we want to clear the `firstName` value of `student`, we can do this as if we were setting a value.

```javascript
student.firstName = "";
student.firstName = null;
student.firstName = undefined;
```

Any of these could potentially be suitable ways to clear a property of its value. It all depends on what you want to do and how you've structured your program.

All of this, though, is very different from deleting a property entirely. To do that, we use the `delete` operator.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

console.log(student);

delete student.firstName;    // firstName is gone entirely

console.log(student);
```

For demonstration purposes, we'll print out `student` before and after the property deletion.

Here's what it looks like before.

```text
{ id: 1010203,
  firstName: 'Jonathan',
  lastName: 'Parker',
  gradeLevel: 12,
  gpa: 4 }
```

And here's what it looks like after.

```text
{ id: 1010203,
  lastName: 'Parker',
  gradeLevel: 12,
  gpa: 4 }
```

See how `firstName` is no longer there?

{% embed url="https://www.youtube.com/watch?v=QuUv94TODPo&list=PLCCRzPrPbnO1IX9XsUGuiXFIPR5LdCPla" %}

## Property Iteration

Sometimes we might need to iterate over all of the properties of an object. To do this, JavaScript provides a special kind of loop called a `for...in` loop. Its syntax is pretty straightforward.

```javascript
for (property in object) {
    // do something with property
}
```

We can use this technique to get the names of the properties of an object, which is what `property` represents in the syntax example above. Let's try this with our `student` object.

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

for (prop in student) {
    console.log(prop);
}
```

When we run this segment of code, we're going to get each of the `student` property names printed to the console.

```text
id
firstName
lastName
gradeLevel
gpa
```

If we want to access the values themselves in this way, we need to use bracket notation \(without the double-quotes this time\). Let's modify our code a bit to print out the property values \(rather than the names\).

```javascript
let student = {
    id: 1010203,
    firstName: "Jonathan",
    lastName: "Parker",
    gradeLevel: 12,
    gpa: 3.87
};

for (prop in student) {
    console.log(student[prop]);
}
```

Now let's see what gets printed to the console.

```text
1010203
Jonathan
Parker
12
3.87
```

