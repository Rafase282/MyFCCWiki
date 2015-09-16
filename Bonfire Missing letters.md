# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 2/5

Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return undefined.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [String.charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
- [String.fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)

## Problem Script:

```js
function fearNotLetter(str) {
  return str;
}

fearNotLetter('abce');
```

# Problem Explanation:
- You will create a program that will find the missing letter from a string and add it. If there is not missing letter it will return undefined. There is currently no test case for it missing more than one letter, but if anything recursion can be implemented or a second or more calls to the same function as needed. Also the letters are always provided in order so there is no need to sort them.

## Hint: 1
- You will need to convert from character to ASCII code using the two methods provided in the description.

## Hint: 2
- You will have to check for the difference in ASCII code as they are in order. Using a chart would be very helpful.

## Hint: 3
- You will need to figure out where to insert the letter and how to do it, along with handling the case that there is not missing letter as it needs an specific return value.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function fearNotLetter(str) {
  // Create our variables.
  var firstCharacter = str.charCodeAt(0);
  var valueToReturn = '';
  var secondCharacter = '';

  // Function to find the missing letters
  var addCharacters = function(a, b) {
    while (a - 1 > b) {
      b++;
      valueToReturn += String.fromCharCode(b);
    }

    return valueToReturn;
  };

  // Check if letters are missing in between.
  for (var index = 1; index < str.length; index++) {
    secondCharacter = str.charCodeAt(index);

    // Check if the diference in code is greater than one.
    if (secondCharacter - firstCharacter > 1) {
      // Call function to missing letters
      addCharacters(secondCharacter, firstCharacter);
    }

    // Switch positions
    firstCharacter = str.charCodeAt(index);
  }

  // Check whether to return undefined or the missing letters.
  if (valueToReturn === '')
    return undefined;
  else
    return valueToReturn;
}
```

# Code Explanation:
- Read comments in code.
