# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) |  [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details
- Difficulty: 4/5

Return true if the passed string is a valid US phone number

The user may fill out the form field any way they choose as long as it is a valid US number. The following are all valid formats for US numbers:

555-555-5555, (555)555-5555, (555) 555-5555, 555 555 5555, 5555555555, 1 555 555 5555

For this challenge you will be presented with a string such as "800-692-7753" or "8oo-six427676;laskdjf". Your job is to validate or reject the US phone number based on any combination of the formats provided above. The area code is required. If the country code is provided, you must confirm that the country code is "1". Return true if the string is a valid US phone number; otherwise false.

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links
- [RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

# Problem Script:

```js
function telephoneCheck(str) {
  // Good luck!
  return true;
}

telephoneCheck("555-555-5555");
```

# Problem Explanation:
- The task is not that hard to understand, implementing it is the hardest part. You have a to validate an US phone number. This means there is a certain amount of numbers required, while you don't need to put the country code, you will still need the area code and use one of the few formats allowed.

## Hint: 1
- There is no way around it, you will need to brush up your regular expressions skills.

## Hint: 2
- Try using a site like [http://regexpal.com/](http://regexpal.com/) to test the regex live while you create it.

## Hint: 3
- Start by trying to get it to validate each format from the example, each one should take a new line, once you get to select them all, then add examples that should not be selected and make sure they are not selected.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function telephoneCheck(str) {
  // Good luck!
  var re = /^(?:(?:\+?1\s*(?:[.-]\s*)?)?(?:\(\s*([2-9]1[02-9]|[2-9][02-8]1|[2-9][02-8][02-9])\s*\)|([2-9]1[02-9]|[2-9][02-8]1|[2-9][02-8][02-9]))\s*(?:[.-]\s*)?)?([2-9]1[02-9]|[2-9][02-9]1|[2-9][02-9]{2})\s*(?:[.-]\s*)?([0-9]{4})$/;

  return re.test(str);
}
```

# Code Explanation:
- While the answer works, there is a much shorter regex that will satisfy this problem. However the code provide is very good and robust when it comes to validating US phone numbers client side, a much better way would be to implement this [library](https://github.com/googlei18n/libphonenumber)

# Credits:
If you found this page useful, you can give thanks by copying and pasting this on the main chat:  **`thanks @Rafase282`**

> **NOTE:** Please add your username only if you have added any **relevant main contents** to the wiki page. (Please don't remove any existing usernames.)

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
