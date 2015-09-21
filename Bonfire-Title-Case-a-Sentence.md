# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: #/5

Return the provided string with the first letter of each word capitalized.

For the purpose of this exercise, you should also capitalize connecting words like 'the' and 'of'.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [String.charAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)

## Problem Script:

```js
function titleCase(str) {
  return str;
}

titleCase("I'm a little tea pot");
```

## Explanation:
We have to return a sentence with camel case. This means that the first letter will always be in uppercase and the rest lowercase.

## Hint: 1
You should start by splitting the string into an array of words.

## Hint: 2
You should make the word lowercase before making the first letter uppercase.

## Hint: 3
You will need to create a new string with pieces of the previous one and at the end merge everythign into a single string again.

## My code:

```js
String.prototype.replaceAt = function(index, character) {
    return this.substr(0, index) + character + this.substr(index+character.length);
};


function titleCase(str) {
    var newTitle = str.split(' ');
    var updatedTitle = [];
    for (var st in newTitle) {
        updatedTitle[st] = newTitle[st].toLowerCase().replaceAt(0, newTitle[st].charAt(0).toUpperCase());
    }
    return updatedTitle.join(' ');
}
```

## My Code Explanation:
We are modifying the `replaceAt` function using prototype to facilitate the use of the program.

Split the string by whitespaces, and create a variable to track the updated title. Then we use a loop to turn turn the first character of the word to uppercase and the rest to lowercase. by creating concatenated string composed of the whole word in lowercase with the first character replaced by it's uppercase.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
