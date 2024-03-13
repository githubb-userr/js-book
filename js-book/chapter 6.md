# Chapter 6: Data types and variables
Data types are types of data. (obviously)

They are very important and used in all languages. The reason why is because, how would a computer know what 1+1 is? Well obviously 1+1 is 2, but the computer could also think it's 11. 
What's a+b? Well it would make sense for it to be ab, and that's what JavaScript does. But when questioned with 1+1, 1 is just a character, same as all the letters in the alphabet. The computer isn't going to know what to do, so we ntringeed to specify it.

Here's some logic,
- "1"+"1" = "11"
- 1+1 = 2

As you can see here, text is stored in double quotes. We can also use single quotes to indicate text. This text is called a *string*.

You might be thinking, "What would happen if we didn't put it in quotes?". Well, most likely it would print an error to the console. In some cases though, the computer could think you are referencing a *variable*.

A variable is just a value stored and given a name. For example,

```js
var variablename = 1
```

A thing to note with JavaScript is that it is case sensitive. In other words, 'variableName' is different than 'variablename' because the N in name is different in each of them.

So, we have our variable called variablename. We can see that it equals 1.
Let's try to add 2 variables together. Let's try this

```js
var number1 = 3
var number2 = 4

console.log(number1 + number2)
```
If you were to run this code, you will see '7' printed in the console. You can also alert() this. In any case, number1+number2 always equals 7.

To change a variable, we wright `variablename = 9`.
Let's try changing a variable to itself plus itself.

```js
var varname = 20
varname = varname + varname
alert(varname)
```
woah, we got 40.

There is a way to simplify this.
```js
var varname = 20
varname += varname
alert(varname)
```
Nothing has changed, the code still runs the same. However, we have simplified it into +=.
Notice how we don't use = anymore, it's now +=.

variablename is equal to variablename plus 5, is the same as
variablename += 5.
All it did is add 5 to variablename, nothing more

There's another one, ++.
++ means increase by one. Let's try this

```js
var num = 7
num ++
console.log(num)
```

Here we see that the console printed 8, which means num is now 8 because ++ increased it by 1.
There are a few more symbols like that you can use, *=, **, --, and -=. There are some other ones, but not commonly used and more complex.

We'll go over one more data type in this chapter, which is boolean.
Boolean is a type of data that only has two possible values: true and false. We cannot assign a variable to true or false, so we are safe to use it without quotes. If we used quotes, the computer would just think it was some text.
Let's try this.

```js
var bool = true
```

We now have a boolean type of data for our variable. You can actually add these together!
But how would you add true + false, or true + true. They aren't strings, so false+true doesn't equal 'falsetrue' or anything. Instead, it results in a number.

Essentially, true = 1 and false = 0. So you just add true and false as if they are numbers. Here are some examples

- true + true = 2
- false + false = 0
- true + false = 1
- false + true = 1
- false - true = -1 