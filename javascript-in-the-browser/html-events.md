# HTML Events

## Responding to User Actions

Events are triggered by certain actions the user might take. The browser fires an event to let your application know that something happened, thereby allowing your application to respond in kind.

{% embed url="https://youtu.be/EaRrmOtPYTM" %}

There are many, many events, but we'll focusing on just the more commonly used ones.

{% tabs %}
{% tab title="Window Events" %}
| Event | Description |
| :--- | :--- |
| `onload` | Fires after the page is finished loading. |
{% endtab %}

{% tab title="Form Events" %}
| Event | Description |
| :--- | :--- |
| `onchange` | Fires the moment the value of an element is changed. |
| `onsubmit` | Fires when a form is submitted. |
{% endtab %}

{% tab title="Keyboard Events" %}
| Event | Description |
| :--- | :--- |
| `onkeydown` | Fires when a user is pressing a key. |
| `onkeyup` | Fires when a user releases a key. |
{% endtab %}

{% tab title="Mouse Events" %}
| Event | Description |
| :--- | :--- |
| `onclick` | Fires when the user clicks an element. |
| `onmouseout` | Fires when the mouse pointer moves out of an element. |
| `onmouseover` | Fires when the mouse pointer moves over an element. |
{% endtab %}
{% endtabs %}

### Window Events

The `onload` event is the simplest of them all. It is triggered when the website finishes loading, which allows us to execute a block of code as soon as the page loads.

```javascript
window.onload = function() {
    // perform application setup here
}
```

### Form Events

There are two primary form events we'll need to understand: `onchange` and `onsubmit`.

The `onchange` event fires whenever the value of an element is changed. This can be incredibly useful when building a responsive application that renders \(and re-renders\) itself to reflect realtime changes.

```javascript
const element = document.getElementById("id");

element.onchange = function(e) {
    // e is the event, which will have attributes
    // related to the change that was made
    
    // respond accordingly to the change here
}
```

The `onsubmit` event, on the other hand, is only fired when a form is submitted. This would trigger the input validation and submission routines that typically happen after the user finishes entering his or her information.

```javascript
const form = document.getElementById("form");

form.onsubmit = function(e) {
    // e is the event, which will have attributes
    // related to information submitted on the form
    
    // validate input and submit, which in a real-world
    // application would mean sending data to the
    // server and storing it in a database
}
```

### Keyboard Events

Naturally, there are many keyboard events. We'll focus on just `onkeydown` and `onkeyup`. They are both fairly straightforward.

{% embed url="https://www.youtube.com/watch?v=5-koI06rmcA&list=PLyuRouwmQCjmQTKvgqIgah03HF1wrYkA9" %}

`onkeydown` fires when a user presses a key \(more specifically, the action of pressing the key down\). `onkeyup` fires when a user releases a previously pressed key. These can both be useful in capturing the pressing of single keys \(like pressing Enter to submit a form\).

```javascript
const input = document.getElementById("element");

input.onkeydown = function(e) {
    // e is the event, which will have attributes
    // related to the key that was pressed
}

input.onkeyup = function(e) {
    // e is the event, which will have attributes
    // related to the key that was released
}
```

### Mouse Events

There are a few important mouse events, and we'll be turning our attention to `onclick`, `onmouseout`, and `onmouseover`.

`onclick` is more utilitarian. It fires whenever a user clicks an element. This is usually in the form of a button click, which tells the application to perform some action.

```javascript
const button = document.getElementById("button");

button.onclick = function(e) {
    // e is the event, which will have attributes
    // related to the button click
    
    // when it is clicked, we can do any number of things:
    //    update the css styling
    //    add html elements to the dom
    //    whatever the situation requires
}
```

`onmouseout` and `onmouseover` are more aesthetically-focused. `onmouseout` fires when the pointer moves out of an element, whereas `onmouseover` fires when the mouse moves over an element. These can be used to create hover effects for stylistic purposes.

```javascript
const image = document.getElementById("img");

image.onmouseover = function() {
    // maybe we add a border to the image when a user
    // hovers the mouse over it
}

image.onmouseout = function() {
    // assuming we add a border to the image when a
    // user hovers, we remove that border when a
    // user stops hovering
{
```

Each of these events could be used as attributes of HTML elements. However, it is better practice to reference these events in our JavaScript rather than in our HTML.

If you want to learn more about all of the HTML events available to you, check out the [W3Schools article on HTML Event Attributes](https://www.w3schools.com/tags/ref_eventattributes.asp).

Ready to put these skills to the test? A few quick tutorials will help you get your feet under you.

{% page-ref page="../tutorials/tutorial-1.md" %}

{% page-ref page="../tutorials/tutorial-2.md" %}

{% page-ref page="../tutorials/tutorial-3.md" %}

And now it's time to fly on your own!

{% page-ref page="../projects/project-1.md" %}

{% page-ref page="../projects/project-2.md" %}

{% page-ref page="../projects/project-3.md" %}

