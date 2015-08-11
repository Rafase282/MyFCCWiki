# Details

* Difficulty: 2/5

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument).

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links

* [Array.some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)

# My Code:
```
function find(arr, func) {
	// Make num undefined by default
    var num;
    // Loop thorugh the array and use the function to check
    for (var a in arr) {
        if (func(arr[a])){
        	// Store the first case and break the loop
            num = arr[a];
            return num;
        }
    }
  // otherwise return undefined
  return num;
}
```

# Problem Script:
```
function find(arr, func) {
  var num = 0;
  return num;
}

find([1, 2, 3, 4], function(num){ return num % 2 === 0; });

```
## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)