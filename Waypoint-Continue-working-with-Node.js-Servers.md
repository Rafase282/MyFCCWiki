# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Continue working with Node.js Servers
# HTTP Collect
Write a program that performs an HTTP GET request to a URL provided to you<br>  as the first command-line argument. Collect all data from the server (not<br>  just the first "data" event) and then write two lines to the console<br>  (stdout).  

  The first line you write should just be an integer representing the number<br>  of characters received from the server. The second line should contain the<br>  complete String of characters sent by the server.   

## HINTS
  There are two approaches you can take to this problem:  

  1) Collect data across multiple "data" events and append the results<br>  together prior to printing the output. Use the "end" event to determine<br>  when the stream is finished and you can write the output.  

  2) Use a third-party package to abstract the difficulties involved in<br>  collecting an entire stream of data. Two different packages provide a<br>  useful API for solving this problem (there are likely more!): bl (Buffer<br>  List) and concat-stream; take your pick!  

  [http://npm.im/bl](http://npm.im/bl) [http://npm.im/concat-stream](http://npm.im/concat-stream)  

  To install a Node package, use the Node Package Manager npm. Simply type:  

```
 $ npm install bl
```

  And it will download and install the latest version of the package into a<br>  subdirectory named node_modules. Any package in this subdirectory under<br>  your main program file can be loaded with the require syntax without being<br>  prefixed by './':  

```
 var bl = require('bl')
```

  Node will first look in the core modules and then in the node_modules<br>  directory where the package is located.  

  If you don't have an Internet connection, simply make a node_modules<br>  directory and copy the entire directory for the package you want to use<br>  from inside the learnyounode installation directory:  

  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_modules/bl<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_modules/concat-stream  

  Both bl and concat-stream can have a stream piped in to them and they will<br>  collect the data for you. Once the stream has ended, a callback will be<br>  fired with the data:  

```
 response.pipe(bl(function (err, data) { /* ... */ }))  
 // or  
 response.pipe(concatStream(function (data) { /* ... */ }))
```

  Note that you will probably need to data.toString() to convert from a<br>  Buffer.  

  Documentation for both of these modules has been installed along with<br>  learnyounode on your system and you can read them by pointing your browser<br>  here:  

  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/docs/bl.html<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/docs/concat-stream.html  

## My Solution

```js
var http = require('http');
var uri = process.argv[2];
var str = '';
http.get(uri, function(response) {
  response.setEncoding('utf8');
  response.on("data", function(data) {
    str += data;
  });
  response.on('end', function() {
    console.log(str.length);
    console.log(str);
  });
});
```

Official Solution:

```js
var http = require('http')  
     var bl = require('bl')  
     http.get(process.argv[2], function (response) {  
       response.pipe(bl(function (err, data) {  
         if (err)  
           return console.error(err)  
         data = data.toString()  
         console.log(data.length)  
         console.log(data)  
       }))    
     })
```

# Juggling Async
This problem is the same as the previous problem (HTTP COLLECT) in that<br>  you need to use http.get(). However, this time you will be provided with<br>  three URLs as the first three command-line arguments.  

  You must collect the complete content provided to you by each of the URLs<br>  and print it to the console (stdout). You don't need to print out the<br>  length, just the data as a String; one line per URL. The catch is that you<br>  must print them out in the same order as the URLs are provided to you as<br>  command-line arguments.  

## HINTS
  Don't expect these three servers to play nicely! They are not going to<br>  give you complete responses in the order you hope, so you can't naively<br>  just print the output as you get it because they will be out of order.  

  You will need to queue the results and keep track of how many of the URLs<br>  have returned their entire contents. Only once you have them all, you can<br>  print the data to the console.  

  Counting callbacks is one of the fundamental ways of managing async in<br>  Node. Rather than doing it yourself, you may find it more convenient to<br>  rely on a third-party library such as [async](http://npm.im/async) or<br>  [after](http://npm.im/after). But for this exercise, try and do it without<br>  any external helper library.  

### My Solution

```js
var http = require('http');

// Slice the arguments from command line to get only the urls.
var URLs = process.argv.slice(2);

// Counter to keep track of async responses.
var count = 0;

// Arry to store completed responses
var resArr = [];
URLs.forEach(getData);

// Makes the call and handles everythign.
function getData(url, index) {
  http.get(url, function(response) {
    var str = '';
    response.setEncoding('utf8');
    response.on("data", function(data) {
      str += data;
    });
    response.on('end', function() {
      resArr[index] = str;
      count++;
      if (count === URLs.length) {
        resArr.forEach(function(msg) {
          console.log(msg);
        });
      }
    });
  });
}
```

Official Solution:

```js
var http = require('http')  
     var bl = require('bl')  
     var results = []  
     var count = 0  
     function printResults () {  
       for (var i = 0; i < 3; i++)  
         console.log(results[i])  
     }  
     function httpGet (index) {  
       http.get(process.argv[2 + index], function (response) {  
         response.pipe(bl(function (err, data) {  
           if (err)  
             return console.error(err)  

           results[index] = data.toString()  
           count++  

           if (count == 3)  
             printResults()  
         }))  
       })  
     }  

     for (var i = 0; i < 3; i++)  
       httpGet(i)
```

# Time Server
Write a TCP time server!  

  Your server should listen to TCP connections on the port provided by the<br>  first argument to your program. For each connection you must write the<br>  current date & 24 hour time in the format:  

```
 "YYYY-MM-DD hh:mm"
```

  followed by a newline character. Month, day, hour and minute must be<br>  zero-filled to 2 integers. For example:  

```
 "2013-07-06 17:42"
```

## HINTS
  For this exercise we'll be creating a raw TCP server. There's no HTTP<br>  involved here so we need to use the net module from Node core which has<br>  all the basic networking functions.  

  The net module has a method named net.createServer() that takes a callback<br>  function. Unlike most callbacks in Node, the callback used by<br>  createServer() is called more than once. Every connection received by your<br>  server triggers another call to the callback. The callback function has<br>  the signature:  

```
 function callback (socket) { /* ... */ }
```

  net.createServer() also returns an instance of your server. You must call<br>  server.listen(portNumber) to start listening on a particular port.  

  A typical Node TCP server looks like this:  

```
 var net = require('net')  
 var server = net.createServer(function (socket) {  
   // socket handling logic  
 })  
 server.listen(8000)
```

  Remember to use the port number supplied to you as the first command-line<br>  argument.  

  The socket object contains a lot of meta-data regarding the connection,<br>  but it is also a Node duplex Stream, in that it can be both read from, and<br>  written to. For this exercise we only need to write data and then close<br>  the socket.  

  Use socket.write(data) to write data to the socket and socket.end() to<br>  close the socket. Alternatively, the .end() method also takes a data<br>  object so you can simplify to just: socket.end(data).  

  Documentation on the net module can be found by pointing your browser<br>  here:  

  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/net.html  

  To create the date, you'll need to create a custom format from a new<br>  Date() object. The methods that will be useful are:  

```
 date.getFullYear()  
 date.getMonth()     // starts at 0  
 date.getDate()      // returns the day of month  
 date.getHours()  
 date.getMinutes()
```

  Or, if you want to be adventurous, use the strftime package from npm. The<br>  strftime(fmt, date) function takes date formats just like the unix date<br>  command. You can read more about strftime at:<br>  [https://github.com/samsonjs/strftime](https://github.com/samsonjs/strftim     e)  

## My Solution

```js
var net = require('net');
var port = process.argv[2];
var server = net.createServer(function(socket) {
  // socket handling logic
  var date = new Date();
  var out = date.getFullYear() + '-' + (date.getMonth() + 1) + '-' + date.getDate() + ' ' + date.getHours() + ':' + date.getMinutes();
  socket.end(out);
  socket.pipe(socket);
});

server.listen(port);
```

Official Solution:

```js
var net = require('net')  
     function zeroFill(i) {  
       return (i < 10 ? '0' : '') + i  
     }  
     function now () {  
       var d = new Date()  
       return d.getFullYear() + '-'  
         + zeroFill(d.getMonth() + 1) + '-'  
         + zeroFill(d.getDate()) + ' '  
         + zeroFill(d.getHours()) + ':'  
         + zeroFill(d.getMinutes())  
     }  

     var server = net.createServer(function (socket) {  
       socket.end(now() + '\n')  
     })  

     server.listen(Number(process.argv[2]))
```
