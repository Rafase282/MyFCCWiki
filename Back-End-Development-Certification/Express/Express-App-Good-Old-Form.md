### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Express App: Good Old Form

Write a route ('/form') that processes HTML form input (`<form><input name="str"/></form>`) and prints backwards the str value.

## HINTS

To handle POST request use the post() method which is used the same way as get():

```javascript
app.post('/path', function(req, res){...})
```

Express.js uses middleware to provide extra functionality to your web server.

Simply put, a middleware is a function invoked by Express.js before your own request handler.

Middlewares provide a large variety of functionalities such as logging, serving static files and error handling.

A middleware is added by calling use() on the application and passing the middleware as a parameter.

To parse x-www-form-urlencoded request bodies Express.js can use urlencoded() middleware from the body-parser module.

```javascript
var bodyparser = require('body-parser')
app.use(bodyparser.urlencoded({extended: false}))
```

Read more about Connect middleware here:

<https://github.com/senchalabs/connect#middleware>

The documentation of the body-parser module can be found here:

<https://github.com/expressjs/body-parser>

Here is how we can flip the characters:

```javascript
req.body.str.split('').reverse().join('')
```

## NOTE

When creating your projects from scratch, install the body-parser dependency with npm by running:

```
$ npm install body-parser
```

...in your terminal.

## My Solution

```javascript
var express = require('express')
var bodyParser = require('body-parser')

var app = express()

// create application/x-www-form-urlencoded parser
//var urlencodedParser = bodyParser.urlencoded({ extended: false })
app.use(bodyParser.urlencoded({
  extended: false
}))

// POST /form gets urlencoded bodies
app.post('/form', function(req, res) {
  //if (!req.body) return res.sendStatus(400)
  res.send(req.body.str.split('').reverse().join(''))
})

app.listen(process.argv[2]);
```

## Official Solution:

```javascript
var express = require('express')
    var bodyParser = require('body-parser')
    var app = express()

    app.use(bodyParser.urlencoded({extended: false}))

    app.post('/form', function(req, res) {
      res.send(req.body.str.split('').reverse().join(''))
    })

    app.listen(process.argv[2])
```
