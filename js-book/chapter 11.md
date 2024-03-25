# Chapter 11: Accessing HTML components
By now we've learned probably everything we need to know to begin writing our own triggers for HTML.
First off, html is accessed by accessing special ids, classes, or just the tag name.

We can access an html element by certain attributes. Below is a list of functions we can use to access elements.

- document.getElementById("id")            | accesses an element via it's id.
- document.getElementsByClassName("class") | accesses an array of elements via class name.
- document.querySelector("selector")       | accesses the first element that matches the query selector given (query selector as in css selector)
- document.querySelectorAll("selector")    | very similar to querySelector(), only it returns an array of elements.

We can use the css selectors given in chapter 4, using # to indicate an id and . to indicate a class, as well as element names and etc for the query selector functions.

Each of these functions gives us an object that refers to an HTML element, or an array multiple HTML elements inside an array.

Let's look at what we can do with these elements.

```js
document.getElementById("welcome-header").innerText = "Welcome!"
```
we can see it has an element called innerText. A very small list of other properties of the element include

- `innerHTML`
- `style`
- `addEventListener()`
- `click()`
- `blur()`
- `focus()`

and a whole ton of others, pertaining to element widths, scrollbars, essentially anything pertaining to that element. [visit this website](https://www.w3schools.com/jsref/dom_obj_all.asp) I found for the whole list.

Now, let's start at `innerText`. `innerText` and `innerHTML` are extremely similar, the only difference is that `innerText` can't add elements to the innertext. This is especially useful when preventing things like *cross site scripting* which happens when someone inputs valid HTML into a field into a blog or something, and the blog interprets that input as actual HTML. On the other hand, if you would like to add extra elements inside the element, you can use .innerHTML, just be weary of XSS (cross site scripting).

To change the text of an element, we can use innerText or innerHTML. The better practice is innerText, and you can use it like this
```js
let element = document.querySelector("#info-text")
element.innerText = "Invalid login credentials"
```
We can also change the styles of an element using the style object.
```js
let el = document.querySelector("body") // el now equals the body element
el.style.color = "#555" //#555 is a shade of grey
```
The code above essentially just turns the body element grey, useful for dark themes and etc.

The style object also contains a TON of other things, not only color but background color, width, margin, essentially any style that exists. View the full list [here](https://www.w3schools.com/jsref/dom_obj_style.asp)
In the `<input>` element, instead of `innerHTML` there is a `.value` property, which makes sense because `<input>` doesn't have an ending tag. To change the value inside an `<input>` element, we change the `element.value` property, since it doesn't have a `element.innerHTML` property.

Now, we need to know how to add a trigger of course, so when we press a button or something it does something. To do that, we use the `element.addEventListener()`. function. This function is actually a callback function, which was discussed in chapter 8.

The `element.addEventListener()` function has two parameters. The first parameter is the event name. There are a wide variety of events, for now we'll just use `click`. The second parameter is a callback function. Inside the callback you can specify what you'd like to happen once the event happens. Here's an example.
```js
let el = document.getElementById("button")
el.addEventListener("click"(e) => {
    el.style.backgroundColor = 'blue'
    el.value = 'Clicked!'
})
```
The `e` variable defined as a parameter for the callback pertains to the event. In some cases, such as keyboard events, it will tell you the key pressed and other important information.

Note that the `el` variable is probably going to be a `<input type="button" id="button">`, as we're using `el.value`, and accesssing it by the `button` id.

Try creating your own little website with event handlers and things, if you really want a challenge, try creating your own tic-tac-toe game that changes the innerHTML of the element to either x/o based on whose turn it is.
