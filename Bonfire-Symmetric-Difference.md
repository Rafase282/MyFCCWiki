# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 4/5

Create a function that takes two or more arrays and returns an array of the symmetric difference of the provided arrays.

The mathematical term symmetric difference refers to the elements in two sets that are in either the first or second set, but not in both.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Array.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
- [Symmetric Difference Video](https://www.youtube.com/watch?v=PxffSUQRkG4)
- [Symmetric Difference Text](https://en.wikipedia.org/wiki/Symmetric_difference)

## Problem Script:

```js
function sym(args) {
  return arguments;
}

sym([1, 2, 3], [5, 2, 1, 4]);
```

# Problem Explanation:
Symmetric Difference is the difference between **two** sets.

So in the Symmetric Difference Bonfire you would work through the arrays of numbers something like this -

`sym(A, B, C)` Translates to `sym(sym(A,B),C)`

Or in plain English - First find the Symmetric Difference of Set A and Set B. Then find the Symmetric Difference of this new set and Set C.

So -

`sym([1, 2, 5], [2, 3, 5], [3, 4, 5])`

would equal

`[1,4,5]`

Here's a nice video tutorial (with an awful fake British accent!) -

[YouTube - Symmetric Difference](https://www.youtube.com/watch?v=PxffSUQRkG4)

## Hint: 1
The arguments object is not an Array. It is similar to an Array, but does not have any Array properties except length. For example, it does not have the pop method. However it can be converted to a real Array:

`var args = Array.prototype.slice.call(arguments);`

## Hint: 2
Write a function that returns the symmetric difference of array1 and array2.

`yourFunction([1, 2, 3], [2, 4, 6])` must return `[1, 3, 4, 6]`

## Hint: 3
Use `Array.prototype.reduce` along with yourFunction to repeat the process on multiple arguments

Something a bit strange about the definition of symmetric difference is that if one identical item occurs in three different sets, it is a member of the symmetric difference.  An example is easier to explain:

```
a = [1, 2, 5]
b = [2, 3, 5]
c = [3, 4, 5]

sym(a, b) = [1, 3]
sym([1, 3], c) = [1, 4, 5]
```

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function sym() {

  // Convert the argument object into a proper array
  var args = Array.prototype.slice.call(arguments);

  // Return the symmetric difference of 2 arrays
  var getDiff = function(arr1, arr2) {

    // Returns items in arr1 that don't exist in arr2
    function filterFunction(arr1, arr2) {
      return arr1.filter(function(item) {
        return arr2.indexOf(item) === -1;
      });
    }

    // Run filter function on each array against the other then get unique values
    return filterFunction(arr1, arr2)
      .concat(filterFunction(arr2, arr1))
      .filter(function(item, idx, arr) {
        // Keep any items that are unique - the index of the current item === index of the first occurrence in the array
        return arr.indexOf(item) === idx;
      });
  };

  // Reduce all arguments getting the difference of them
  return args.reduce(getDiff, []);
}
```

# Code Explanation:
- Read comments in code.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
