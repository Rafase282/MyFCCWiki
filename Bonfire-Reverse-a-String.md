# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Global String Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [String.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [Array.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

## Problem Script:

```js
function reverseString(str) {
  return str;
}

reverseString('hello');
```

## Explanation:
You need to take the string and reverse it so if you had originally 'hello', it will turn into 'olleh'. Because you will need to split it, you will be working with Arrays too.

## Hint: 1
You should split the string by characters.

## Hint: 2
Find out about the built in function to reverse a string.

## Hint: 3
Once you have split and reversed, do not forget to join them back into one string.

## My code:

```js
function reverseString(str) {
  var strReverse = str.split('').reverse().join('');
  return strReverse;
}
```

## My Code Explanation:
This is a straightforward code. We create a variable that will hold the string split by characters, and then reversed and put back together.
