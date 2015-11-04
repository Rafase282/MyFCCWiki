# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 2/5

Check if a value is classified as a boolean primitive. Return true or false.

Boolean primitives are true and false.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Boolean Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

## Problem Script:

```js
function boo(bool) {
  // What is the new fad diet for ghost developers? The Boolean.
  return bool;
}

boo(null);
```

# Problem Explanation:
- This program is very simple, the trick is to understand what a boolean primitive is. The programs requires a true or false answer.

## Hint: 1
- You will need to check for the type of the parameter to see if it is a boolean.

## Hint: 2
- To check for the type of a parameter, you can use `typeof`

## Hint: 3
- Since you must return true or false you can use if statements or just have it return the boolean used for the if statement.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function boo(bool) {
  // Uses the operator typeof to check if is a boolean
  // if yes then return true, if it is another type then return false
  return typeof bool === 'boolean';
}
```

# Code Explanation:
- Read comments on code.
