# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 2/5

Convert the given number into a roman numeral.

All roman numerals answers should be provided in upper-case.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Roman Numerals](http://www.mathsisfun.com/roman-numerals.html)
- [Array.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
- [Array.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
- [Array.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

## Problem Script:

```js
function convert(num) {
 return num;
}

convert(36);
```

## Problem Explanation:
- You will create a program that converts an integer to a roman numeral.

### Hint: 1
- Creating an array with the Roman Numerals and one with the decimal equivalent for the new forms will be very helpful.

### Hint: 2
- If you add the numbers that go before the new letter is introduce, it will save you plenty of code, like 4 and 9.

### Hint: 3
- You can't have more than three consecutive Roman numerals together.

### Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
var convert = function(num) {

  // Create arrays with default conversion with matching indices.
  var decimalValue = [1, 4, 5, 9, 10, 40, 50, 90, 100, 400, 500, 900, 1000];
  var romanNumeral = ['I', 'IV', 'V', 'IX', 'X', 'XL', 'L', 'XC', 'C', 'CD', 'D', 'CM', 'M'];

  // Create a copy of num to work on and an empty string variable for the final roman number
  var numCopy = num;
  var romanized = '';

  // While the decimal number is greater than 0,
  while (numCopy > 0) {
    // Loop through the indices of the decimalValue array.
    for (var index = 0; index < decimalValue.length; index++) {
      // Get the maximum decimal number less or equal then the decimal number.
      if (+decimalValue[index] <= numCopy && +decimalValue[+index + 1] > numCopy) {
        // Add the Roman numeral & decrease numCopy by the decimal equivalent.
        romanized += romanNumeral[index];
        numCopy -= decimalValue[index];
      }
    }
  }

  return romanized;
};
```

# Code Explanation:
- Read comments on code.
