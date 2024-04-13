# Chapter 14: Async/await and some more express
To make a post request inside a browser, we can either use a form element or we can use JavaScript. I personally am not a fan of the form element way, so I will teach you how to make a post request with JavaScript.

First of all, we need to figure our what to do with our post request, a login seems good, let's try that. So first of all we need to send a request from the client to the server, saying "Hey! Can you check these credentials?"

Now first of all, we're using HTTP, not HTTPS. The difference is that anyone who is connected to your network can see everything you put into your requests. We do *not* want people to be able to log in. I will not go into detail about this, but it something to think about. Another option is just getting an SSL certificate which means you can use HTTPS securely and nobody will be able to see the details, other than your ip address.

Another thing is that usually passwords should be hashed inside your database. If someone ever manages to get this password hash, they won't be able to use it since it's a one-way operation. Here's how a hashing algorithm works.

- User creates account, password they chose is hashed and stored in a database.
- When a user logs in, they enter their password. Password is sent to server and hashed. If the hash matches what's in the database, user is successfully logged in.
- If a hacker steals hashed password, he can enter it into the login form, send it to the server, and out will come out a completely different hash.
- Yay, hacker can't get in!

Now let's go about creating a login form. I won't be demonstrating anything to do with a database yet, I will be using a few made-up functions that are self explanitory.

Firstly, let's create some server code
```js
const express = require('express')
const app = express()
const path = require('path')
app.use(express.json)
app.listen(80, (req, res) => {
    console.log("Server is listening!")
})
app.get('/login', (req, res) => {
    res.sendFile(path.join(__dirname, 'client', 'login.html'))
})
```
Hmm, we need a login.html file inside a client folder.
```html
<!DOCTYPE html>
<html>
<!--insert login here-->
</html>
```
Good enough, let's get back to the server code, and apend this to our code.
```js
app.post('/validateuser', (req, res) => {
    //These are some made-up functions
    let userHash = getHashFromDatabase(req.body.username)
    let isCredentialsCorrect = checkHash(req.body.password, userhash)

    if(isCredentialsCorrect) {
        res.json({success: true, data: {/*insert data here*/}})
    } else {
        res.json({success: false})
    }
})
```
Okay cool, we have our server stuff, now let's try to make a post request with the client. We can either make a /client/client.js file or put it in the html.
If we want to make a client.js file we need to add a line of code to our server, so we're gonna go with the html.
(`app.use(express.static('client'))`)
Okay so in the client, let's try this
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Login</title>
        <script>
            const data = {username: document.querySelector("usernameinput").value, password: document.querySelector("#passwordinput").value}
            document.querySelector("#login-submit-button").addEventListener('click', async () => {
            let responseFromServer = await fetch("/validateuser", {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json",
                    },
                    body: JSON.stringify(data)
                })
            })
            responseFromServer = responseFromServer.json()
            if(responseFromServer.success) {
                alert("Success! You are authorized")
            } else {
                alert("Incorrect username or password")
            }
            
        </script>
    </head>
</html>
```
There's one thing that might seem unfamiliar, async/await calls. These serve a very useful purpose. Here's how they work.
First, async is specified at the start of a function. You are only able to ever use async when await is at the top of the function.
Next, whenever you add await to the start of any statement, it will wait for that statement to complete before moving on.

Think of file calls for example. Let's say you put a file in a variable. Right under the line of code you have for that, you're accessing the file and doing something with it, say console.logging it. This file will take a second to load, so if you try logging this file that you've put in a variable... before the second to load has happened, the variable will just be undefined because you failed to use await.

Now, this piece of code up here, I don't expect you to run it as there is no database set up, nothing like that. However I hope I demonstrated how to use the fetch API. Fetch is for sending all sorts of requests up to the server, or even to other websites.