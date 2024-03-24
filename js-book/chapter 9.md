# Chapter 9: If statements and for loops.
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
    age = prompt("")
}

function isElligible() {
    
}
