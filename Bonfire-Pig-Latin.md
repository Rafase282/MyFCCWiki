# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 2/5

Translate the provided string to pig latin.

[Pig Latin](http://en.wikipedia.org/wiki/Pig_Latin) takes the first consonant (or consonant cluster) of an English word, moves it to the end of the word and suffixes an "ay".

If a word begins with a vowel you just add "way" to the end.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Array.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
- [Array.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
- [Array.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [String.substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)
- [String.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)

## Problem Script:

```js
function translate(str) {
 return str;
}

translate("consonant");
```

# Problem Explanation:
- You need to create a program that will translate from English to Pig Latin. Check the instructions for converting to Ping Latin from the initial description or the wiki page. It might not be obvious but you need to remove all the consonants up to the first vowel in the case there letter does not start with a vowel.

## Hint: 1
- You will probably want to use regular expressions. This will allow you to convert the words easily.

## Hint: 2
- If the first character is a vowel, then take that whole word and add 'way' at the end. Otherwise comes the tricky part, take the consonant(s) before the first vowel and move it to the end and add 'ay'. This is where I had trouble since it was not clear that it was not just the first consonant but all of them before the first vowel.

## Hint: 3
- You will need to use everything you know about string manipulation to get the last part right. However, it can be done with `substr` alone.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function translate(str) {
  // Create variables to be used
  var pigLatin = '';
  var regex = /[aeiou]/gi;
  // Check if the first character is a vowel
  if (str[0].match(regex)) {
    pigLatin = str + 'way';
  } else {
    // Find how many consonants before the firs vowel.
    var vowelIndice = str.indexOf(str.match(regex)[0]);
    // Take the string from the first vowel to the last char
    // then add the consonants that were previously omitted and add the ending.
    pigLatin = str.substr(vowelIndice) + str.substr(0, vowelIndice) + 'ay';
  }

  return pigLatin;
}
```

# Code Explanation:
- Read comments in code.
