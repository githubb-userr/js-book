# Chapter 7: Arrays and objects
Let's check out some other ways of storing variables. A good way is a list. To make a list (array) we use [].
Inside the [] we can put values, separated by commas. For example,

```js
let someVariable = 59
var array = [2, "some text", ["another array", someVariable]]
```

Well, we have our list now. But, at some point we're going to have to be able to access a value from it. That's pretty easy
```js
var exampleArray = [2, 3, 4, 5]
console.log(array[1])
```
If you run this code, you will see that it prints 3 to the console. Why 3 and not 2? This is because it starts at 0, and 1 refers to the second item on the list.
If we run
```js
var exampleArray = [5, 2, 7, 3]
console.log(array[1], array[2], array[7], array[3])
```
you'll see `5 2 7 3` logged to the console.

Now, having a list can be convenient for some things, but in other cases we'll need to use a thing called an object. An object is essentially an array, only with names for all of the values. We use {} to enclose our object.
```js
var object = {age: 9, name: "Bob", lastName: "Green"}
```
And to access our objects, there are two methods. The first, by using a string.
```js
object["value"]
```
The second, by using dot notation.
```js
object.value
```
If value isn't inside the object, it will return undefined. You can store anything inside an object, including other objects and functions.