# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Build Web Apps with Express.js
# Hello World!
Create an Express.js app that outputs "Hello World!" when somebody goes to /home.

The port number will be provided to you by expressworks as the first argument of the application, ie. process.argv[2].

## HINTS
This is how we can create an Express.js app on port 3000, that responds with a string on '/':

```js
var express = require('express')
var app = express()
app.get('/', function(req, res) {
  res.end('Hello World!')
})
app.listen(3000)
```

Please use process.argv[2] instead of a fixed port number:

```js
app.listen(process.argv[2])
```

## My Solution

```js
var express = require('express')
var app = express()
app.get('/home', function(req, res) {
  res.end('Hello World!')
})
app.listen(process.argv[2])
```

It is similar to node which in turn is similar to JavaScript so everything is easier to pickup.

# Static
Apply static middleware to serve index.html file without any routes.

Your solution must listen on the port number supplied by process.argv[2].

The index.html file is provided and usable via the path supplied by process.argv[3]. However, you can use your own file with this content:

```html
    <html>
      <head>
        <title>expressworks</title>
        <link rel="stylesheet" type="text/css" href="/main.css"/>
      </head>
      <body>
        <p>I am red!</p>
      </body>
    </html>
```

## HINTS
This is how you can call static middleware:

```js
app.use(express.static(path.join(__dirname, 'public')));
```

For this exercise expressworks will pass you the path:

```js
app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));
```

## My Solution

```js
var express = require('express')
var path = require("path")
var app = express()
app.use(express.static(process.argv[3]));
app.listen(process.argv[2])
```

Official Solution:

```js
var path = require('path')
    var express = require('express')
    var app = express()

    app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));

    app.listen(process.argv[2])
```

# Jade
Create an Express.js app with a home page rendered by Jade template engine.

The homepage should respond to /home.

The view should show the current date using toDateString.

## HINTS
The Jade template file index.jade is already provided:

```
h1 Hello World
p Today is #{date}.
```

This is how to specify path in a typical Express.js app when the folder is 'templates':

```js
app.set('views', path.join(__dirname, 'templates'))
```

However, to use our index.jade, the path to index.jade will be provided as process.argv[3].  You are welcome to use your own jade file!

To tell Express.js app what template engine to use, apply this line to the Express.js configuration:

```js
app.set('view engine', 'jade')
```

Instead of Hello World's res.end(), the res.render() function accepts a template name and presenter data:

```js
res.render('index', {date: new Date().toDateString()})
```

We use `toDateString()` to simply return the date in a human-readable format without the time.

## My Solution
You will need to install jade first: `npm install jade`

```js
var express = require('express')
    var app = express()
    app.set('view engine', 'jade')
    app.set('views', process.argv[3])
    app.get('/home', function(req, res) {
      res.render('index', {date: new Date().toDateString()})
    })
    app.listen(process.argv[2])
```

# Good Old Form
Write a route ('/form') that processes HTML form input (`<form><input name="str"/></form>`) and prints backwards the str value.

## HINTS
To handle POST request use the post() method which is used the same way as get():

```js
app.post('/path', function(req, res){...})
```

Express.js uses middleware to provide extra functionality to your web server.

Simply put, a middleware is a function invoked by Express.js before your own request handler.

Middlewares provide a large variety of functionalities such as logging, serving static files and error handling.

A middleware is added by calling use() on the application and passing the middleware as a parameter.

To parse x-www-form-urlencoded request bodies Express.js can use urlencoded() middleware from the body-parser module.

```js
var bodyparser = require('body-parser')
app.use(bodyparser.urlencoded({extended: false}))
```

Read more about Connect middleware here:

  [https://github.com/senchalabs/connect#middleware](https://github.com/senchalabs/connect#middleware)

The documentation of the body-parser module can be found here:

  [https://github.com/expressjs/body-parser](https://github.com/expressjs/body-parser)

Here is how we can flip the characters:

```js
req.body.str.split('').reverse().join('')
```

## NOTE
When creating your projects from scratch, install the body-parser dependency with npm by running:

```
$ npm install body-parser
```

...in your terminal.

## My Solution

```js
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

Official Solution:

```js
var express = require('express')
    var bodyParser = require('body-parser')
    var app = express()

    app.use(bodyParser.urlencoded({extended: false}))

    app.post('/form', function(req, res) {
      res.send(req.body.str.split('').reverse().join(''))
    })

    app.listen(process.argv[2])
```

# Stylish CSS
HTML without styles is boring so this exercise will teach you how to use Stylus with Express on the fly.

Style the HTML from the "STATIC" exercise using Stylus middleware. Stylus [https://github.com/stylus/stylus](https://github.com/stylus/stylus) generates .css files on-the-fly from .styl files.

Your solution should listen on the port supplied by `process.argv[2]` for GET requests, one of which will be for main.css, which should be automatically generated by your Stylus middleware. index.html and main.styl can be found in `process.argv[3]` (they are in the same directory).

You could also create your own folder and use these, if you like:

The main.styl file:

```sass
p
  color red
```

The index.html file:

```html
<html>
  <head>
    <title>expressworks</title>
    <link rel="stylesheet" type="text/css" href="/main.css"/>
  </head>
  <body>
    <p>I am red!</p>
  </body>
</html>
```

## HINTS
You'll want to plug in some stylus middleware using app.use again. It'll look something like this:

```js
app.use(require('stylus').middleware('/path/to/*.styl' ))
```

In addition to producing in the "STATIC" exercise, you'll need to serve static files. Remember that middleware is executed in the order app.use is called!

## NOTE
For your own projects, Stylus needs to be installed like any other dependency:

```
$ npm install stylus
```

## My Solution

```js
var express = require('express');
var app = express();

app.use(require('stylus').middleware(process.argv[3]));
app.use(express.static(process.argv[3]));
// This will display the main.styl content, not needed.
app.get(process.argv[3], function(req, res) {
  res.render('main');
});

app.listen(process.argv[2]);
```

Official Solution:

```js
var express = require('express')
var app = express()

app.use(require('stylus').middleware(process.argv[3]));
app.use(express.static(process.argv[3]));

app.listen(process.argv[2])
```

# Param Pam Pam
This exercise is about using URL parameters. For example, if you have /message/526aa677a8ceb64569c9d4fb, then you should know how to extract that value which is an ID of the message.

Create an Express.js server that processes PUT /message/:id requests and produces a SHA-1 hash of the current date combined with the ID from the URL.

For instance, if the server receives

```
PUT /message/526aa677a8ceb64569c9d4fb
```

it will respond with a hash of the current date (as a string) and the ID.

The SHA-1 can be computed like this:

```js
require('crypto')
  .createHash('sha1')
  .update(new Date().toDateString() + id)
  .digest('hex')
```

## HINTS
Express.js apps can also be mounted to paths that contain a variable by prepending a : to the beginning of a variable name. For instance, in the following, app handles PUT requests in any subdirectory of /path/:

```js
app.put('/path/:NAME', function(req, res){ /* ... */ });
```

The given variable is then stored in req.params. So, to extract parameters from within the request handlers, use:

```js
req.params.NAME
```

BONUS

You can use req.param middleware to parse the URL parameter.

For example,

```js
app.param('id', function (req, res, next, id) {
  req.id = id
  ...
  next()
})

app.get('/message/:id', function (req, res, next) {
  console.log(req.id)
  next()
})
```

## My Solution

```js
var express = require('express');
var app = express();

app.put('/message/:NAME', function(req, res) {
  var id = req.params.NAME;
  res.send(require('crypto')
    .createHash('sha1')
    .update(new Date().toDateString() + id)
    .digest('hex')
  );
});

app.listen(process.argv[2]);
```

Official Solution:

```js
var express = require('express')
var app = express()

app.put('/message/:id', function(req, res) {
  var id = req.params.id
  var str = require('crypto')
    .createHash('sha1')
    .update(new Date().toDateString() + id)
    .digest('hex')
  res.send(str)
})

app.listen(process.argv[2])
```

# What's In Query
Oftentimes, we need to process the data from the URL query string (urlencoded).

Write a route that extracts data from the query string in the `GET /search URL route`, e.g. `?results=recent&include_tabs=true` and then outputs it back to the user in JSON format.

Use `app.get('/search', function(){...})` for the route.

In Express.js, to extract query string parameters, we can use (inside the request handler):

```js
req.query.NAME
```

## HINTS
No need to install query middleware. It's part of the Express.js framework.

To output JSON we can use:

```js
res.send(object)
```

## My Solution

```js
var express = require('express');
var app = express();
var url = require('url');

app.get('/search', function(req, res) {
  var parsedURL = url.parse(req.url, true);
  res.send(JSON.stringify(parsedURL.query));
});

app.listen(process.argv[2]);
```

Official Solution:

```js
var express = require('express')
var app = express()

app.get('/search', function(req, res) {
  var query = req.query
  res.send(query)
})

app.listen(process.argv[2])
```

# JSON Me
Most of the times we're building RESTful API servers with JSON.

Write a server that, when it receives a GET, reads a file, parses it to JSON, and responds with that content to the user.

The server should respond to any GET that matches the /books resource path. As always, the port is passed in `process.argv[2]`. The file to read is passed in `process.argv[3]`.

Respond with:

```js
res.json(object)
```

Everything should match the /books resource path.

For reading the file, use the fs module, e.g.,

```js
fs.readFile(filename, callback)
```

## HINTS
While the parsing can be done with JSON.parse:

```js
object = JSON.parse(string)
```

No need to install the fs module. It's part of the core and the Node.js platform.

## My Solution

```js
var express = require('express');
var fs = require("fs");
var app = express();
app.set('json spaces', 0)
app.get('/books', function(req, res) {
  fs.readFile(process.argv[3], 'utf8', function(err, data) {
    if (err) throw err;
    var out = JSON.parse(data);
    res.json(out)
  });

});

app.listen(process.argv[2]);
```

Official Solution (Not working on c9)

```js
var express = require('express')
var app = express()
var fs = require('fs')

app.get('/books', function(req, res) {
  var filename = process.argv[3]
  fs.readFile(filename, function(e, data) {

    if (e) return res.sendStatus(500)
    try {
      books = JSON.parse(data)
    } catch (e) {
      res.sendStatus(500)
    }
    res.json(books)
  })
})

app.listen(process.argv[2])
```
