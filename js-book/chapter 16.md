# Chapter 16: Debugging
It's extremely important to know how to debug. After all, coding is the process of putting bugs into your code, debugging is the process of removing them. This makes debugging critical.

One of the best ways to debug is setting breakpoints. Every widely used programming language, including JavaScript, should have an IDE or code editor that supports breakpoints. Breakpoints are most easily created in the browser. If you use a modern browser that includes developer tools, it should have the functionality of setting breakpoints.

The definition of a breakpoint is a line of code that, when executed will stop the program in it's tracks so you can examine what exactly is happening. 
For example, try going to a random website with chrome, ensuring that you are able to use the built-in developer tools. Go to the sources tab and find a JavaScript file. It's likely that the file will be obfuscated, so you can't really see what is happening. 
I'd encourage you to set up a server which feeds the client an HTML file, which then requests a static JavaScript file from the server. Once you've requested this file, it's a piece of cake opening up sources and selecting this file. Once the file is selected, you should be able to click to the left of the line number, and this should set a breakpoint. Now when this line of code is run, your browser will alert you.

There's also ways to set breakpoints with server code. Vscode has a built-in feature that allows you to do this, there are also some npm packages that allow you to go into chrome://inspect, and select the port that your debugger is running on. From there, it will open up a devtools window, much like the client devtools, only it's a window and not a portion of your tab.

When your program is stuck on a breakpoint, the most important feature of your editor should be the console. In the console, you can view variables and execute code. It executes the code you write wherever your breakpoint is set. For example, if you've set a breakpoint inside of a class, you can use the `this` variable, to access your class's methods and variables. If you've set your breakpoint inside a function, you can access the function's parameters.

Another very important feature of the debugger is the call stack. You may have seen this call stack when your node.js program throws an error inside your terminal. It will say something like,
```Error: [blah blah] at [filename.js] line [57, 197]
[faulty code statement] ^^^

Call stack:
[filename.js] line [line, char]
[filename2.js] line [line, char, etc]

```
Some of these files you may have not known existed, such as the files in `node_modules`, or even inside node.js itself. But in essence, it shows you exactly what your code touches. The call stack in the debugger is extremely similar to this. It shows what everything is calling. For example you could have a file somewhere, let's call it file1, that runs another function in a different file (file2). If you set a breakpoint inside the file2 function, it will add file1 to the call stack, as the function call originated there. This is extremely useful when you're trying to find what called the specific function you've set the breakpoint in.

There should also be steps you can take. For example, stepping over to the next function, or stepping *into* a function, where you can debug that speficic function. Every debugger has this feature.

Try debugging your projects. You can start with the client, debugging the javascript that runs. Your breakpoints should be saved when you reload, ensuring that you can catch the lines of code that run right when the client is loaded.