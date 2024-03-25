# Chapter 9: If statements and loops.
In chapter 8, we tried making a function to loop through a list of people. We kind of got stuck because we need the loop to stop somewhere. I encourage you, once you are done with this chapter to try and re-implement the people loop.

Now, to make a conditional is very easy.
```js
if(condition) {
    //then do this code
}
```
we can add on an else, which runs if ths condition is not true
```js
if(condition) {
    //will happen if condition is true
} else {
    //will happen if condition is false
}
```
we can also add on as many else if's as we like
```js
if(condition) {
    //run this if true
} else if(condition) {
    //run if the first condition is false, and the new condition is true
} else {
    //run if the first two conditions were false
}
```

Here's an example function with if statements that loops over and over until a number is provided, then tells you if you're elligible for the roller coaster ride.
```js
var age;
function promptForAge() {
    age = prompt("What's your age?")

    if(typeof age == 'number') { // != is "not equal to"
        return age
    } else {
        promptForAge()
    }
}

function isElligible() {
    age = promptForAge()

    if(age > 5) {
        alert("Congratulations! You can ride on the roller coaster")
    } else {
        alert("I'm sorry, but you aren't ellegible for this ride")
    }
}

isElligible()
```
If you run this in a `<script>` tag in your browser, you'll see that it asks for your age. If it doesn't understand your answer, it will prompt you again for your age, until you do give it a valid answer, which it will determine if you are elligible.

You may notice a few odd things 'here'. The first is the `return age` statement, the second is `==`.
Firstly, the `==` is conditional whereas `=` is for defining things. If you were to use `=` inside an ifthenelse, it would change the `age` variable to 'number' which we DON'T want.

Secondly, the `return` statement will block any further code that you try to write. You can return a variable, which makes it so the function you're returning actually has a value. For example

```js
function getAge() {
    return 27
}

console.log(getAge)
```

You can also put it through an if condition.

```js
function getAge() {
    return 27
}
if(getAge() == 27) {
    console.log('getAge() is equal to 27.')
}
```

How about we try this
```js
if("blah blah") {
    console.log('"blah blah" is equal to true?')
}
```
You'll notice that it actually runs through and apparently `"blah blah"` is true. What???
Well there's a concept called truthy/falsey. It's handy for knowing if something exists or not. It's most commonly used to check if something is undefined.

Falsey is either false, an empty string, null, undefined, or 0.
Truthy is everything else.

An if statement will always check for if something is either true or false, no matter the value or the condition.

Now let's move onto loops. A loop is an easier way of a function that repeats itself.
Firstly, a while loop. A while loop is something that always repeats if a condition is true.
```js
while(true) {
    //do this
}
```
will repeat forever. Other cases include
```js
while(i<10) {
    //do this
    i++
}
```
This is very common. Another loop that's very clean is
```js
for(let i=0; i<10; i++) {
    //wll repeat 10 times
}
```
woah woah, first off, `let` is another term for declaring a variable, only it won't exist if you try writing it outside of whatever you define it in.

The other stuff is just how you write a for loop. What it does is the equivalent of
```js
let i=0;
while(i<10) {
    //do stuff
    i++
}
```
only the for loop is cleaner.

In the first part of the for loop, we declare i as 0.
In the middle part, we define where the loop ends.
In the last part, we're declaring what happens right before the loop ends.

Typically you use some variable, and default back to i. If you have a for loop inside a for loop, to avoid using i, we default to j and so on. Usually you don't have so many loops inside each other that you use z, and if you do you have some serious code readability issues.