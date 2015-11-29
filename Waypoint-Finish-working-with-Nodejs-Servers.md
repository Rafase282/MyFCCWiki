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
## My Solution
# HTTP JSON API Server
## My Solution
