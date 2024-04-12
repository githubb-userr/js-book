# Routing with express
There are 4 types of requests we can send. (client to server). They are used in categorizing the different types of requests we get.
- DELETE [Used for deleting something from somewhere]
- GET [Used to get data]
- POST [Creates or replaces data]
- PUT [Same as POST, not used as often]
PUT is essentially the same as POST only it's idempotent, meaning it will always do the same thing if the same request is put in, whereas a POST request may or may not do the exact same thing if the data you put in is the exact same each time.

We used a GET listener, `app.get` in our server code in the last chapter, to listen for /. / is our URL path, you can change this to /login and will be sent the message inside res.send() promptly upon entering http://localhost/login in your browser's address bar.

There are also response codes we need to handle. A common one is 404, you must have seen before to indicate when a page has not been found. Others include
- 200: OK
- 403: Unauthorized
- 500: Internal server error
- 400: Bad request

View the full list [here](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).

100 http codes are informational,
200 http codes indicate success
300 http codes indicate a redirection
400 http codes indicate a client error
500 http codes indicate a server error

You can send the 404 code using `response.status(404)`, same with any other code. Put this in your `app.get()` function, look in your browser's network tab and you should see it gave you a 404 code.

```js
var express = require("express")
var app = express()
app.listen('80', () => {
    console.log('server listening on port 80. Visit http://localhost:80')
})
app.get('/', (request, response) => {
    response.sendFile('/client/mainpage.html')
    response.status(200)
})
```
In this code we're using the response.status() function to set the status to 200. There's usually no need for this however, and the client should automatically have a status of 200.

Let's try making a 404 page
```js
var express = require("express")
var app = express()
app.listen('80', () => {
    console.log('server listening on port 80. Visit http://localhost:80')
})
app.get('/', (request, response) => {
    response.sendFile('/client/mainpage.html')
})
app.get('*', (request, response) => {
    response.send('404, page not found').status(404)
})
```
Here, if the route is not found it sends a 404 code and a message. * indicates all routes.
The way routes work is, it cycles through from top to bottom, all routes. It finds the first matching one, and executes it. Alongside the request and response variables, there is a next variable which is a function. If this function is executed, it will move on and search for the next handler that matches the client's request. We can use the next function to set up logs.

```js
var app = express()
app.listen('80', () => {
    console.log('server listening on port 80. Visit http://localhost:80')
})
app.get('*', (req, res, next) => {
    console.log(`New GET request at ${req.path}`)
    next()
})
app.get('/', (request, response) => {
    response.sendFile(__dirname +'/client/mainpage.html')
    response.status(200)
})
```
This will log every request. The only problem is it does not log post, delete, or put requests. To do this, we can do the same thing but use the `app.post`, `app.delete`, and `app.put` functions.
req.path as you can see by running this code should return the path of whatever URL a person goes to. Remember how req is the object that holds all of the data from the request the client sent. Note you have to have a file called mainpage.html, inside of a client folder.

For post requests, `req.body` should contain all the data this request sent. We'll learn how to make post requests in the next chapter.