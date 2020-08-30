# Arrays

## Creating Arrays

An array is an order collection of values, which you can visualize as a list. Each value is called an element, and each element is assigned a unique index \(starting at 0\). Many languages only permit us to store elements of the same data type, but JavaScript doesn't impose this restriction on us. We can put whatever we want in our arrays.

The easiest and most common way to create an array in JavaScript is to use the array literal syntax.

```javascript
let empty = [];                                    // an empty array
let numbers = [ 1, 2, 3 ];                         // an array of 3 numbers
let words = [ "one", "two", "three" ];             // array of strings
let mixed = [ 1, "two", { three: 3, four: 4 }];    // array of mixed elements
```

If we print out these variables, we'll get the array contents.

```javascript
console.log(empty);
console.log(numbers);
conso.e.log(words);
console.log(mixed);
```

The output will looking something like this.

```text
[]
[ 1, 2, 3 ]
[ 'one', 'two', 'three' ]
[ 1, 'two', { three: 3, four: 4 } ]
```

There is an `Array` constructor that can be used to create arrays, as well, but it's almost always simpler \(and preferable!\) to use the literal syntax.

```javascript
let empty = new Array();                                  // empty
let numbers = new Array(1, 2, 3);                         // numbers only
let words = new Array("one", "two", "three");             // strings only
let mixed = new Array(1, "two", { three: 3, four: 4});    // mixed elements
```

This does everything the literal syntax did, expect it's not as straightforward. Again, please opt for the literal syntax unless you have a very good reason not to.

{% embed url="https://www.youtube.com/watch?v=dozFo33v21k" %}

## Getting and Setting Values

Remember the bracket syntax we used with objects? We're going to use the same syntax to read and write values from and to our arrays.

```javascript
const names = [ "Joseph", "Jennifer", "Alex", "Ashley" ];
```

Each element is given a unique index, starting with 0. For our `names` array, `Joseph` is at the zeroth index, `Jennifer` is at the first index, `Alex` is at the second index, and `Ashley` is at the third index.

### Getting

We can access these values using their indexes and the bracket notation.

```javascript
const a = names[0];    // a is now "Joseph"
const b = names[1];    // b is now "Jennifer"
const c = names[2];    // c is now "Alex"
const d = names[3];    // d is now "Ashley"
```

Although negative indexes and indexes that exceed the length of the array are invalid, JavaScript does not prevent us from trying to use them. If you reference an index that doesn't exist, your program won't crash \(not right away, anyway\).

```javascript
const nonexistent = names[-1];        // undefined
const alsoNonexistent = names[4];     // undefined
```

Both `nonexistent` and `alsoNonexistent` would be given the value of `undefined`, but your program wouldn't crash because of your reference to nonexistent indexes. It might, however, later crash later if you try to manipulate an `undefined` value that you believe is defined.

```javascript
const friend = names[1];
const imaginaryFriend = names[7];

const nickname = friend.substring(0, 3);
const anotherNickname = imaginaryFriend.substring(0, 3);    // crash!

console.log(nickname);           // prints "Jen"
console.log(anotherNickname);    // what does this print?
```

Your program will happily proceed until it tries to call the `substring` method on `imaginaryFriend`. Because we used an invalid index, `imaginaryFriend` was set to `undefined`. JavaScript didn't mind until we tried to call `substring` on an `undefined` value. That would cause the program to crash!

### Setting

We can assign values to specific indexes in much the same way.

```javascript
const names = [];    // initially empty

names[0] = "Patrick";
names[1] = "Paula";
```

Now, the first two indexes of `names` have been assigned values. Likewise, we can overwrite existing values using the same methodology.

```javascript
const names = [ "Patrick", "Paula", "Robert", "Rebecca" ];

console.log(names[0]);    // prints "Patrick"

names[0] = "Peter";

console.log(names[0]);    // prints "Peter"
```

### Length

JavaScript provides a simple way to access the length of an array: the `length` property.

```javascript
const list = [ "a", "b", "c", "d" ];

console.log(list.length);    // prints 4
```

Unlike other programming languages, array lengths in JavaScript are fluid. We can create an array whose length is four, but writing a value change quickly change that.

```javascript
const list = [ "a", "b", "c", "d" ];

console.log(list.length);    // prints 4

list[7] = "h";

console.log(list.length);    // prints 9

// [ "a", "b", "c", "d", undefined, undefined, undefined, "h" ]
```

We write `h` into the seventh index, which increases the length accordingly. All of the empty slots in between are filled in with `undefined`.

{% embed url="https://www.youtube.com/watch?v=inMcmr4kAbY&list=PL\_c9BZzLwBRLVh9OdCBYFEql6esA6aRsi" %}

## Adding and Removing Elements

To add or remove one or more elements, we're going to start exploring some of the built-in methods of the `Array` object.

### Adding

The easiest way to append one or more elements to the end of an array is with the `push` method. This allows you to pass into a comma-separated list of values, each of which will be appended to the end of your array.

```javascript
const letters = [ "a", "b", "c", "d" ];

letters.push("e");    // appends "e" to end of letters
```

Originally, the `letters` array contains four letters: `a`, `b`, `c`, and `d`. After the push method, the array will contain `a`, `b`, `c`, `d`, and `e`.

We can do the same thing to append more than one value at a time.

```javascript
// remember, letters contains a, b, c, d, and e

letters.push("f", "g", "h", "i");
```

Now, `f`, `g`, `h`, and `i` have been appended to the end of the array.

Remember, `push` adds elements to the end of an array. Similarly, the `unshift` method adds one or more elements to the beginning of the array.

```javascript
const fruits = [ "pear", "strawberry", "watermelon" ];

fruits.unshift("blueberry");

// now, fruits contains blueberry, pear, strawberry, watermelon
```

Again, we can add more than one element at a time, too.

```javascript
// fruits: blueberry, pear, strawberry, watermelon

fruits.unshift("apple", "banana");

// now, it contains apple, banana, blueberry, strawberry, watermelon
```

### Removing

As you might've guessed, there are companion methods that perform the opposite functions as `push` and `unshift`. Let's start with `pop`, which removes an element from the end of the array.

```javascript
const fruits = [ "apple", "banana", "blueberry", "strawberry" ];

const removed = fruits.pop();

// removed is strawberry
// fruits is now apple, banana, blueberry
```

The pop method returns whatever element it removed, just in case we need a reference to it. It's gone from the array, so this is the only way to retain access to it.

If we don't need to reference the last removed element, we can use the pop method on its own and it'll still remove the element from the array.

```javascript
fruits.pop();    // removed banana

// now fruits is just apple
```

Similarly, the `shift` method removes the first element of an array.

```javascript
const animals = [ "lion", "tiger", "bear" ];

const removed = animals.shift();

// removed is lion
// animals is now tiger, bear
```

Like `pop`, `shift` returns a reference to the element it just removed. This isn't necessary, but is sometimes helpful. We can use the `shift` method on its own and it'll do the same job.

```javascript
animals.shift();    // removed tiger

// now animals is just bear
```

### Inserting and Replacing

The splice method is a powerful method that helps us to insert or replace elements in our array. It's flexible, and can be used to achieve a number of things.

```javascript
const months = [ "Jan", "Feb", "Mar", "May", "Jun", "Jul" ];

// we forgot Apr, so we need to insert that before May

months.splice(3, 0, "Apr");

// now the array holds:
// Jan, Feb, Mar, Apr, May, Jun, Jul
```

Let's see what's going on here. The `splice` method takes three arguments.

* start
* deleteCount
* item \(possible a comma-separated list of items\)

`start` is the index at which we want to insert. `deleteCount` is how many elements we want to delete \(beginning with `start`\). And `item` \(or a list of items\) is the element we're going to insert.

So, using our `months` example, let's walk through this. `Apr` belongs at the third index, so we pass `3` into the `splice` method as our `start` value. We don't want to delete anything, so we pass `0` as our `deleteCount`. And lastly, we pass `Apr` as the `item` to insert.

We can also use splice to replace elements.

```javascript
const months = [ "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Aug" ];

// we want to replace Aug with Jul

months.splice(6, 1, "Jul");

// now the array holds:
// Jan, Feb, Mar, Apr, May, Jun, Jul
```

Again, let's walk through this.

We want to replace `Aug` with `Jul`, and this will be at the sixth index. Our `start` value is 6. We want to remove `Aug`, so our `deleteCount` is `1`. And we want to insert a single `item`: `Jul`.

You can check out these \(and many more\) `Array` methods in the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

## Array Iteration

To iterate over an array means to traverse each of the elements in the array. A `for` loop is, by far, the most common way to do this, and we're going to look at a few variations of this.

### Traditional `for` Loop

A traditional for loop uses indexes, bracket notation, and the length of the array to iterate over the elements.

```javascript
const arr = [ 2, 4, 6, 8 ];

// print out each element of the array one-by-one

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

If we run this code segment, we'll get each value printed on its own line.

```text
2
4
6
8
```

You can, of course, modify which elements you iterate over by manipulating the start and end indexes, as well as the incrementation \(or decrementation\) of the loop counter.

To demonstration this, we could print the values of an array in reverse order by switching the starting value of the `i` and the condition under which the loop continues or not.

```javascript
const arr = [ 1, 2, 3, 4, 5, 6, 7 ];

// print in reverse order

for (let i = array.length - 1; i >= 0; i--) {
    console.log(arr[i]);
}
```

Or, we could print every other value by changing `i++` to `i = i + 2`.

```javascript
const arr = [ 1, 2, 3, 4, 5, 6, 7 ];

// print every other value

for (let i = 0; i < arr.length; i = i + 2) {
    console.log(arr[i]);
}
```

{% embed url="https://www.youtube.com/watch?v=Z9DomDWX7QY&list=PL\_c9BZzLwBRLVh9OdCBYFEql6esA6aRsi" %}

### Enhanced `for` Loop

Remember the `for...in` loop that iterated over the _properties_ of an object? This is similar. It's called a `for...of` loop and it iterates over the values of an array.

```javascript
const flowers = [ "daisy", "sunflower", "tulip" ];

// print each value of the flowers array

for (let flower of flowers) {
    console.log(flower);
}
```

The syntax is a little different. It uses a placeholder that represents each value of an array. The array goes from the very first element to the very last element one at a time, and it does this automatically.

In our example, `flower` is a placeholder. It will take on the value of every element of the `flowers` array one-by-one. We don't need to increment the array index. All of that is done for us.

### `forEach` Loop

`forEach` is a built-in method of the `Array` object. It functions a lot like the `for...of` loop, but it's even more powerful.

```javascript
const flowers = [ "daisy", "sunflower", "tulip" ];

// print each value of the flowers array using arrow function

flowers.forEach((flower) => {
    console.log(flower)
});
```

Remember arrow functions? Yeah, they're back, and they're what makes the `forEach` method so powerful. We need to provide a function that is called on each value of the `flowers` array.

Let's break down the function itself.

```javascript
// arrow function

(flower) => {
    console.log(flower);
}

// converted to function declaration

function doSomething(flower) {
    console.log(flower);
}
```

The function is anonymous, meaning it doesn't have a name. It doesn't need one because it's only ever going to be called in the `forEach` method. It accepts a single parameter, which is a placeholder for the current value of the array. That placeholder value is printed to the console.

This is a simple implementation, but we can do whatever we want in this function. Suppose we wanted to manipulate the names of each of the flower before printing them.

```javascript
const flowers = [ "daisy", "sunflower", "tulip" ];

// print each value in the format: "I like daisies."

flowers.forEach((f) => {
    let flower = f.charAt(0).toUpperCase() + f.substring(1);
    
    if (flower.endsWith("y")) {
        flower = flower.substring(0, flower.length() - 1) + "ies";
    } else {
        flower = flower + "s";
    }

    console.log(`I like ${flower}.`);
});
```

Our arrow function capitalizes and pluralizes our flowers, before printing a message to the console. Alternatively, we could have declared this function elsewhere and invoked it from inside of a `for` loop. Sometimes that is preferable, other times the array syntax is better.

The `forEach` method also lets us pass in the current index and the original array, in addition to the current value. This gives us a great deal of flexibility in our implementations.

{% embed url="https://www.youtube.com/watch?v=MMb6CPU0vy8&list=PL\_c9BZzLwBRLVh9OdCBYFEql6esA6aRsi" %}

## Built-in Methods

We've already seen a few built-in methods: `pop`, `push`, `shift`, `unshift`, `splice`, and `forEach`. There are many, many others! Make sure you're comfortable using and interpreting the following methods.

* `every`
* `fill`
* `filter`
* `find`
* `findIndex`
* `forEach`
* `includes`
* `indexOf`
* `join`
* `lastIndexOf`
* `pop`
* `push`
* `shift`
* `splice`
* `unshift`

{% embed url="https://www.youtube.com/watch?v=R8rmfD9Y5-c" %}

You can and should check out [the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) on these and many more `Array` methods.

Alright, I've thrown a lot at you. Let's see how much of it stuck.

{% page-ref page="../problem-sets/problem-set-7.md" %}

