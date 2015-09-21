# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Problem Script:

```js
function destroyer(arr) {
  // Remove all the values
  return arr;
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```

## Explanation:
This problem is a bit tricky because you have to familiarize yourself with Arguments, as you will have to work with two **or more** but on the script you only see two. Many people hardcode this program for three arguments. You will remove any number from the first argument that is the same as any other other arguments.

## Hint: 1
You need to work with `arguments` as if it was a regular array. The best way is to convert it into one.

## Hint: 2
You need to filter, this also means you need to create a callback function, one that checks if the element is on the `indexOf()`

## Hint: 3
To convert `arguments` into an array use this code `var args = Array.prototype.slice.call(arguments);`

## My code:

```js
function destroyer(arr) {
  var args = Array.prototype.slice.call(arguments);
  args.splice(0,1);
  return arr.filter(function(element) {
    return args.indexOf(element) === -1;
  });
}
```

## My Code Explanation:
- The first line will turn the `arguments` variable into a full array instead of the limited array it currently it.
- Next I remove the first argument since I don't need, since I only want the other arguments passed besides the first which is the array we are going to compare against.
- The use the `filter()` to filter out the elements that are on the array and keep the ones that are not.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
