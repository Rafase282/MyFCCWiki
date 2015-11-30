# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Finish working with Nodejs Servers
# HTTP File Server
Write an HTTP server that serves the same text file for each request it<br>  receives.  

  Your server should listen on the port provided by the first argument to<br>  your program.  

  You will be provided with the location of the file to serve as the second<br>  command-line argument. You must use the fs.createReadStream() method to<br>  stream the file contents to the response.  

## HINTS
  Because we need to create an HTTP server for this exercise rather than a<br>  generic TCP server, we should use the http module from Node core. Like the<br>  net module, http also has a method named http.createServer() but this one<br>  creates a server that can talk HTTP.  

  http.createServer() takes a callback that is called once for each<br>  connection received by your server. The callback function has the<br>  signature:  

```
 function callback (request, response) { /* ... */ }
```

  Where the two arguments are objects representing the HTTP request and the<br>  corresponding response for this request. request is used to fetch<br>  properties, such as the header and query-string from the request while<br>  response is for sending data to the client, both headers and body.  

  Both request and response are also Node streams! Which means that you can<br>  use the streaming abstractions to send and receive data if they suit your<br>  use-case.  

  http.createServer() also returns an instance of your server. You must call<br>  server.listen(portNumber) to start listening on a particular port.  

  A typical Node HTTP server looks like this:  

```
 var http = require('http')  
 var server = http.createServer(function (req, res) {  
   // request handling logic...  
 })  
 server.listen(8000)
```

  Documentation on the http module can be found by pointing your browser<br>  here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/http.html  

  The fs core module also has some streaming APIs for files. You will need<br>  to use the fs.createReadStream() method to create a stream representing<br>  the file you are given as a command-line argument. The method returns a<br>  stream object which you can use src.pipe(dst) to pipe the data from the<br>  src stream to the dst stream. In this way you can connect a filesystem<br>  stream with an HTTP response stream.  

## My Solution

```js
var http = require("http");
var fs = require("fs");
var portNumber = process.argv[2];
var fileLocation = process.argv[3];
var server = http.createServer(function (req, res) {  
   // request handling logic...  
   var src = fs.createReadStream(fileLocation);
   src.pipe(res);
 })  
 server.listen(portNumber);
```

 Official Solution:

```js
var http = require('http')  
     var fs = require('fs')  
     var server = http.createServer(function (req, res) {  
       res.writeHead(200, { 'content-type': 'text/plain' })  
       fs.createReadStream(process.argv[3]).pipe(res)  
     })  

     server.listen(Number(process.argv[2]))
```

# HTTP Uppercaserer
Write an HTTP server that receives only POST requests and converts<br>  incoming POST body characters to upper-case and returns it to the client.  

  Your server should listen on the port provided by the first argument to<br>  your program.  

## HINTS
  While you're not restricted to using the streaming capabilities of the<br>  request and response objects, it will be much easier if you do.  

  There are a number of different packages in npm that you can use to<br>  "transform" stream data as it's passing through. For this exercise the<br>  through2-map package offers the simplest API.  

  through2-map allows you to create a transform stream using only a single<br>  function that takes a chunk of data and returns a chunk of data. It's<br>  designed to work much like Array#map() but for streams:  

```
 var map = require('through2-map')  
 inStream.pipe(map(function (chunk) {  
   return chunk.toString().split('').reverse().join('')  
 })).pipe(outStream)
```

  In the above example, the incoming data from inStream is converted to a<br>  String (if it isn't already), the characters are reversed and the result<br>  is passed through to outStream. So we've made a chunk character reverser!<br>  Remember though that the chunk size is determined up-stream and you have<br>  little control over it for incoming data.  

  To install through2-map type:  

```
 $ npm install through2-map
```

  If you don't have an Internet connection, simply make a node_modules<br>  directory and copy the entire directory for the module you want to use<br>  from inside the learnyounode installation directory:  

  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_modules/through2-map  

  Documentation for through2-map has been installed along with learnyounode<br>  on your system and you can read them by pointing your browser here:  

  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/docs/through2-map.html  

## My Solution

```js
var http = require("http");
var map = require("through2-map");
var portNumber = process.argv[2];
var server = http.createServer(function(req, res) {
  // request handling logic...
  req.pipe(map(function(chunk) {
    return chunk.toString().toUpperCase();
  })).pipe(res);
})
server.listen(portNumber);
```

Official Solution:

```js
var http = require('http')  
     var map = require('through2-map')  
     var server = http.createServer(function (req, res) {  
       if (req.method != 'POST')  
         return res.end('send me a POST\n')  
       req.pipe(map(function (chunk) {  
         return chunk.toString().toUpperCase()  
       })).pipe(res)  
     })  

     server.listen(Number(process.argv[2]))
```

# HTTP JSON API Server
Write an HTTP server that serves JSON data when it receives a GET request<br>  to the path '/api/parsetime'. Expect the request to contain a query string<br>  with a key 'iso' and an ISO-format time as the value.  

  For example:  

  /api/parsetime?iso=2013-08-10T12:10:15.474Z  

  The JSON response should contain only 'hour', 'minute' and 'second'<br>  properties. For example:  

```
 {  
   "hour": 14,  
   "minute": 23,  
   "second": 15  
 }
```

  Add second endpoint for the path '/api/unixtime' which accepts the same<br>  query string but returns UNIX epoch time in milliseconds (the number of<br>  milliseconds since 1 Jan 1970 00:00:00 UTC) under the property 'unixtime'.<br>  For example:  

```
 { "unixtime": 1376136615474 }
```

  Your server should listen on the port provided by the first argument to<br>  your program.  

## HINTS
  The request object from an HTTP server has a url property that you will<br>  need to use to "route" your requests for the two endpoints.  

  You can parse the URL and query string using the Node core 'url' module.<br>  url.parse(request.url, true) will parse content of request.url and provide<br>  you with an object with helpful properties.  

  For example, on the command prompt, type:  

```
 $ node -pe "require('url').parse('/test?q=1', true)"
```

  Documentation on the url module can be found by pointing your browser<br>  here:<br>  file:///home/ubuntu/.nvm/versions/node/v5.1.0/lib/node_modules/learnyounod<br>  e/node_apidoc/url.html  

  Your response should be in a JSON string format. Look at JSON.stringify()<br>  for more information.  

  You should also be a good web citizen and set the Content-Type properly:  

```
 res.writeHead(200, { 'Content-Type': 'application/json' })
```

  The JavaScript Date object can print dates in ISO format, e.g. new<br>  Date().toISOString(). It can also parse this format if you pass the string<br>  into the Date constructor. Date#getTime() will also come in handy.  

## My Solution

```js
var http = require("http");
var url = require('url');
var portNumber = process.argv[2];

function parsetime(time) {
  // Parse time as ISO
  return {
    "hour": time.getHours(),
    "minute": time.getMinutes(),
    "second": time.getSeconds()
  };
}

function unixtime(time) {
  // Parse time as unix time
  return {
    "unixtime": time.getTime()
  };
}

var server = http.createServer(function(req, res) {
  // request handling logic...
  var parsedURL = url.parse(req.url, true);
  var time = new Date(parsedURL.query.iso);
  var result;
  if (req.url.search('parsetime') != -1) {
    result = parsetime(time);
  } else if (req.url.search('unixtime') != -1) {
    result = unixtime(time);
  }

  if (result) {
    res.writeHead(200, {
      'Content-Type': 'application/json'
    });
    res.end(JSON.stringify(result));
  } else {
    res.writeHead(404);
    res.end();
  }
})
server.listen(portNumber);
```

Official Solution (Used part of it):

```js
var http = require('http')  
     var url = require('url')  
     function parsetime (time) {  
       return {  
         hour: time.getHours(),  
         minute: time.getMinutes(),  
         second: time.getSeconds()  
       }  
     }  
     function unixtime (time) {  
       return { unixtime : time.getTime() }  
     }  

     var server = http.createServer(function (req, res) {  
       var parsedUrl = url.parse(req.url, true)  
       var time = new Date(parsedUrl.query.iso)  
       var result  

       if (/^\/api\/parsetime/.test(req.url))  
         result = parsetime(time)  
       else if (/^\/api\/unixtime/.test(req.url))  
         result = unixtime(time)  

       if (result) {  
         res.writeHead(200, { 'Content-Type': 'application/json' })  
         res.end(JSON.stringify(result))  
       } else {  
         res.writeHead(404)  
         res.end()  
       }  
     })  
     server.listen(Number(process.argv[2]))
```
