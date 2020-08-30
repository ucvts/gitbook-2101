# Manipulating the DOM

## Accessing Elements

There are several ways by which you can find an HTML element using JavaScript. The simplest and most straightforward is the `getElementById` method of the `Document` object.

{% embed url="https://www.youtube.com/watch?v=O6BNfJz3rgs&list=PLyuRouwmQCjmQTKvgqIgah03HF1wrYkA9" %}

Let's have a closer look at some code samples that demonstrate how the HTML and JavaScript are working together.

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <p id="p1">Hello, world!</p>
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
const paragraph = document.getElementById("p1");

// this line of code searches the DOM for an element whose ID
// is p1. if it can't find one, it sets paragraph to null.
```
{% endtab %}
{% endtabs %}

There are two similar methods called `getElementsByTagName` and `getElementsByClassName`. If you're paying attention, you can probably guess that these methods will find more than one element.

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <p class="detail">I am an important detail.</p>
        <p class="details">I, too, am an important detail.</p>
        
        <div>
            <img src="images/myimage.png"/>
        </div>
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
const paragraphs = document.getElementsByClassName("detail");

// this line of code searches the DOM for all elements that are
// members of the details class. this comes back as a list of
// elements, which we'll need to access in a specific way. if it
// can't find any, it sets paragraphs to null.

const images = document.getElementsByTagName("div");

// this line of code searches the DOM for all div elements. this
// comes back as a list of elements, which we'll need to access in
// a specific way. if it can't find any, it sets images to null.
```
{% endtab %}
{% endtabs %}

The method actually returns an array of elements, which will make a whole lot more sense after the [Arrays]() section. We'll come back to this, but understand that it does exist and can be useful at times.

If the element or elements you're looking for don't have a class or ID, there is a third option: `querySelector`. This method uses CSS selectors to locate elements.

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <div>
            <p>This is paragraph one.</p>
            <span>
                <p>This is paragraph two.</p>
            </span>
        </div>
        <p>This is paragraph three.</p>
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
const paragraph = document.querySelector("div span p");

// this line of code searches the DOM for the element that matches the
// provided CSS selector string. there are several paragraphs in this
// document, but we're only interested in this one.
```
{% endtab %}
{% endtabs %}

## Modifying Elements

Once we are able to access an element, we can modify any of its characteristics. Content, style, an attributes are all programmatically customizable.

```javascript
const imageSrc = "images/house.png";

const image = document.getElementById("image-1");

image.src = imageSrc;    // changes the image being displayed
```

Albeit simple and arbitrary, this code will change the picture being displayed on the page. We can expand upon this to do some very cool and creative things.

{% embed url="https://youtu.be/DO02UZaedIo" %}

Maybe we want to display a certain message whenever a user clicks a button. This is how we can dynamically change the text of a paragraph in real-time.

```javascript
const paragraph = document.getElementById("text-1");

paragraph.textContent = "Let's change our paragraph's text!";

// this updates the text being displayed by the paragraph
```

Let's try another. We'll change the color of the text of a paragraph.

```javascript
const paragraph = document.getElementById("text-2");

paragraph.style.color = "red";

// now our paragraph is red
```

It can be tricky to remember all of the different attributes and locations we want to modify, but don't worry. It's pretty easy to find this stuff online.

Let's say we wanted to make our font bold, but we weren't sure how. This might seem reasonable.

```javascript
const paragraph = document.getElementById("text-3");

paragraph.font = "bold";
```

You launch your website, but the text isn't bold. Hm. It is certainly possible, but we need to change how we're going about doing this. A quick Google search for _"change font to bold in javascript"_ reveals a couple of things.

* We need to set the `fontWeight` property, not the `font` property.
* The `fontWeight` property is nested under the `style` property, not on the `paragraph` itself.

Let's make those changes and see if we can get our code working.

```javascript
const paragraph = document.getElementById("text-3");

paragraph.style.fontWeight = "bold";
```

There we go! Everything is up-and-running. Google can be your best friend if you know how to narrow down what you're looking for. Any problem you're facing was likely solved long ago. Do a little digging and I'm sure you'll find a solution.

## Creating and Adding Elements

To create a new element \(i.e., a new tag to be inserted into your HTML\), we can use the `createElement` method of the `Document` object.

```javascript
const paragraph = document.createElement("p");

// this creates a new paragraph element. the createElement method
// uses our input (in this case, the "p") to determine what type of
// element to create.

// now we can add content and styling as needed

p.innerHTML = "Hello, world!";
p.style.color = "blue";
```

In the example above, we created a `<p>` element by typing `"p"` in the parenthesis of the `createElement` method. If we replaced `"p"` with `"img"`, the `createElement` method would create an `<img>` element. This works equally well for any HTML tag.

{% embed url="https://www.youtube.com/watch?v=an-6owXUwdg&list=PLyuRouwmQCjmQTKvgqIgah03HF1wrYkA9" %}

Creating elements is great, but we need to actually add them to our pages. There are quite a few ways to do this, depending on where we want to insert our content.

* `append`
* `prepend`
* `before`
* `after`

### Location, Location, Location

Appending an element means you're adding it at the very end of the parent node. On the other hand, prepending an element means you're adding it at the very beginning of the parent node.

Suppose we have the following HTML structure. Assuming we've used the getElementById method to get the `<ul>` element, we can use these built-in methods to place newly created elements into our HTML.

```markup
<html>
    <body>
        <div>
            <!-- ul.before(...) would insert an element here -->
            <ul id="list">
                <!-- ul.prepend(...) would insert an element here -->
                <li>This is the first item.</li>
                <li>This is the second item.</li>
                <li>This is the third item.</li>
                <!-- ul.append(...) would insert an element here -->
            </ul>
            <!-- ul.after(...) would insert an element here -->
        </div>
    </body>
</html>
```

Let's take a look at fully functional example.

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>
<html>
    <head>
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <div>
            <p>I was inserted using the before method.</p>
            <ul id="list">
                <li>I was prepended,</li>
                <li>This is the first item.</li>
                <li>This is the second item.</li>
                <li>This is the third item.</li>
                <li>I was appended.</li>
            </ul>
            <p>I was inserted using the after method.</p>
        </div>
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
const list = document.getElementById("list");

const firstItem = document.createElement("li");
firstItem.innerHTML = "I was prepended.";

const lastItem = document.createElement("li");
lastItem.innerHTML = "I was appended.";

const beforeParagraph = document.createElement("p");
beforeParagraph.innerHTML = "I was inserted using the before method.";

const afterParagraph = document.createElement("p");
afterParagraph.innerHTML = "I was inserted using the after method.";

list.prepend(firstItem);         // prepend
list.append(lastItem);           // append
list.before(beforeParagraph);    // before
list.after(afterParagraph);      // after
```
{% endtab %}
{% endtabs %}

These are relatively new methods, and are much more streamlined than their legacy counterparts. However, you may still encounter older code that uses these legacy methods.

* `appendChild`
* `insertBefore`
* `insertAdjacentElement`

This perform similar functions, but do so in less intuitive way. You can find plenty of documentation on these online if you wish to dig a little deeper.

## Removing or Replacing Elements

If we can create and insert new elements, then we must be able to remove \(or replace\) them, too.

* `remove`
* `replaceWith`

All we need to do to remove an element is access it using one of the methods we've already learned, then use the `remove` method.

```javascript
const element = document.getElementById("remove-me");

element.remove();    // and it's gone!

// this, of course, assumes there is an element already in our
// HTML whose ID is remove-me
```

If we want to remove a particular element and replace it with another, we can do that in one shot.

```javascript
const oldElement = document.getElementById("replace-me");

const newElement = document.createElement("p");
newElement.innerHTML = "Time for an upgrade!";
newElement.id = "upgrade";

oldElement.replaceWith(newElement);

// this assumes that there is an existing element in our HTML
// whose ID is replace-me. this element is replaced by our
// newly created paragraph element
```

These, too, are fairly new. You should be aware of legacy methods that perform similar functions.

* `removeChild`
* `replaceChild`

If you're ever tasked with maintaining legacy code, you'll likely run into some of these.

