# The Math Object

## More Math

`Math` is a built-in object in JavaScript that provides some helpful mathematical properties and methods that you can use. To use the `Math` object, you reference it by name following by the constant or method you wish to use.

```javascript
Math.SOME_CONSTANT
Math.someMethod()
```

### Properties

Let's take a look at the available properties of the `Math` object.

* `Math.E`
* `Math.LN10`
* `Math.LN2`
* `Math.LOG10E`
* `Math.LOG2E`
* `Math.PI`
* `Math.SQRT1_2`
* `Math.SQRT2`

Properties are always typed in all capital letters. Most of these are self-explanatory, even if their spellings are often abbreviated. You can read more about these in the [full documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math#Static_properties).

### Methods

Beyond properties, the `Math` object provides many useful methods. We'll take a look at a few of the more popular ones.

* `Math.abs(x)`

The `abs` method returns the absolute value of `x`, where `x` is a placeholder for any number you enter.

```javascript
let a = Math.abs(-7);    // a is 7

let b = -12;
let c = Math.abs(b);    // c is 12, b is unchanged
```

* `Math.cbrt(x)`

The `cbrt` method returns the cube root of `x`, where `x` is a placeholder for any number you enter.

```javascript
console.log(Math.cbrt(125));    // prints 5
```

* `Math.ceil(x)`

The `ceil` method returns the smallest integer greater than or equal to `x`, where `x` is a placeholder for any number you enter.

```javascript
let a = 4.1;
let b = Math.ceil(a);    // b is 5

let c = 4;
let d = Math.ceil(c);    // d is 4
```

* `Math.floor(x)`

The `floor` method returns the largest integer less than or equal to `x`, where `x` is a placeholder for any number your enter.

```javascript
let a = 4.9;
let b = Math.floor(a);    // b is 4

let c = 4;
let d = Math.floor(c);    // d is 4
```

* `Math.hypot(x, y)`

The `hypot` method returns the square root of the sum of the squares of `x` and `y`, where `x` and `y` are placeholders for any numbers you enter. Essentially, this calculates the hypotenuse of a triangle using the Pythagorean Theorem.

```javascript
let a = 3;
let b = 4;
let c = Math.hypot(a, b);    // c is 5
```

* `Math.max(x, y, ...)`

The `max` method returns the largest number provided. You can provide as many numbers as you'd like.

```javascript
let a = Math.max(1, 2);       // a is 2
let b = Math.max(1, 2, 3);    // b is 3
```

* `Math.min(x, y, ...)`

The `min` method returns the smallest number provided. You can provide as many numbers as you'd like.

```javascript
let a = Math.min(9, 8);       // a is 8
let b = Math.min(9, 8, 7);    // b is 7
```

* `Math.pow(x, y)`

The `pow` method returns `x` raised to the power of `y`, where `x` and `y` are placeholders for any numbers you enter.

```javascript
let base = 2;
let exponent = 3;

console.log(Math.pow(base, exponent));    // prints 8
```

* `Math.random()`

The `random` method returns a random number between 0 and 1 \(inclusive of 0, but not of 1\).

```javascript
let a = Math.random();    // a might be 0.123...
let b = Math.random();    // b might be 0.987...
```

You read about these methods \(in more detail\) and others in the [full documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math#Static_methods). Alright, time for another problem set. Let's see if you can put all those operators to good use!

