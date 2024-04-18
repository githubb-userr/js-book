# Chapter 15: Files and styles
Now, there's always a style of coding to every programmer, when you're beginning, you don't really have one. File structure can be part of this. I'll go over some things that may be useful, also some file structures and how to use javascript from other files.

There is another use for `require()` actually, we can require files, using their relative file path.
To avoid `require()` thinking it's a package, use `./` or `../` in front of your file path.

Let's say we have a folder called `project`. Inside this folder is a file called `index.js`, and 2 folders named `server` and `client`. Let's also say we have a file inside `server` called `database.js`.

```
Project [
    index.js    
    Server [database.js]
    Client []
]
```
In this file system we can write `require('./server/database.js')` inside of index.js and it will request code from database.js.
Now you might be thinking require() just inserts the entire file of database.js into the file you require it from, but in reality this does not happen. If it were to be like this, there would be some confusion as to what exactly require() returns. The most prominent fix for this is to define a variable inside database.js which defines what exactly we are requiring. This is how it works in JavaScript. We define `module.exports` which in turn defines what you obtain from requiring your file.

Let's go into database.js. There is a class, called Database. I want to use this class in another file, and so inside database.js I put `module.exports = Database`.
Now, inside index.js we can use `const Database = require('./server/database.js')`.

We have the database object from inside of our index.js file! The way this works is, the first time you require this file it will run. Then, the results in module.exports are cached and whenever you require() from hereon, it will give the module.exports without running the file.
You can put any data type you want into module.exports. It can be a function `module.exports = () => {}`, it can be a string `module.exports = 'hello world'`, it can be an object `module.exports = {}`, or a class, whatever you like.

A common file structure is to make most files into classes, for example if you have a game, you'd make a class for every item and use functions for them. You'll also need some type of main configuration file where you can edit common properties of each item, such as cooldown time and etc.
You can do this with a JSON file. The structure of JSON is quite easy to learn, I encourage you to. To require a JSON file, use require('./config.json') and the output will be your JSON object.

Some good code tips are,
- always use `let`. Using `var` could bring unwanted consequences when your variable is changing and you don't know what statement changed it
- Use ?. if you don't want a property or function of an object to give an error if it's undefined. For example, `object?.property` or `object?.function()`
- Another way of using the if/else statement is `[condition] ? [do if true] : [do if false]`. For example, `req.body.username ? username : username = "Guest"`. This will check if `req.body.username` is defined, if it's defined then leave it, otherwise set username to "Guest".
- Usually you don't have to check if something is false using `if(variable == false)`, instead you can use `if(!variable)`. Keep in mind this will also trigger if it's undefined, 0, an empty string, or null.
- Don't use `const` if you're going to be changing the value of your variable
- Another thing is switch case. Use it if there's more than 2 if statements for the same variable, it will be more readable and nicer looking.

Here is the switch case
```js
switch(item) {
    case 0:
        //do something
        break;
    case 1: 
        //do something
        break;
    case 2:
        //do something
        break;
    default:
        //if item is neither 0, 1, or 2
        break;
}
```
This essentially does the same thing as 
```js
if(item == 0) {
    //do something
} else if(item == 1) {
    //do something
} else if(item == 2) {
    //do something
} else {
    //if item is neither 0, 1, or 2
}
```
Only the switch will look nicer.