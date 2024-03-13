# Chapter 5: Introduction to JavaScript.
Yay, we're on to some pretty interesting stuff (at least in my opinion) here.

Now the first thing to note, is that JavaScript is NOT Java. JavaScript is for web development, and Java is entirely different. There's a lot of people who think Java is JavaScript, so I feel I have to mention it.

Moving on, let's talk about what JavaScript really is.
Throughout this book, I have been mentioning that JavaScript adds the functionality of the website. When this button is clicked, do this and so on.

A common way of using JavaScript is to set a trigger to an element.

You can add triggers to any clickable element, there are many, many triggers you can use, some are available only for specific types of elements. For example, oninput. Can you input a value to a paragraph? Well no, but you *can* change the value of a text input.

Well, then comes the question of what do we do when it is triggered. Well, JavaScript can do a lot of things. It can access all elements and give them properties, and access the CSS of an element. It can also control the browser, send requests, display prompts, draw things on a canvas, basically a ton of things.

Now, JavaScript is an actual language, not styles or web layouts. We can use it to do some pretty cool stuff.

You can implement JavaScript inside HTML like so:
```html
<script>
    Insert JavaScript here.
</script>
```

There's also one other way of implementing it, which is to link a file. For this, we can use
```html
<script src="javascript.js"></script>
```
The file should always have .js on the end of it, it should also be in the same folder where you put your .html file.
You can also include a URL to a JavaScript file on the web. You can find useful additions to your JavaScript on the web, just from doing this.

The last way to add JavaScript is to put it directly inside the element. This is a very uncommon way of using JavaScript, and we won't go into detail, but it exists.

Now, let's try to write a basic script.

Here we have an extremely simple sample webpage.
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Example website</title>
    </head>
    <body>
        <!--nothing in here-->
    </body>
</html>
```

You may be noticing the <!-- text -->, this is a comment which is completely ignored, and is solely for other people to read.

Let's add a simple script to it.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Example website</title>
        <script>
            alert("Hello World!")
        </script>
    </head>
    <body>
        <!--nothing in here-->
    </body>
</html>
```

Put that into a filename.html file, and open it in your browser. You'll notice that right as soon as you open your webpage, your browser shows you a prompt saying "Hello World".
You can add this script to whatever webpage you have already made, don't feel restricted to only using the code in here.

It is extremely handy to have developer tools in your browser open when you are making a website. To open dev tools, you can usually press ctrl+shift+i. If that doesn't work, try pressing f12. If that *still* doesn't work, first make sure you aren't using a school or work computer, and see if there's documentation on how to open it.

There's a thing in the dev tools called a console. In JavaScript, we can console.log something to the console and it will print it there.

Let's try this.
Put 
```js
console.log("hello world")
```
If you have your browser's dev tools open, you should see the message printed. This is very handy for debugging and fixing problems.