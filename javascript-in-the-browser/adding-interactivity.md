# Adding Interactivity

## Client-side JavaScript

Up to this point, we've focused on learning the fundamentals of the JavaScript programming language without any of the flashiness of the browser. We wrote simple programs and executed them in the terminal. JavaScript, though, owes much of its existence to the browser, and we're going to learn how to leverage the power of JavaScript in our websites and applications.

{% embed url="https://www.youtube.com/watch?v=fWDVDm4HRwA&list=PLyuRouwmQCjmQTKvgqIgah03HF1wrYkA9" %}

### Embedding JavaScript

If you were hoping you'd never see HTML again, well...it's back. In much the same way as we including CSS in our HTML, we can include JavaScript, too. There are three primary ways in which we can do this.

* Inline `script` tags
* Externally-linked source files
* As HTML attributes

Though these \(an other\) options are available to you, externally-linked source files are almost always preferred. It's easier to manage your code, and cleaner to decouple your JavaScript, HTML, and CSS files. For the sake of thoroughness, let's take a look at an example of each.

### Inline JavaScript

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>My Website with JavaScript</title>
    
        <script>
            // i can write whatever javascript i want right here
            
            // anything between these script tags is interpreted
            // as javascript code, just like in a .js file
        </script>
    </head>
    <body>
        <!-- body of page -->
    </body>
</html>
```
{% endtab %}
{% endtabs %}

This sort of thing should probably be avoided, especially on larger applications. The more you mix your HTML and JavaScript \(or your HTML and CSS, for that matter\), the more cluttered your files become.

### Externally-linked JavaScript

When you embed an external source file, you use a `script` tag in the `head` section of your HTML file. Just like CSS, this tells the browser where to find the JavaScript file.

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>My Website with JavaScript</title>
    
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <!-- body of page -->
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
// this is where we'll write our javascript

// any code we write here will be executed on the browser

// we can display popup messages

// we can modify our html or css

// or we can respond to user interaction

// later we'll learn how to do all of these things

```
{% endtab %}
{% endtabs %}

This code doesn't do anything as it stand, but we'll learn how to replicate this structure to create interactive applications that run in the browser.

### JavaScript as HTML Attributes

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>

<html>
    <head>
        <title>My Website with JavaScript</title>
    
        <script type="text/javascript" src="example.js"></script>
    </head>
    <body>
        <button onclick="doSomething()">Click me!</button>
    </body>
</html>
```
{% endtab %}

{% tab title="example.js" %}
```javascript
function doSomething() {
    // do something when user clicks button
}
```
{% endtab %}
{% endtabs %}

Using HTML attributes for your JavaScript is generally considered bad practice. We're covering them so you know it exists, but we'll see much better ways of doing this.

