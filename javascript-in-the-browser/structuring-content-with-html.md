# Structuring Content with HTML

## Overview

HTML is not a programming language, but rather a markup language. It tells the browser how to structure the websites you visit online. HTML consists of a series of tags \(or elements\) that enclose the content you wish to display on the browser. The tags you use determine how this content appears to those visiting your page.

{% embed url="https://www.youtube.com/watch?v=XiQ9rjaa2Ow" %}



### Anatomy of a Tag

Let's start with a simple paragraph element.

```markup
<p>This is a paragraph.</p>
```

This element is made up of several components.

* Opening tag
* Content
* Closing tag

A tag encloses the content of an HTML element. Typically, there is an opening tag and a closing tag. Opening tags contain angled brackets, as well as the name of the tag. Closing tags contain the same things, except there's a `/` before the name of the tag.

The opening paragraph tag looks like this.

```markup
<p>
```

And the corresponding closing tag looks like this.

```markup
</p>
```

The text between these tags is the content of the paragraph. Put all three of these together and you have the entire element.

### Tag Attributes

In addition to their content, tags can have a number of attributes. We'll dive a little more deeply into these later, but let's take a look at a simple example.

```markup
<p class="apcsp">This is a paragraph.</p>
```

The `class` attribute is used for styling effects with CSS, which you'll learn all about in the next section. Attributes contain information that doesn't appear in the content of the element \(like how to render that content\).

An attribute has a name and a value \(in this case `class` and `apcsp`\). Attribute names are always followed by an equals sign, and their values are always surrounded by double-quotes.

Some tags, admittedly, break the opening and closing paradigm. These tags are special tags that are self-closing. Consider the `br` tag, which creates a line break.

```markup
<br />
```

Some tags are not designed to enclose content, and the `br` tag is one of them. When this is the case, these tags often close themselves in the same tag in which they were opened.

### Nesting Tags

Tags can be nested inside of each other to create more complex page structures.

```markup
<div>
    <p>This is a first paragraph.</p>
    <p>This is a second paragraph.</p>
</div>
```

A `div` is used to logically group related elements. We'll talk more about this later. Focus on the concept of nested two paragraphs inside of a single `div` to create a section on the page.

Remember, you need to close your tags in the order in which you opened then. Since we opened up a div element first, we close it last. Each individual paragraph is opened and closed inside of the `div`.

### Anatomy of a Document

A document type declaration \(or, more colloquially, `DOCTYPE`\) tells the browser what type of document it is reading, which gives it some direction on how it should be rendered. In the past, there have been a number of declaration formats depending on the version of HTML or XHTML in use.

Luckily for us, the advent of HTML5 has vastly simplified the required declaration. Simply type this as the first line of every HTML5 document you create.

```markup
<!DOCTYPE html>
```

That's it! Now, the browser knows this is an HTML5 document and should be treated as such. 

Every HTML5 begins and ends with an opening and closing `html` tag. These tags enclose all of the content of the page.

```markup
<!DOCTYPE html>

<html>
   <!-- everything goes in here -->
   <!-- by the way, this is how you write a comment in HTML -->
   <!-- it will be ignored by the browser -->
</html>
```

Everything that makes up your page needs to be inside these tags. The `DOCTYPE`, as you see, is external to these tags. It is placed above the opening `html` tag.

The contents of the `html` tag is further divided into two tags: `head` and `body`.

```markup
<!DOCTYPE html>

<html>
   <head>
      <!-- metadata, which means data about data -->
   </head>

   <body>
      <!-- content to be displayed in the browser -->
   </body>
</html>
```

The `head` section contains metadata about the page. For now, we'll only use it as a place to put the `title` tag \(i.e., the text that appears in the browser tab\). Later, we'll use this section to link CSS and JavaScript files that our page will use.

The `body` section contains all of the content that you wish to be displayed by the browser. Text, links, images, tables. All of the stuff that makes a website what it is goes here.

## Text and Lists

The vast majority of content you add to your pages will be in the form of text or lists of text.

### Headings

There are six different tags that allow us to create headings of various sizes.

* `h1`
* `h2`
* `h3`
* `h4`
* `h5`
* `h6`

The `h1` tag is used for main headings, and as such, it is the largest and most prominent. The `h2` tag is used for subheadings. Each heading, from `h1` to `h6`, is gradually smaller and less prominent than the one before it.

{% tabs %}
{% tab title="H1" %}
The `h1` tag is the largest and most prominent header. It should be used for main section headings. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h1>This is an H1 tag.</h1>
    </body>
</html>
```
{% endtab %}

{% tab title="H2" %}
The `h2` tag is the second largest and most prominent header. It should be used for subheadings of main sections. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h2>This is an H2 tag.</h2>
    </body>
</html>
```
{% endtab %}

{% tab title="H3" %}
The `h3` tag is the third largest and most prominent header. It should be used for teriary headings of main sections. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h3>This is an H3 tag.</h3>
    </body>
</html>
```
{% endtab %}

{% tab title="H4" %}
The `h4` tag is the third smallest and least prominent header. It should be used for minor headings. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h4>This is an H4 tag.</h4>
    </body>
</html>
```
{% endtab %}

{% tab title="H5" %}
The `h5` tag is the second smallest and least prominent header. It should be used for minor headings. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h5>This is an H5 tag.</h5>
    </body>
</html>
```
{% endtab %}

{% tab title="H6" %}
The `h6` tag is the smallest and least prominent header. It should be used for minor headings. Here's how you'd structure it in your HTML.

```markup
<!DOCTYPE html>

<html>
    <body>
        <h6>This is an H6 tag.</h6>
    </body>
</html>
```
{% endtab %}
{% endtabs %}

### Paragraphs

Paragraphs are pretty straightforward, and we've already looked at a couple examples. Much of your content will be enclosed in `p` tags.

```markup
<p>This is a single paragraph.</p>
```

Remember, a paragraph has a slight margin above and below it by default.

### Lists

There are two types of lists available to you: ordered and unordered. An ordered list is numbered, whereas an unordered list is bulleted.

#### Ordered Lists

Use an `ol` tag when you need to display a list of content in a specific, numbered order.

```markup
<ol>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
</ol>
```

The `ol` makes use of another a tag: `li`. Each list item is enclosed by its own `li` tags, and nested inside of the enclosing `ol` tags. This will be rendered in the browser like so.

1. First
2. Second
3. Third

#### Unordered Lists

Use a `ul` tag when you need to display a list of content without any particular order. The list will use bullet points to denote each item.

```text
<ul>
    <li>Some item</li>
    <li>Another item</li>
</ul>
```

Like the `ol`, the `ul` also makes use of nested `li` tags. This will be rendered in the browser like so.

* Some item
* Another item

#### Nested Lists

Like any other tag, list tags can be nested inside of one another to each sublists.

```markup
<ul>
    <li>First item</li>
    <li>
        <ul>
            <li>First subitem</li>
            <li>Second subitem</li>
        </ul>
    </li>
</ul>
```

When rendered in the browser, this will look like so.

* First item
  * First subitem
  * Second subitem

And while we used two unordered lists, you can just as easily nest ordered lists inside of unordered lists \(or the other way around\), too.

### Emphasis and Importance

There is an `em` tag to signal a greater degree of emphasis, a `strong` tag to indicate that a piece of text is a little more important than the rest.

#### Emphasis

In spoken languages, we can stress certain words to add emphasis. In HTML, we use the `em` tag.

```markup
<p>This paragraph is <em>very</em> important.</p>
```

Visually, this adds italics.

> This paragraph is _very_ important.

The `i` tag does this, too, but it's a little outdated. The `em` tag adds italics, and will communicate the added emphasis via screen readers for visually impaired users of our websites. The `i` tag only italicizes the text, which is lost on screen readers.

#### Important

To add a stronger degree of importance, you can use the `strong` tag.

```markup
<p>Please <strong>do not</strong> use this door.</p>
```

Visually, this bolds the designated text.

> Please **do not** use this door.

Again, there's an outdated `b` tag that bolds text, as well. The `strong` tag provides the visual bolding of the text, but also plays nicely with screen readers and other devices that assist visually impaired users in navigated websites.

## Links

In many ways, hyperlinks are one of the most important tags you'll learn. They're what make the Web a web. To create a link, use the `a` tag \(which stands for anchor\).

```markup
<a href="https://www.google.com">Google it!</a>
```

Remember tag attributes? Well, the anchor tag uses one. It's called an `href` attribute, and it tells the link where to go when it's clicked. There are other optional attributes, such as the `target` attribute, which tells the link whether it should open in the same tab or a new one.

## Images

Images use the `img` tag, and it's another one of those self-closing tags. There are a few important attributes you'll need to include, as well.

```markup
<img src="path/to/img.png" />
```

The `src` attribute tells the browser where to find the image. Sometimes this is local to your website \(i.e., on the same server\). Other times, it's a URL that points to somewhere else on the Web. It works a lot like the `href` attribute of links.

### Sizing

You can provide specific sizing instructions to your images directly in the tag. Later, we'll learn a more sophisticated way to do things like this.

```markup
<img src="path/to/img.png" height="100px" width="100px" />
```

The `height` and `width` values are commonly represented in pixels, which are the smallest unit of programmable color on a screen.

## Tables

Tabular data is best presented in \(you guessed it!\) tables.

```markup
<table>
    <!-- your table data here
</table>
```

There's a bit more to it, of course. This is just the outer shell. There are two primary sections. The header and the body.

### Header

The header details the column headers, while the body contains the row and column data.

```markup
<table>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
</table>
```

A few more tags to discuss. The `thead` tag groups all table header information together. Anything within this section will be used to format and populate the table headers.

The `tr` tag represents a single row in the table. In this case, the header row. Each `th` tag represents a single column in the header row.

### Body

The next section is the body, which contains all of the table data.

```markup
<table>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
            <td>Data 3</td>
        </tr>
    </tbody>
</table>
```

The `tbody` section looks a lot like the `thead` section. The `tr` tag still represents a single row in the table. The `td` tags represent individual cells in the table.

If you put it all together, you'll have an entire table.

```markup
<table>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
            <td>Data 3</td>
        </tr>
    </tbody>
</table>
```

There's also a less commonly used `tfoot` tag that outlines a specific footer section.

