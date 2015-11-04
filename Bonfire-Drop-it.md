# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) |  [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details
- Difficulty: 2/5

Drop the elements of an array (first argument), starting from the front, until the predicate (second argument) returns true.

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links
- [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
- [Array.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)

# Problem Script:

```js
function drop(arr, func) {
  // Drop them elements.
  return arr;
}

drop([1, 2, 3], function(n) {return n < 3; });
```

## Explanation:
Basically while the second argument is not true, you will have to remove the first element from the left of the array that was passed as the first argument.

## Hint: 1
You can use Array.shift() or filter that you should be more familiar with to solve this problem in a few lines of code.

## Hint: 2
Shift returns the element that was removed which we don't really need, all we need is the modified array that is left.

## Hint: 3
If you still can't figure out how to solve it with shift, then try solving it with filter, and check how filter works, if you become familiar with it, then you can make the code with shift.

## Code Solution:

```js
Code from Max Helmetag (https://github.com/mhelmetag)

function drop(arr, func) {
  var times = arr.length;
  for (var i = 0; i < times; i++) {
    if (func(arr[0])) {
      break;
    } else {
      arr.shift();
    }
  }

  return arr;
}

drop([1, 2, 3], function(n) {return n < 3; });
```

## My Code Explanation:
- Create a for loop to check each element.
- Then check for the function given if true then stop, otherwise remove that element.
- return the array.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
