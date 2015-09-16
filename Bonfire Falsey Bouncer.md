# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Remove all falsey values from an array.

Falsey values in javascript are false, null, 0, "", undefined, and NaN.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Boolean Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Problem Script:

```js
function bouncer(arr) {
  // Don't show a false ID to this bouncer.
  return arr;
}

bouncer([7, 'ate', '', false, 9]);
```

## Explanation:
Falsey values in javascript are false, null, 0, "", undefined, and NaN. Everything else is basically truthy. So if we find any falsey we have to filter then out.

## Hint: 1
Filter() requires a callback function, you need to create it.

## Hint: 2
You will return a boolean of the argument from the callback function, use `Boolean(arg)`

## Hint: 3
If you figure out how to use filter and boolean then you are all set, if not then keep checking for the answer.

## My code:

```js
function bouncer(arr) {
  function isTruthy(arg){
    return Boolean(arg);
  }
  var filteredArray = arr.filter(isTruthy);
  return filteredArray;
}
```

## My Code Explanation:
- Create a callback function that returns a boolean using the argument passed to it.
- use that call back function with filter to filter the array and return the filtered array.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
