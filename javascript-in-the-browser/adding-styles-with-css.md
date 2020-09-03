# Adding Styles with CSS

## Applying CSS to HTML

There are three ways to apply styles to your HTML using CSS: an internal stylesheet, an external stylesheet, and inline styles. Skilled web developers opt for external stylesheets, as they provide a greater degree of organizational control. Internal stylesheets and inline styles should be avoided if at all possible, and are typically used for one-off content styling.

{% embed url="https://www.youtube.com/watch?v=Tfjd5yzCaxk" %}

### External Stylesheets

When using an external stylesheet, you create a `.css` file and put all of your styles in there. You then reference that file using a `link` tag from the `head` section of your HTML file.

```markup
<!DOCTYPE html>

<html>
    <head>
        <title>CSS</title>
        
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <p>This is paragraph is styled using CSS!</p>
    </body>
</html>
```

The `rel` attribute specifies a relationship between the HTML document and another linked resource \(in this case, a stylesheet\). More importantly, the `href` attribute tells the browser where to find the `.css` file.

As I mentioned, a stylesheet contains all of the styles you're applying to your HTML. A simple one might look something like this.

```css
p {
    color: blue;
}
```

I'm glossing over some details for now, but this will make all paragraphs \(i.e., content enclosed by a `p` tag\) blue. We'll get much more into how to style your content later.

### Internal Stylesheets

An internal stylesheet is contained within the HTML file itself. You can apply the same styling as you can with an external sheet.

```markup
<!DOCTYPE html>

<html>
    <head>
        <title>CSS</title>
        
        <style>
            p {
                color: blue;
            }
        </style>
    </head>
    <body>
        <p>This is paragraph is styled using CSS!</p>
    </body>
</html>
```

Instead of linking an external stylesheet, you use the `style` tag and write your CSS right in the `head` section of your HTML document.

This isn't nearly as efficient as an external sheet, though. If you need to style multiple pages, then you need to copy your internal stylesheet to each HTML document. If you use an external stylesheet, you can link it in as many pages as you want.

### Inline Styles

An inline style affects a single element, and is included using the `style` attribute for that element.

```markup
<!DOCTYPE html>

<html>
    <head>
        <title>CSS</title>
    </head>
    <body>
        <p style="color: blue;">This is paragraph is styled using CSS!</p>
    </body>
</html>
```

If you're working in a restrictive environment that doesn't allow external or internal stylesheets, then you don't really have a choice. However, you should avoid using inline styles when you can. It can be a nightmare to modify and maintain a website like this.

## Selectors

CSS has rules, which is how it determines the elements to style and how to style them. Rules have two components: selectors and properties. A selector is a pattern that informs the browser of the HTML elements to which a property should be applied.

```css
p {
    color: blue;
    text-align: right;
}
```

The selector is `p` and the properties are `color` and `text-align`. This tells the browser that all paragraphs should be aligned to the right and displayed in blue font. We'll review many of the simple selectors, as well as some more advanced techniques. Check out the [W3C documentation](https://www.w3.org/TR/selectors-3/#selectors) for the full specification.

### Listing Selectors

Sometimes you might want to style more than one type of element the same way. Suppose you wanted to underline your h2 and h3 tags.

```css
h2 {
    text-decoration: underline;
}

h3 {
    text-decoration: underline;
}
```

This works perfectly well, but it's a little redundant. You can represent this more succinctly.

```css
h2, h3 {
    text-decoration: underline;
}
```

Some developers prefer to list each selector on its own line for clarity.

```css
h2,
h3 {
    text-decoration: underline;
}
```

### Type Selectors

A type selector is sometimes referred to as a tag selector or element selector, as they simply replicate HTML tag names. We looked at several HTML tags in the previous section, and all of them can be used as type selectors in CSS.

```css
body {
    background-color: black;
}

h1 {
    font-size: 21px;
}

p {
    text-align: right;
}

ol {
    margin: 10px;
}

li {
    text-decoration: underline;
}

a {
    color: red;
}

img {
    height: 100px;
    width: 1000px;
}

table {
    border: 1px solid blue;
}

tr {
    padding: 7px;
}

th {
    font-weight: bold;
}

td {
    font-style: italic;
}
```

#### The Universal Selector

The universal selector is used to target every element in the HTML document. It's often used as a reset, so you know you have a clean working slate on which to start building your application.

```css
* {
    margin: 0;
    padding: 0;
}
```

This sets the `margin` and `padding` to `0` for every element on the page.

### Class Selectors

A class selector begins with a period \(sometimes called a full stop\). If you've added classes to your HTML elements, you can target those elements specifically in this way.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>Styling</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <h1 class="section-header">Section 1</h1>
        <p class="section-content">This is some content</p>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
.section-header {
    color: black;
    font-size: 21px;
    font-weight: bold;
}

.section-content {
    color: gray;
    font-size: 14px;
    font-style: italic;
}
```
{% endcode %}

The style properties defined in the `.section-header` rule are applied to the `h1` tag in `index.html`. Likewise, those defined in the `.section-content` rule are applied to the `p` tag.

#### Elements within Classes

It's common for web developers to apply the same class to different elements. Using a combination of type and class selectors, you can target specific elements.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>Styling</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <h1 class="section">Section 1</h1>
        <p class="section">This is some content</p>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
.section {
    text-align: right;
}

p.section {
    color: gray;
}
```
{% endcode %}

Using the `.section` rule, we've aligned the content of both the `h1` and `p` tags to the right. The `p.section` rule specifically targets paragraphs who have a class attribute of `section`. These elements will be displayed in gray.

#### Elements with Multiple Classes

You can apply more than one class to an HTML element. You separate each class with a single space.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>Styling</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div class="box">Text inside of a box.</div>
        <div class="box shaded">Text inside of a shaded box.</div>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
.box {
    border: 1px solid black;
}

.box.shaded {
    background: yellow;
}
```
{% endcode %}

The `.box` class puts a border around any elements with that class attribute. In this example, that's both of the `div`s. The second `div` has two classes: `box` and `shaded`. You can target this in your CSS by chaining the two classes together in your selector: `.box.shaded`. This shades the box outline in yellow.

### ID Selectors

An ID selector is used in much the same way as a class. You can add an `id` attribute to an HTML element, and then target this element in your CSS.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>More CSS</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div>My first section.</div>
        <div id="section2">My second section.</div>
        <div>My third section.</div>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
#section2 {
    border: 1px solid red;
}
```
{% endcode %}

The second `div` marked with an `id` of `section2` will be rendered with a red border.

### Attribute Selectors

An attribute selector allows you to target elements based on the presence of an attribute, as well as by the value of that attribute. Generally, it takes the following form.

```css
selector[attribute] { }
selector[attribute=value] { }
```

Let's take a look at a more concrete example.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>More CSS</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <a href="https://bing.com" title="Bing">Bing</a>
        <a href="https://google.com">Google</a>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
a[title] {
    color: red;
}

a[href="https://google.com"] {
    color: green;
}
```
{% endcode %}

Any hyperlinks with a `title` attribute \(regardless of value\) will be displayed in red. Any hyperlink whose `href` value is `https://google.com` will be displayed in green.

### Pseudo-classes and Pseudo-elements

A pseudo-class is a special type of selector that targets an element that is in a certain state. Let's take a look at what we mean by state and how this can be useful to us as we create applications.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>More CSS</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div>
            <p class="first">First paragraph.</p>
            <p>Second paragraph.</p>
            <p>Third paragraph.</p>
        </div>
    </body>
</html>
```
{% endcode %}

I want the first paragraph in my `div` to stand out a little. So I added a class and made it bold.

{% code title="styles.css" %}
```css
div p.first {
    font-weight: bold;
}
```
{% endcode %}

This works just fine, but it doesn't scale very well. What if I started adding more and more `div` elements with more and more first paragraphs that needed to be bold? I would have to make sure to add the `.first` class to every single paragraph. A much more scalable approach would be to use the `:first-child` pseudo-class.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>More CSS</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div>
            <p>First paragraph.</p>
            <p>Second paragraph.</p>
            <p>Third paragraph.</p>
        </div>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
div p:first-child {
    font-weight: bold;
}
```
{% endcode %}

Now, the first paragraph inside of every `div` will be bold. No need to add any classes anywhere. There are similar pseudo-classes for `:last-child`, `:only-child`, and `:nth-child`.

Other pseudo-classes target user actions rather than where in the DOM an element is located. Links are a really common example for these types of selectors.

{% code title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>More CSS</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div>
            <a href="https://bing.com">Bing</a>
            <a href="https://google.com">Google</a>
            <a href="https://yahoo.com">Yahoo</a>
        </div>
    </body>
</html>
```
{% endcode %}

{% code title="styles.css" %}
```css
a {
    color: blue;
}

a:hover {
    color: red;
}

a:visited {
    color: green;
}
```
{% endcode %}

Each of the three links are displayed in green. This comes from the type selector on the first three lines of the CSS file. The others, `:hover` and `:visited`, are pseudo-classes. If a user hovers the mouse over a link, it'll change colors \(to red\). Links that a user has already visited will be displayed in green.

### Combinators

We've seen an example or two of these before, but a combinator is pretty much what it sounds like: a combination of other types of selectors.

#### Descendants

A descendant selector follows the hierarchy of the DOM. Suppose you had the following structure.

```markup
<div>
    <p>A section on the page.</p>
    
    <ul>
        <li>An item on the list.</li>
    </ul>
</div>
```

You can target specific elements based on their lineage \(i.e., the parent-child relationship\). The `div` is the top-level element, so we'll refer to it as the parent. It has two children: a `p` tag and a `ul` tag. The unordered list, in turn, has a single child: an `li` tag.

```css
div p {
    /* targets the paragraph */
}

div ul {
    /* targets the unordered list */
}

div ul li {
    /* targets the list item */
}
```

#### Direct Children

The more nesting you add to your HTML structure, the more specific your CSS selectors need to become. If you've got multiple lists nested within each other, each of which have their own list items, you need to be careful in how you target them.

```markup
<ul>
    <li>An item in the outer list</li>
    <li>
        <ol>
            <li>An item in the inner list</li>
            <li>Another item in the inner list</li>
        </ol>
    </li>
</ul>
```

Let's see if we can put a border around the list items of the unordered \(i.e., outer\) list\).

```css
ul li {
    border: 1px solid black;
}
```

This will put a border around all of the list items, including those nested underneath the `ol` tag. Not quite what we wanted.

```css
ul > li {
    border: 1px solid black;
}
```

That's more like it. Now, we're targeting only direct descendants of the `ul` element.

#### Siblings

Two elements are considered siblings if they're positioned at the same hierarchy.

```markup
<div>
    <p>A</p>
    <img src="some/image.png" />
    <ul>
        <li>An item</li>
    </ul>
</div>
```

Each of the elements in this `div` are siblings. The paragraph and image are adjacent siblings, as are the image and unordered list.

You can target adjacent siblings using the adjacent sibling combinator. Here, we're targeting `img` elements that are adjacent to `p` elements.

```css
p + img {
    border: 1px solid black;
}
```

Use the general sibling combinator to target siblings who aren't necessarily adjacent to one another. This will target any `ul` elements that are siblings of the paragraph \(even though there's an `img` element between them\).

```css
p ~ ul {
    color: red;
}
```

## Cascade, Specificity, and Inheritance

CSS stands for cascading style sheets, so the concept of cascading is pretty pivotal to how all of this stuff works. As you begin to write more and more CSS, you will inevitably encounter a situation in which the rules you define aren't applied in the way you thought they would be. As you sift through the reasons why, this is a good place to start.

### Cascade

The order in which you write your rules matters. If two rules with the same specificity are applied to the same element, the one that appears latest in the file will be used.

```css
p {
    color: red;
}

p {
    color: blue;
}
```

These rules are conflicting. The browser will use the second `p` rule, and your paragraphs will be blue.

### Specificity

Each selector is assigned a different level of specificity, and those with greater specificity \(i.e., more specific\) are given priority.

* Type selectors are the least specific.
* Class selectors are more specific than type selectors, but less specific than ID selectors.
* ID selectors are the most specific.

```markup
<p id="one" class="two">My paragraph.</p>
```

```css
#one {
    color: red;
}

.two {
    color: blue;
}

p {
    color: green;
}
```

Since the specificity of these selectors differ, the order isn't taken into account. The most specific selector is used, so the paragraph will be red.

### Inheritance

This can be a little tricky. Some properties that are set on parent elements are inherited by their children, but others are not.

Things like color are inherited. So, if you set the color of a `div` to blue, all subsequent text elements inside of that `div` be blue, too.

```css
div {
    color: blue;
}
```

However, if you also set the width of that div to 50%, its child elements will have a width of 100% \(unless other set individually\).

```css
div {
    color: blue;
    width: 50%;
}
```

Time to put your newfound web design skills to the test. Problem sets are a thing of the past. Welcome to the world of projects! Don't worry, I'm not throwing you in the deep end yet. First, a tutorial.

And now I am throwing you in the deep end!

