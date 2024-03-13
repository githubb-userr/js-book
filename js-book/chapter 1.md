# Chapter 1: How does a website work?
Welcome to the world of web development. We will be learning HTML, CSS, JavaScript, and some other very important things. This book only requires a computer, and the basic functioning of a computer. No prior knowledge needed.

This book is intended to give you enough knowledge to know what to do to move forward. It isn't intended to be a complete tutorial of how to build a website, rather it's so you know *how* to build your website, how it works, the mechanics for it. This doesn't cover everything ever invented in HTML, JavaScript, Node.js, or CSS. Rather, it tells you how to build your website, how a website works, how the languages work, without having to memorize everything. Google exists. If you forget, google it again, and you will instantly be gratified.

Let's get started!

When you visit a website, you are using a browser. Your browser will send requests back and forth, until it recieves the HTML, and some other files like scripts, styles, images, and sounds for the page you are visiting.

The browser is called a *client*. So, anyone who is visiting that website currently is connected to it.
Connected to what you ask? Well, they are connected to a *server*. A server is a really powerful computer. Imagine a desktop computer, but with no screen, and very powerful. This server will basically talk to everyone connected to it.

Now, if you want to go even *deeper* to what is happening when you connect to it, here we are entering into the field of networking, which is for a whole other book, but essentially everything connects with a bunch of radio waves. Your Wi-Fi, all of your internet traffic, and everything.

So, to visualize the idea of clients and servers better, let's take the example of a blog.
This is a simple blog, it takes in a blog someone writes, and will make it so it's public and everyone can see it by visiting that page. So let's assume we want to make a test blog that just has a title of "test", and a body of "hello world". So, let's assume we have hit the create blog button, and let's analyze what happens in the background.

So, first the client sends the body and the title of the blog to the server, and the server makes an ID for it in a database and stores it.
Now, the server makes it so that whenever you enter that ID into the url. For example, https://exampleblog.com/blog/19204. It will look inside the database, grab what we wrote, and it will show it to anyone that goes to the url.

Now, there are 3 main components of a webpage:
HTML
CSS
JavaScript

HTML is for the basic layout of a webpage, It structures it.
CSS is for the styles of a webpage. It controls wether this button is blue, or to change the margin of this paragraph by 10, and so forth.
JavaScript is the triggers for that website. For example, when this button is clicked, turn this paragraph green, or when the s key is pressed, do this or that.

We will be learning how to use all of these during this book.