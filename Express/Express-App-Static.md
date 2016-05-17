### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Express App: Static

Apply static middleware to serve `index.html` file without any routes.

Your solution must listen on the port number supplied by `process.argv[2]`.

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

```javascript
app.use(express.static(path.join(__dirname, 'public')));
```

For this exercise expressworks will pass you the path:

```javascript
app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));
```

## My Solution

```javascript
var express = require('express')
var path = require("path")
var app = express()
app.use(express.static(process.argv[3]));
app.listen(process.argv[2])
```

## Official Solution:

```javascript
var path = require('path')
    var express = require('express')
    var app = express()

    app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));

    app.listen(process.argv[2])
```
