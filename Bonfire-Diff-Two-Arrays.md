# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 2/5

Compare two arrays and return a new array with any items not found in both of the original arrays.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
- [Array.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
- [Array.concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)

## Problem Script:

```js
function diff(arr1, arr2) {
  var newArr = [];
  // Same, same; but different.
  return newArr;
}

diff([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```

## Problem Explanation:
- You will check two arrays and return a new array that contains only the items that are not in either of the original arrays.

### Hint: 1
- Merge the list to make it easy to compare functions.

### Hint: 2
- Use filter to get the new array, you will need to create a callback function.

### Hint: 3
- The best way to go about the callback function is to check if the number from the new merged array is not in **both** original arrays and return it.

### Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function diff(arr1, arr2) {
  var newArr = arr1.concat(arr2);

  function check(item) {
    if (arr1.indexOf(item) === -1 || arr2.indexOf(item) === -1) {
      return item;
    }
  }

  return newArr.filter(check);
}
```

# Code Explanation:
- Merge both arrays on the new one using `.concat()`
- Create a callback function to use with filter. The function will check if the number is not present in both original arrays and return it.
- Return the filtered array.
