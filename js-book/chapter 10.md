# Chapter 10: Classes
JavaScript is an object oriented programming language (OOP). This means we use classes and objects a ton in our code. A class is kind of like an object, but you can define it whenever you like. Kind of like a function that creates an object whenever you call it.

To create a class, we use
```js
class ClassName = {

}
```

We now have a variable called ClassName, which we can use to make a new object in the style of that class whenever we want using
```js
var obj = new ClassName()
```
This is just an empty class though, to add things to it, we need to add functions. We don't use the function keyword however in classes. Here's how functions are made

```js
class Car {
    vroom() {
        alert("vroom")
    }
}
```
Now that we have a car class, we can use

```js
let mercedes = new Car()
mercedes.vroom()
```
You can see we're calling a function using the `()`, and the function is part of the mercedes object.
Now let's say we want to call our own function. This is interesting, because we can't necessarily write `mercedes.vroom()` *inside* our class, rather we use `this.vroom()`. Here's an example

```js
class Car {
    vroom() {
        alert("vroom")
    }

    vroomTwice() {
        this.vroom()
        this.vroom()
    }
}
```
Normally you'd automate and put a count parameter inside your vroom() function, indicating how many times you'd like to alert("vroom"). However for this example, I won't put it in there.

Anyhow, you can see how we call the this.vroom() function from inside the class.

Now, classes are built up of functions. You can't do something weird like
```js
class Car {
    this.model = "some car model"
}
```
Instead, you can define variables and things inside functions. You don't *have* to define a function that's part of the class, however sometimes it's useful to do so.

```js
class Car {
    function init() {
        this.model = "some car model"
        this.miles = "car mileage"
        this.hp = "car horsepower"
        this.mpg = "miles/gallon"

        let index = 0 //example of variable not using `this.`
        while(index < 4) {
            console.log(index)
            index ++
        }

    }
}
```

Let's say we want to create a few variables upon the class being created. This is kind of like function parameters. Consider this code
```js
class Car {
    constructor(make, model, hp, mpg) {
        this.make = make
        this.model = model
        this.hp = hp
        this.mpg = mpg
    }

    getStats() {
        console.log(this.make, this.model, this.hp, this.mpg)
    }
}

let car = new Car("some make", 'some model', 'some hp', 'some mpg')
car.getStats()
```

Look at that, we now have a car that runs some code (the stuff in the constructor function) upon creation.

There's also parent/base classes and child classes. These classes are modeled after one another, but the child class has some minor changes.
```js
class Car {
    constructor(type) {
        this.type = type
        this.locked = false
    }
    beep() {
        alert('Beep beep!')
    }
    lock() {
        this.locked = true
        alert('car locked')
    }
}

class UnlockableCar extends Car {
    unlock() {
        this.locked = false
        alert('unlocked car')
    }
}

let unlockableCar = new UnlockableCar("some kind of type variable")
unlockableCar.beep() //beep still works, even though we didn't define it in the UnlockableCar class
unlockableCar.unlock() //this function doesn't exist in the Car class
```
We can also redefine a function, for example if we wanted to make a GlitchyCar class that actually unlocks the car when you try to lock it, we can just
```js
class GlitchyCar extends Car {
    lock() {
        this.locked = false
        alert('hahaha, car is now unlocked')
    }
}
```
from now on, `this.lock()` or `glitchyCar.lock()` will switch the locked variable to false, and alert "hahaha, car is now unlocked". If we want to access the *original* function, we can use super.lock() which will actually lock the car.

Overall, classes are extremely important and you'll find a lot of them wherever you go in your JavaScript explorations.
