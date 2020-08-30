# Pixels and Images

## Encoding Images

Storing text was pretty straightforward. Assign a number to each character, convert that number to binary, and store it. Storing image data isn't as intuitive, so let's see if we can wrap our heads around it.

In order to store a digital representation of a picture, we need to break down the image into concrete values that a computer can store.

Pixels are the building blocks of images. A pixel represents the smallest element of a digital image. Images are represented by a grid of values, where each value encodes the color at that position in the image.

The simplest encoding scheme would be black-and-white, where each pixel is either 0 \(black\) or 1 \(white\). This is great, but we probably want to add some color.

We've all worked in CSS to some extent, so you've probably realized that those color codes are hexadecimal values. Before we can talk about storing color data, we'll need to go on a brief tangent about the hexadecimal number system.

{% embed url="https://www.youtube.com/watch?v=L390Jn\_dCkI&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

## Hexadecimal

Remember, all number systems work exactly the same. The only difference is their base \(which defines the number of available digits or characters\). Hexadecimal has a base of 16, and supports the following digits and characters \(yes, there are letters in this number system\).

* `0-9`
* `A-F`

{% embed url="https://www.youtube.com/watch?v=v-azFgcnOwg&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

A hexadecimal value might be something `43F`. This looks weird, because numbers don't typically have letters in them. Once you get past this, it becomes a little easier to interpret these values.

### Converting to Decimal

Since we're working with a base of 16, we know that each place value increases by a factor of 16.

| 256s | 16s | 1s |
| :--- | :--- | :--- |
| 4 | 3 | F |
| \(4 \* 256\) | \(3 \* 16\) | \(F \* 1\) |

How can we convert this to decimal? Well, we multiply and add just like we've always done.

`(4 * 256) + (3 * 16) + (F * 1) = (4 * 256) + (3 * 16) + (15 * 1)`

We use decimal values to replace the hexadecimal letters. `A` is `10`, `B` is `11`, and so on. Now, back to the math.

`1024 + 48 + 15 = 1087`

`43F` in hexadecimal is equivalent to `1087` in decimal.

### Converting to Binary

All hexadecimal digits can be represented by 4 bits. If we sketch out a simple table of these values, we can avoid all of the math in the conversions.

| Hexadecimal | Binary | Hexadecimal | Binary |
| :--- | :--- | :--- | :--- |
| 0 | 0000 | 8 | 1000 |
| 1 | 0001 | 9 | 1001 |
| 2 | 0010 | A | 1010 |
| 3 | 0011 | B | 1011 |
| 4 | 0100 | C | 1100 |
| 5 | 0101 | D | 1101 |
| 6 | 0110 | E | 1110 |
| 7 | 0111 | F | 1111 |

Suppose we have a hexadecimal value of `AC73`. We have 4 hexadecimal digits, so we're going to have 4 sets of 4 bits. Let's use our table.

| A | C | 7 | 3 |
| :--- | :--- | :--- | :--- |
| 1010 | 1100 | 0111 | 0011 |

Not too bad, right? `AC73` in in hexadecimal is `10101100 01110011` in binary.

## Pixels with Color

Back to encoding images, this time with a little color! There are a few different color encoding schemes, but we're going to start with a simple one: RGB. This encoding scheme, whose letters stand for red, green, and blue, encode the proportion of red, green, and blue light in a pixel.

{% embed url="https://www.youtube.com/watch?v=DUX-cn1lcxU&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Using red, green, and blue light at varying intensities, we can create any color. Each pixel gets three values between 0 and 255. These are referred to as color channels \(red, green, and blue\). All 0s is black, and all 255s is white. Everything in between is a shade of some color.

Each color channel is represented by 8 bits. And since we have three channels, each color is represented by 24 bits. When we represent colors, its common to use hexadecimal, which means the 8 bits are split across 2 hexadecimal digits or characters.

* RGB: `(156, 54, 255)`
* Binary: `10011100 00110110 11111111`
* Hexadecimal: `#9C36FF`

Hexadecimal color codes are always represented as `#RRGGBB`.

## Image Manipulation

Now that we have a system to encode image data, we can manipulate that system to modify the image.

{% embed url="https://www.youtube.com/watch?v=Po0iqPA6j1A&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Suppose we have a pixel whose RGB values are 120, 20, and 220. We can apply a brightness filter and increase each color channel by 50 \(without exceeding 255\). The result is a pixel whose RBG values are 170, 70, and 255.

Programmatically, this might look something like this.

```javascript
let red = /* value of red color channel */;
let green = /* value of green color channel */;
let blue = /* value of blue color channel */;

const brighten = 50;    // brightness filter

red = Math.min(red + brighten, 255);
green = Math.min(green + brighten, 255);
blue = Math.min(blue + brighten, 255);
```

Now, each color channel in the pixel is brightened by a factor of 50 \(without exceeding 255\). We can do the same to darken an image, too.

```javascript
let red = /* value of red color channel */;
let green = /* value of green color channel */;
let blue = /* value of blue color channel */;

const darken = 50;    // darkness filter

red = Math.max(red - darken, 0);
green = Math.max(green - darken, 0);
blue = Math.max(blue - darken, 0);
```

Now, each color channel in the pixel is darkened by a factor of 50 \(without going below 0\).

### Programming

All of this is great in theory, but we need to take a look at how to access images and pixels in our code. [WebImage](https://developers.google.com/android/reference/com/google/android/gms/common/images/WebImage) is a JavaScript API that can help simplify this process.

{% embed url="https://www.youtube.com/watch?v=tL6tGxNjURA&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

If you have an image accessible via a certain web address, you can use this address to create a `WebImage` object in JavaScript.

```javascript
const url = "https://codehs.com/static/img/library/characters/monkey.jpg";
const img = new WebImage(url);
```

Now, we have a host of methods available to our `img` object.

* `setPosition(x, y)` - sets the position of the upper left corner of the image.
* `setSize(width, height)` - sets the width and height of the image in pixels.
* `getWidth()` - returns the width of the image in pixels.
* `getHeight()` - returns the height of the image in pixels.
* `getPixel(x, y)` - returns the pixel at the coordinate \(`x`, `y`\) as an array of RGB values `[ R, G, B ]`.
* `setRed(x, y, value)` - assigns the red color channel of the pixel at coordinate \(`x`, `y`\) to be `value`.
* `setGreen(x, y, value)` - assigns the green color channel of the pixel at coordinate \(`x`, `y`\) to be `value`.
* `setBlue(x, y, value)` - assigns the blue color channel of the pixel at coordinate \(`x`, `y`\) to be `value`.

With this functionality, we can write our own image filters! All we'd need to do is loop through each coordinate pair in an image, retrieve the pixel at that location, modify it as needed, and update the image.

