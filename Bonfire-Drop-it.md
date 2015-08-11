# Details

* Difficulty: 2/5

Drop the elements of an array (first argument), starting from the front, until the predicate (second argument) returns true.

# Useful Links

* [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
* [Array.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)

# My code:

```
function drop(arr, func) {
  // Using Array.protptype.filter() which makes it pretty easy.
  return arr.filter(func);
}

drop([1, 2, 3], function(n) {return n < 3; });
```

# Problem Script:

```
function drop(arr, func) {
  // Drop them elements.
  return arr;
}

drop([1, 2, 3], function(n) {return n < 3; });
```

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)