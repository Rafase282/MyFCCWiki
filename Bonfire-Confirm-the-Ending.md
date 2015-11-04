# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Check if a string (first argument) ends with the given target string (second argument).

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [String.substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)

## Problem Script:

```js
function end(str, target) {
  // "Never give up and good luck will find you."
  // -- Falcor
  return str;
}

end('Bastian', 'n');
```

## Explanation:
The function is a whole Boolean operation. You need to return true if the first argument ends with the second argument. This means that for the problem script, it should return true for the `end('Bastian', 'n'); case.`

## Hint: 1
Take a look at how substr() works. You will be trying to get the last Nth characters.

## Hint: 2
To get the Nth-to-Last character you will use length() and turn it into a negative number.

## Hint: 3
Check that you have the proper syntax and that you use `===` to compare.

## My code:

```js
function end(str, target) {
  if (str.substr(-target.length) === target)
    return true;
  else
    return false;
}
```

## My Code Explanation:
We use the subtring() with the negative value of the lengths of target. We could use -1 to get the last element but if the target is actually longer than one letter then the program will provide the wrong information. The we return true or false as needed.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
