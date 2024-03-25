# Chapter 8: Functions
There is one highly useful thing you can do in your code called a function. A function is something you can run, to call some code you've written in your function. You can call this function whenever you want, rather than typing a ton of code every time you want to do something. You can also specify parameters, which are very useful if there's some value that you should be able to specify each time you run it

Functions are usually defined with the `function` keyword, or with `()`.
To define using the `function` keyword, use this syntax.
```js
function functionName() {
    //put code here
}
```
And to define a function using (), use this.
```js
var functionName = () => {
    //put code here
}
```
Overall, these do essentially the exact same thing. The fat arrow just means it's a function.
To execute your function, just type your function name, followed by (). Here's an example

```js
function welcome() {
    alert("hi")
    let name = prompt("enter your name")
    alert("welcome, "+name)
}

welcome()
```
Suppose you were to take out `welcome()`. Nothing would happen, as you haven't executed the welcome() function.

Now, you can also add parameters to your function. Remember `alert()`? Well, `alert()` has one parameter, which is what you're supposed to alert.
In `alert("Hello world")`, "Hello world" is the parameter. You can have more than one parameter in your function, but it has to be separated by a comma. Consider the following code.
```js
function sendText(name, text) {
    alert(`To ${name}: ${text}`)
}

sendText("Alex", "Hi there Alex!")
```
This function has 2 parameters. If you run it in a browser, it will immediately alert, `To Alex: Hi there Alex!`
Let's try experimenting with some parameters.

Believe it or not, we can actually put a function in a parameter. It's called a callback. Watch this!
```js
function exampleCallbackFunction(callback) { //our parameter is called callback.
    //do some stuff
    let age = 3
    callback(age) //this executes the function, we can even put a parameter in it
}
exampleCallbackFunction((ageParameter) => {//execute the function defined, note the value we put in the parameter
    console.log(ageParameter)
})
```
This may be hard to understand, here's a summary.
- We create a function called exampleCallbackFunction(), and we define a parameter called callback. We could name this anything we wanted to, not just callback.
- Then, we make a variable called age. Since we're using `let`, this variable will not exist outside of the function.
- Now, we are executing our parameter, indicating that the parameter is a function, and we end the function.
- We call our `exampleCallbackFunction` function now, specifying a parameter called ageParameter.
- Once the `callback(age)` is executed, it will execute the function, putting `age` in the parameter, and we will log the age it puts inside.

Let's make a function that you need to put an object in. We will have `person` be the specified object
```js
function listPerson(person) {
    console.log(person.name)
    console.log(person.age)
    console.log(person.profession)
}
```
Okay so we have our function. What if we want to list... a list of people. Let's try making an array of people, with a bunch of objects in them.
```js
var people = [
    {name: 'Alice', age: 25, profession: 'Teacher'},
    {name: 'Bob', age: 30, profession: 'Engineer'},
    {name: 'Charlie', age: 35, profession: 'Doctor'},
    {name: 'David', age: 40, profession: 'Lawyer'},
    {name: 'Eve', age: 22, profession: 'Artist'}
]
```
Hmm, we need a way to list all of these. An obvious way would be to use
```js
listPerson(people[0])
listPerson(people[1])
listPerson(people[2])
listPerson(people[3])
```
But if the list of people changes size, and more elements are added on, or shrinks, it will be inaccurate.
One thing to notice is that these lines of code are mostly the same, except for the numbers 0, 1, 2, and 3. When you are coding, you want to avoid patterns. If it's a pattern, try your best to eliminate lines of code, to make it efficient. Do not repeat the same line of code, if it is loopable. Let's make a modification to our function.

```js
var index = 0
function listPeople(peohepleArray) {
    console.log(peopleArray[index].name)
    console.log(peopleArray[index].age)
    console.log(peopleArray[index].profession)

    index ++
    peopleArray(index)
}
```

Woah! Genius huh? We now have one last problem. Our loop will repeat infinitely! The answer to this would be to check whether we've reached the end of peopleArray. We can use peopleArray.length to see how many people are in our list, and we can compare it to the current index. If the index has hit the number of people in peopleArray (minus 1, because the length will be 1 greater than the last person's index, as it counts from 0) then we can stop the loop.

Now we need to know how to check if the index is greater than peopleArray.length. We'll discuss this in the next chapter.