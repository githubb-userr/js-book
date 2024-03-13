# Chapter 2: The basics of HTML
Now that we know how a website works, let's design one ourselves!

So, we are going to be using HTML to create the webpage. HTML as I said before, is the basic layout of a webpage. It's kind of like a skeleton. HTML by itself doesn't look very good, although it's very very essential to a website, and it provides a nice layout.

So, to make the most basic of basic websites (a blank page), we write in a .html file:
```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
    </body>
</html>
```

So all our website has right now is the title of the webpage, called My Website. That's pretty boring, so let's add a header to our code:
```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>Welcome to my website!</h1>
    </body>
</html>
```

Why `<h1>` instead of something like `<h>`? Well, there's actually 6 headers. `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, and `<h6>`.
`<h1>` is the biggest header, and `<h6>` is the smallest.

Now, you may be wondering how to run this. Well, first let's save our file. Once we've saved our file, we're going to run it in a browser. You will have to open your browser.

First, open up a file manager and find the filename.html file you created. If it opens in a text editor when you click it, close the text editor and right-click the file and click 'open with', or 'open with other application'. Then select your favorite browser and it will open!

So, we made our first website. But it looks pretty empty, except for a bit of text. So, let's try adding a button.

Add `<button>`Click me!`</button>` right under the `<h1>` element, save the file, reload your webpage and look! There's now a button. Try clicking it, nothing happens. We need to use JavaScript to make the button functional!

Now, let's go over what exactly the main components of HTML are. First, we have `<!DOCTYPE html>`. This is a header, and it basically tells your browser, "Hey! This file should be displayed as HTML".
Next there is the `<html>` element. This stores all of the html to be used in our page, including the body and head elements.
The `<head>` element contains metadata. What is metadata you ask? Well, metadata is information about the webpage. Such as the document title, styles, scripts, and some other information. None of this is displayed. It's a sort of data about data, kind of like a header.

Now, the `<body>` element contains everything that exists on the HTML page. Buttons, containers, inputs, paragraphs, you name it! Everything inside the `<body>` element should be able to be displayed.

We will talk about more advanced html in chapter 3. 
