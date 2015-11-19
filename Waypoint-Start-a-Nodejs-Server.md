# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

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


#### HINTS
  The fs.readdir() method takes a pathname as its first argument and a<br>  callback as its second. The callback signature is:  

```
 function callback (err, list) { /* ... */ }  
```

  where list is an array of filename strings.  

  Documentation on the fs module can be found by pointing your browser here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/fs.html  

  You may also find node's path module helpful, particularly the extname<br>  method.  

  Documentation on the path module can be found by pointing your browser<br>  here:<br>  file:///home/ubuntu/.nvm/versions/node/v4.1.1/lib/node_modules/learnyounod<br>  e/node_apidoc/path.html  
