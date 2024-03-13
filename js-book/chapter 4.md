# Chapter 4: CSS
By now you've probably built your own little website, possibly discovered some cool elements not mentioned in this book. However, it probably looks pretty bland. How do we not make it look bland? CSS. CSS is the acronym for "cascading style sheets", although people usually just shorten it to CSS. First, let's see how exactly to implement CSS.

There are 3 ways to implement CSS.
- inside the element
- inside a .css file
- inside of a <style></style> element.

First let's focus on the <style></style> element. This is intended to be put inside the <head> tag. Because well, even though the code inside the <style> tag is displayed, the element itself isn't actually displayed.

Now, to write CSS, we have to understand how elements are referenced.

To reference an element with the id of welcome-header, or the equivalent, you just add a # in front. So #welcome-header. It's the same thing with classes, only you add a period. For example, .blue-text.
In addition to id's and classes, you can also style every element, by it's tag name. For example the body element, would just be body in CSS. You can also specify a tag name, followed by its class or id. For example, div.menu would reference all <div> elements with a class of 'menu', and you can also specify div#menu to access divs with the id of 'menu' in the same way.

Now, the structure of CSS inside a file or <style> element is like follows:
```
[element or group of elements] {
    [attribute]:[value];
    [attribute]:[value];
}
```
Now you can continue to keep adding values to these attributes like so. An attribute is just the name of the characteristic of an object, such as color, sizing, font, shadow and etc.
As for the [element or group of elements], refer back to how to reference elements.

Here's an example for css:
```css
body {
    color: 'white';
    background-color: "#000000";
}

#welcome-header {
    margin-left:200px;
    font-size:30px;
}
```
So we can see there is a style rule for the body element, and we can see the background color is black. The background color will be the most noticable, and the color is simply the text color of all text inside the body, if it does not have a rule overriding this.
Color must be enclosed in double quotes or single quotes. There are a few ways to define color. One is by text. CSS has some pre-defined colors that are available for usage, such as 'black', 'blue', 'cyan', etc. You can look up the full list.

The most common way is to use hex colors. Hex colors must always start with #. A hex color uses hexadecimal, which is also called base 16. Hexadecimal colors go from 000000-ffffff, where instead of 1-9 it goes through 1-f. There are 3 pairs of hexadecimal digits, used to indicate red, green. and bue.

For example,
```RR GG BB
ff 00 00```
#ff0000 is the color red.

In some cases, there are 4 pairs of hexadecimal digits, the fourth pair being used to indicate tranquility.

Now, let's look at the #welcome-header element. it has a margin-left of '200px'. px is pixels. There are different measurement units you can use, each for different purposes.

There are two different types of units, absolute and relative.
Absolute units are fixed and will not move if your screen size is different, or window resized. Each are different lengths.
Relative units on the other hand, specify a length related to another element or property. Each of them do different things, I won't list them here but you can look them up.

Absolute units
- cm
- mm
- in
- px
- pt
- pc

Relative units
- em
- ex
- ch
- rem
- vw
- vh
- vmin
- vmax
- %

As for the font size, it is also measured in these units. The default font size is 16px, but if you change it, it will make the text bigger. For most elements, the style will be that of the parent element, unless overridden.

Now to implement the CSS we learned, we have the 3 ways mentioned earlier. 
To add styles via a <style> element is simple. We just put all of the CSS code inside the <style></style> tags, which are located inside the <head> element.
For files, we need to use a <link> element. This is actually a closed element. To link a stylesheet, we use
```html
<link rel="stylesheet" href="styles.css">
```
Keep in mind styles.css should be a filename, located in the same folder as where you put your .html file. It can also be a URL to a CSS file.

For the last way of implementing css, it is within a style="" parameter in an HTML element. This way of CSS is almost like the others, except it ommits referencing elements. Instead, you are always referring to the element you put the parameter in. Let me show you an example:

<p style="color:'magenta; border: 1px solid #000000;'">some text</p>

In this example, it skips the {} and the element selection. We don't need to! We're already using this element, the one we put the style parameter in.

Now, in border, you can set multiple properties. 1px, solid, and #000000 which is black. This will make a thin black border around the <p>. You don't have to worry about this now, even though it might seem complex. You can look it up later, as this book won't go into detail about it.

I encourage lots of experimenting with styles, to get the feel of how they are interpreted by the browser. If you want, see if you can make your own portfolio or something that looks nice. If you want to delve deeper into CSS and discover animations and things, go do your own research into making websites look amazing. Once you are finished with CSS, we are going to move onto the main topic of this book, JavaScript.

