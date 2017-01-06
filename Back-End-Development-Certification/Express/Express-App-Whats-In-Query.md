### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Express App: What's In Query

Oftentimes, we need to process the data from the URL query string (urlencoded).

Write a route that extracts data from the query string in the `GET /search URL route`, e.g. `?results=recent&include_tabs=true` and then outputs it back to the user in JSON format.

Use `app.get('/search', function(){...})` for the route.

In Express.js, to extract query string parameters, we can use (inside the request handler):

```javascript
req.query.NAME
```

## HINTS

No need to install query middleware. It's part of the Express.js framework.

To output JSON we can use:

```javascript
res.send(object)
```

## My Solution

```javascript
var express = require('express');
var app = express();
var url = require('url');

app.get('/search', function(req, res) {
  var parsedURL = url.parse(req.url, true);
  res.send(JSON.stringify(parsedURL.query));
});

app.listen(process.argv[2]);
```

## Official Solution:

```javascript
var express = require('express')
var app = express()

app.get('/search', function(req, res) {
  var query = req.query
  res.send(query)
})

app.listen(process.argv[2])
```
