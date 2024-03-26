# Chapter 12: Starting backend development
Now that we have learned the basics of *frontend* web development, it's time to move onto the backend. If you haven't made your own little html page with some stuff, go back and make your own website - possibly more than one, before continuing in this chapter.

First of all, we're going to need to actually install a programming language. On linux, you can install a thing called nvm that will make it so you can install whatever version of node you'll need for your project.
If you are on windows, nagvigate to the node.js website and download it. It's completely free.

First of all, node works by running directly on your computer. When you set up a web server, other computers who navigate to your ip address will be sent some type of file, html document, or... nothing upon accessing your ip. This will be displayed according to your browser. Refer to chapter 1.

Now, there's one other component you need to know called *npm*. Npm is a package manager. A package manager is basically a big storage for code other people have created. Say you want to access some cool component in your code, but don't want to recreate the wheel for it. You can use npm (node package manager) to download some code other people have written, and then use it in your own code. Some of these packages include handy utilities, apis, you name it.

Make sure you've installed node. Npm will be installed right along when you install node, so you don't need to install npm separately.
First, we're going to open up cmd/terminal, you can navigate to a folder using `cd [file path]`. Once you're wherever you want to develop your web server, we're going to type `npm install express`. This package is for web development, and is extremely useful.

I recommend visual studio code editor for this part, it has a built in terminal and is very useful for development.

Now, once express has been installed we need to make a file. The file extension should be .js, typically index.js. Inside index.js, we can put code. First, some things to note: console.log will still work, variable making, functions and etc will still work, however alert(), prompt() and all functions related to the browser to not exist because we are running this on your computer.
Also, we do not have a window object, instead we have global. The window/global objects are the objects that contain every single function. For example instead of console.log, you can type window.console.log, and it will work in your browser. In node, you use global.console.log.

Now, we're going to make a simple web server that runs on port 80. Think of port 80 as a little slot in your computer that can hold one process. If you try running multiple processes, they probably aren't going to work. The same thing happens if you try running *two* web servers on the same port, it just doesn't work and will create an error.

First of all, usually at the beginning of every JavaScript file you're going to use the `require` function, or the import keyword. This imports a package so it's available for use in your code.

Here's a simple web server running on port 80.
```js
var express = require("express")
var app = express()
app.listen('80', () => {
    console.log('server listening on port 80. Visit http://localhost:80')
})
app.get('/', (request, response) => {
    response.send('Hello World!')
})
```
In this code you'll see we have our express variable, and as you can probably see, it's a function. This function returns a value which we've defined as the `app` variable. With the `app` variable, we have a function called `listen()`. This starts the web server, listening on port 80. Once the web server is started, we `console.log()` that the server is listening on port 80.
Now, we can use app.get('/') to listen for requests to `http://localhost` or `http://localhost:80`. Inside the callback, we can use the request and response variables to do different things. The request object is what holds all of the data about the request - ip address, browser information, etc. With the response variable, we can send responses back to the client that connected to `http://localhost`. We can use the `response.send()` method to send back some text to be displayed by the browser: 'Hello World'.
### Running the file
Once you've made a .js file with this code inside, we'll need to run it. To run node.js, open up cmd/terminal, and type `cd [path to folder]`. Put in the path to where the folder with your file inside is. If you are on linux, you can type `ls` to see the avaiable folders that you can go into, and you can also type `cd [folder name]` without having a full path. On windows, the equivalent is `dir` to see available folders.

Please note that, you have to install express in the same folder as where you make your .js file. If you want to be able to access it from all places, you can type `npm install -g [package name]` in which the package name would be express.

Now, to run our .js file we're going to type in cmd/terminal `node [filename.js]`. Typically index.js, as index.js is a sort of standard for the root of a project, however you can name it anything.

If this works, you'll now have a server running! In the case that it says something like `Access denied for port 80`, you can either try running the .js file as admin (sudo in linux) *or*, you can try changing the port that it's running on, to something like 3000. Then you should be able to access it at http://localhost:3000.