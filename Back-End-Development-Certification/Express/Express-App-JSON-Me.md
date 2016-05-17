### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Express App: JSON Me

Most of the times we're building RESTful API servers with JSON.

Write a server that, when it receives a GET, reads a file, parses it to JSON, and responds with that content to the user.

The server should respond to any GET that matches the /books resource path. As always, the port is passed in `process.argv[2]`. The file to read is passed in `process.argv[3]`.

Respond with:

```javascript
res.json(object)
```

Everything should match the /books resource path.

For reading the file, use the fs module, e.g.,

```javascript
fs.readFile(filename, callback)
```

## HINTS

While the parsing can be done with JSON.parse:

```javascript
object = JSON.parse(string)
```

No need to install the fs module. It's part of the core and the Node.js platform.

## My Solution

```javascript
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

## Official Solution (Not working on c9)

```javascript
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
