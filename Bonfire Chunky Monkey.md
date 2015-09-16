# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Write a function that splits an array (first argument) into groups the length of size (second argument) and returns them as a multidimensional array.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Array.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

## Problem Script:

```js
function chunk(arr, size) {
  // Break it up.
  return arr;
}

chunk(['a', 'b', 'c', 'd'], 2);
```

## Explanation:
You need to take an array from the first parameter, and then make sub-arrays the size of the second parameter and return them inside a big array.

## Hint: 1
You will need two extra variables to store temp values and the new arrays.

## Hint: 2
You need to check if you already have enough elements or not and add them.

## Hint: check
You will need to check if there is any elements to push before returning the final results.

## My code:

```js
var temp = [];
var result = [];

for (var a in arr) {
  if (a % size !== size - 1)
    temp.push(arr[a]);
  else {
    temp.push(arr[a]);
    result.push(temp);
    temp = [];
  }
}

if (temp.length !== 0)
  result.push(temp);
 return result;
}
```

## My Code Explanation:
- Create a temp variable and an results variable.
- For every element in the array:
  - if the index of the element is even then add the element temp variable.
  - Otherwise it means that we already have an element and should add the element and flush temp into results.

- Outside the loop, we check if temp is empty and return accordingly.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
