# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Start a Nodejs Server
### Baby Steps
  Write a program that accepts one or more numbers as command-line arguments   and prints the sum of those numbers to the console (stdout).

#### HINTS
  You can access command-line arguments via the global process object. The   process object has an argv property which is an array containing the   complete command-line. i.e. process.argv.  

  To get started, write a program that simply contains:  

```
 console.log(process.argv)
```

  Run it with node program.js and some numbers as arguments. e.g:  

```
 $ node program.js 1 2 3
```

  In which case the output would be an array looking something like:  

```
 [ 'node', '/path/to/your/program.js', '1', '2', '3' ]
```

  You'll need to think about how to loop through the number arguments so<br>  you can output just their sum. The first element of the process.argv array<br>  is always 'node', and the second element is always the path to your<br>  program.js file, so you need to start at the 3rd element (index 2), adding<br>  each item to the total until you reach the end of the array.  

  Also be aware that all elements of process.argv are strings and you may<br>  need to coerce them into numbers. You can do this by prefixing the<br>  property with + or passing it to Number(). e.g. +process.argv[2] or<br>  Number(process.argv[2]).  

  learnyounode will be supplying arguments to your program when you run<br>  learnyounode verify program.js so you don't need to supply them yourself.<br>  To test your program without verifying it, you can invoke it with<br>  learnyounode run program.js. When you use run, you are invoking the test<br>  environment that learnyounode sets up for each exercise.  

### My Code

```js
var newarr = process.argv.slice(2);
var out = newarr.reduce(function(num, num2){
  return +num + +num2  });
console.log(out);
```

## My First I/O!
 Write a program that uses a single synchronous filesystem operation to<br> read a file and print the number of newlines (\n) it contains to the<br> console (stdout), similar to running cat file | wc -l.  

 The full path to the file to read will be provided as the first<br> command-line argument (i.e., process.argv[2]). You do not need to make<br> your own test file.  

### HINTS
 To perform a filesystem operation you are going to need the fs module from<br> the Node core library. To load this kind of module, or any other "global"<br> module, use the following incantation:  

```
var fs = require('fs')
```

 Now you have the full fs module available in a variable named fs.  

 All synchronous (or blocking) filesystem methods in the fs module end with<br> 'Sync'. To read a file, you'll need to use<br> fs.readFileSync('/path/to/file'). This method will return a Buffer object<br> containing the complete contents of the file.  

 Documentation on the fs module can be found by pointing your browser here:<br> file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br> e/node_apidoc/fs.html  

 Buffer objects are Node's way of efficiently representing arbitrary arrays<br> of data, whether it be ascii, binary or some other format. Buffer objects<br> can be converted to strings by simply calling the toString() method on<br> them. e.g. var str = buf.toString().  

 Documentation on Buffers can be found by pointing your browser here:<br> file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br> e/node_apidoc/buffer.html  

 If you're looking for an easy way to count the number of newlines in a<br> string, recall that a JavaScript String can be .split() into an array of<br> substrings and that '\n' can be used as a delimiter. Note that the test<br> file does not have a newline character ('\n') at the end of the last line,<br> so using this method you'll end up with an array that has one more element<br> than the number of newlines.  

### My code

```js
var newarr = process.argv[2];
var fs = require('fs');
var file = fs.readFileSync(newarr).toString().split('\n');
console.log(file.length -1)
```

## My First ASYNC I/O!
  Write a program that uses a single asynchronous filesystem operation to<br>  read a file and print the number of newlines it contains to the console<br>  (stdout), similar to running cat file | wc -l.  

  The full path to the file to read will be provided as the first<br>  command-line argument.  

### HINTS
  The solution to this problem is almost the same as the previous problem<br>  except you must now do it the Node.js way: asynchronous.  

  Instead of fs.readFileSync() you will want to use fs.readFile() and<br>  instead of using the return value of this method you need to collect the<br>  value from a callback function that you pass in as the second argument. To<br>  learn more about callbacks, check out:<br>  [https://github.com/maxogden/art-of-node#callbacks.](https://github.com/maxogden/art-of-node#callbacks)

  Remember that idiomatic Node.js callbacks normally have the signature:  

```
 function callback (err, data) { /* ... */ }
```

  so you can check if an error occurred by checking whether the first<br>  argument is truthy. If there is no error, you should have your Buffer<br>  object as the second argument. As with readFileSync(), you can supply<br>  'utf8' as the second argument and put the callback as the third argument<br>  and you will get a String instead of a Buffer.  

  Documentation on the fs module can be found by pointing your browser here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/fs.html  

## My solution

```js
  var newarr = process.argv[2];
var fs = require('fs');
fs.readFile(newarr, function doneReading(err, fileContents) {
    if (err){
        console.log('Error')
    } else {
        var number = fileContents.toString().split('\n').length -1;
    console.log(number);
    }

});
```

## Filtered LS
  Create a program that prints a list of files in a given directory,<br>  filtered by the extension of the files. You will be provided a directory<br>  name as the first argument to your program (e.g. '/path/to/dir/') and a<br>  file extension to filter by as the second argument.  

  For example, if you get 'txt' as the second argument then you will need to<br>  filter the list to only files that end with .txt. Note that the second<br>  argument will not come prefixed with a '.'.  

  The list of files should be printed to the console, one file per line. You<br>  must use asynchronous I/O.  

### HINTS
  The fs.readdir() method takes a pathname as its first argument and a<br>  callback as its second. The callback signature is:  

```
 function callback (err, list) { /* ... */ }
```

  where list is an array of filename strings.  

  Documentation on the fs module can be found by pointing your browser here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/fs.html  

  You may also find node's path module helpful, particularly the extname<br>  method.  

  Documentation on the path module can be found by pointing your browser<br>  here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/path.html  

### My solution

```js
var fs = require('fs');
 fs.readdir(process.argv[2], function callback (err, list){
     if (err){
         console.log('Error');
     } else {
         list.filter(function (filename){
             return filename.indexOf('.' + process.argv[3]) >= 0
         }).forEach(function (file) {
             console.log(file);
         })
     }
 });
```

 Standard solution from the program:

```js
var fs = require('fs')  
    var path = require('path')  
    fs.readdir(process.argv[2], function (err, list) {  
      list.forEach(function (file) {  
        if (path.extname(file) === '.' + process.argv[3])  
          console.log(file)  
      })  
    })
```

## Make It Modular
 This problem is the same as the previous but introduces the concept of<br> modules. You will need to create two files to solve this.  

 Create a program that prints a list of files in a given directory,<br> filtered by the extension of the files. The first argument is the<br> directory name and the second argument is the extension filter. Print the<br> list of files (one file per line) to the console. You must use<br> asynchronous I/O.  

 You must write a module file to do most of the work. The module must<br> export a single function that takes three arguments: the directory name,<br> the filename extension string and a callback function, in that order. The<br> filename extension argument must be the same as what was passed to your<br> program. Don't turn it into a RegExp or prefix with "." or do anything<br> except pass it to your module where you can do what you need to make your<br> filter work.  

 The callback function must be called using the idiomatic node(err, data)<br> convention. This convention stipulates that unless there's an error, the<br> first argument passed to the callback will be null, and the second will be<br> your data. In this exercise, the data will be your filtered list of files,<br> as an Array. If you receive an error, e.g. from your call to<br> fs.readdir(), the callback must be called with the error, and only the<br> error, as the first argument.  

 You must not print directly to the console from your module file, only<br> from your original program.  

 In the case of an error bubbling up to your original program file, simply<br> check for it and print an informative message to the console.  

 These four things are the contract that your module must follow.  

  » Export a single function that takes exactly the arguments described.<br>  » Call the callback exactly once with an error or some data as described.<br>  » Don't change anything else, like global variables or stdout.<br>  » Handle all the errors that may occur and pass them to the callback.       

 The benefit of having a contract is that your module can be used by anyone<br> who expects this contract. So your module could be used by anyone else who<br> does learnyounode, or the verifier, and just work.  

### HINTS
 Create a new module by creating a new file that just contains your<br> directory reading and filtering function. To define a single function<br> export, you assign your function to the module.exports object, overwriting<br> what is already there:  

```
module.exports = function (args) { /* ... */ }
```

 Or you can use a named function and assign the name.  

 To use your new module in your original program file, use the require()<br> call in the same way that you require('fs') to load the fs module. The<br> only difference is that for local modules must be prefixed with './'. So,<br> if your file is named mymodule.js then:  

```
var mymodule = require('./mymodule.js')
```

 The '.js' is optional here and you will often see it omitted.  

 You now have the module.exports object in your module assigned to the<br> mymodule variable. Since you are exporting a single function, mymodule is<br> a function you can call!  

 Also keep in mind that it is idiomatic to check for errors and do<br> early-returns within callback functions:  

```
function bar (callback) {  
  foo(function (err, data) {  
    if (err)  
      return callback(err) // early return  

    // ... no error, continue doing cool things with `data`  

    // all went well, call callback with `null` for the error argument  

    callback(null, data)  
  })  
}
```

### My solution
> proogram.js

```js
var mymodule = require('./findfile');
mymodule(process.argv[2], process.argv[3], function callback(err, data) {
  if (err) {
    return callback(err);
  }
  data.forEach(function(file) {
    console.log(file);
  });
});
```

> findfile.js

```js
module.exports = function findFziles(dir, ext, callback) {
  var fs = require('fs');
  fs.readdir(dir, function(err, list) {
    if (err) {
      return callback(err);
    } else {
      var data = list.filter(function(filename) {
        return filename.indexOf('.' + ext) >= 0;
      });
      return callback(null, data);
    }
  });
};
```

Here's the official solution in case you want to compare notes: _/home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounode/exercises/make_it_modular/solution/solution.js_ :  

```js
    var filterFn = require('./solution_filter.js')  
    var dir = process.argv[2]  
    var filterStr = process.argv[3]  
    filterFn(dir, filterStr, function (err, list) {  
      if (err)  
        return console.error('There was an error:', err)  
      list.forEach(function (file) {  
        console.log(file)  
      })  
    })
```

_/home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounode/exercises/make_it_modular/solution/solution_filter.js_ :  

```js
    var fs = require('fs')  
    var path = require('path')  
    module.exports = function (dir, filterStr, callback) {  
      fs.readdir(dir, function (err, list) {  
        if (err)  
          return callback(err)  

        list = list.filter(function (file) {  
          return path.extname(file) === '.' + filterStr  
        })  

        callback(null, list)  
      })  
    }
```

Basically you have to make two files, one who will include another file that takes three arguments, filename, extension, and callback function. and then call that function from the first file and passing the right arguments. The tricky part is the callback. For the second file it needs to be called when there is an early error and also the information should be returned to the callback with a null error so the other function can then print the information.

## HTTP CLIENT
  Write a program that performs an HTTP GET request to a URL provided to you<br>  as the first command-line argument. Write the String contents of each<br>  "data" event from the response to a new line on the console (stdout).  

### HINTS
  For this exercise you will need to use the http core module.  

  Documentation on the http module can be found by pointing your browser<br>  here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/http.html  

  The http.get() method is a shortcut for simple GET requests, use it to<br>  simplify your solution. The first argument to http.get() can be the URL<br>  you want to GET; provide a callback as the second argument.  

  Unlike other callback functions, this one has the signature:  

```
 function callback (response) { /* ... */ }
```

  Where the response object is a Node Stream object. You can treat Node<br>  Streams as objects that emit events. The three events that are of most<br>  interest are: "data", "error" and "end". You listen to an event like so:  

```
 response.on("data", function (data) { /* ... */ })
```

  The "data" event is emitted when a chunk of data is available and can be<br>  processed. The size of the chunk depends upon the underlying data source.  

  The response object / Stream that you get from http.get() also has a<br>  setEncoding() method. If you call this method with "utf8", the "data"<br>  events will emit Strings rather than the standard Node Buffer objects<br>  which you have to explicitly convert to Strings.  

### My solution

```js
var http = require('http');
var uri = process.argv[2];
http.get(uri, function(response) {
  response.setEncoding('utf8');
  response.on("data", function(data) {
    console.log(data);
  });
});
```

Soution from the course:

```js
var http = require('http')  
     http.get(process.argv[2], function (response) {  
       response.setEncoding('utf8')  
       response.on('data', console.log)  
       response.on('error', console.error)  
     })
```
