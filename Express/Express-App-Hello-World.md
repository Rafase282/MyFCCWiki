### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Express App: Hello World!

Create an Express.js app that outputs "Hello World!" when somebody goes to `/home`.

The port number will be provided to you by expressworks as the first argument of the application, ie. `process.argv[2]`.

## HINTS

This is how we can create an Express.js app on port 3000, that responds with a string on '/':

```javascript
var express = require('express')
var app = express()
app.get('/', function(req, res) {
  res.end('Hello World!')
})
app.listen(3000)
```

Please use process.argv[2] instead of a fixed port number:

```javascript
app.listen(process.argv[2])
```

## My Solution

```javascript
var express = require('express')
var app = express()
app.get('/home', function(req, res) {
  res.end('Hello World!')
})
app.listen(process.argv[2])
```

It is similar to node which in turn is similar to JavaScript so everything is easier to pickup.
