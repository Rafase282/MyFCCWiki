# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Repeat a given string (first argument) n times (second argument). Return an empty string if n is a negative number.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Global String Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

## Problem Script:

```js
function repeat(str, num) {
  // repeat after me
  return str;
}

repeat('abc', 3);
```

## Explanation:
The program is very simple, we have to take a variable and return that variable being repeated certain amount of times. No need to add space or anything, just keep repeating it into one single string.

## Hint: 1
You can't edit strings, you will need to create a variable to store the new string.

## Hint: 2
Create a loop to repeated the code as many times as needed.

## Hint: 3
Make the variable created store the current value and append the word to it.

## My code:

```js
function repeat(str, num) {
    var accumulatedStr = "";
    while (num > 0) {
        accumulatedStr += str;
        num--;
    }
    return accumulatedStr;
}
```

## My Code Explanation:
- Create a variable to store the repeated word.
- Use a while loop or for loop to repeat code as many times as needed according to `num`
- The we just have to add the string to the variable created on step one. and increase or decrease num depending on how you set the loop.
- At the end of the loop, return the variable for the repeated word.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
