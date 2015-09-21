# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a '...' ending.

Note that the three dots at the end add to the string length.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [String.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)

## Problem Script:

```js
function truncate(str, num) {
  // Clear out that junk in your trunk
  return str;
}

truncate('A-tisket a-tasket A green and yellow basket', 11);
```

## Explanation:
We need to reduce the length of the string or **truncate** it if it is longer than the given maximum lengths specified and add `...` to the end. If it is not that long then we keep it as is.

## Hint: 1
Strings are immutable in JavaScript so we will need a new variable to store the truncated string.

## Hint: 2
You will need to use slice and specify where to start and where to stop.

## Hint: 3
Do not forget that when we truncate the word, we also must count the length added by `...`

## My code:

```js
function truncate(str, num) {
    var truncd = '';
    if (str.length > num) {
        truncd = str.slice(0,num-3) + '...';
        return truncd;
    }
    return str;
}
```

## My Code Explanation:
- Create a variable `truncd` to store the truncated string.
- Check to see if the string needs to be truncated.
- If so, then slice the string and make sure you include the three dots.
- Return the truncated word or the original string if it didn't need to be truncated.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
