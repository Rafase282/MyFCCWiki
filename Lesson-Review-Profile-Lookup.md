# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282 based on FCC Wiki version.

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Details
We have an array of objects representing different people in our contacts lists.

A **lookUp** function that takes **firstName** and a property (**prop**) as arguments has been pre-written for you.

The function should check if **firstName** is an actual contact's **firstName** and the given property (**prop**) is a property of that contact.

If both are true, then return the "value" of that property.

If **firstName** does not correspond to any contacts then return **"No such contact"**

If **prop** does not correspond to any valid properties then return **"No such property"**

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Challenge: Accessing Objects Properties with Bracket Notation](http://www.freecodecamp.com/challenges/accessing-objects-properties-with-bracket-notation)
- [Challenge: Iterate with JavaScript For Loops](http://www.freecodecamp.com/challenges/iterate-with-javascript-for-loops)

## Problem Explanation:
- Change the code below `// Only change code below this line` and up to `// Only change code above this line`
- Take note that you are editing the inside of the `lookUp` function
  - This function includes two parameters, `firstName` and `prop`

- The function should check look through the `contact` list for the given `firstName` parameter
  - If there is a match found, the function should then look for the given `prop` parameter
  - If both `firstName` and the associated `prop` are found, you should return the value of the `prop`
  - If `firstName` is found and no associated `prop` is found, you should return `"No such property"`
  - If `firstName` isn't found anywhere, you should return `"No such contact"`

## Hint: 1
- Use a **for loop** to cycle through the `contact` list

## Hint: 2
- Use a nested `if` statement to first check if the `firstName` matches, and then checks if the `prop` matches

## Hint: 3
- Leave your `return "No such contact"` out of the `for loop` as a final catch-all

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function lookUp(firstName, prop) {
  // Only change code below this line
  var answer = "No such contact";
  contacts.some(function(arg) {
    if (arg.firstName === firstName && arg.hasOwnProperty(prop) === true) {
      answer = arg[prop];
    } else if (arg.hasOwnProperty(prop) === false) {
      answer = "No such property";
    }
  });
  return answer;
  // Only change code above this line
}

// Change these values to test your function
lookUp("Kristian", "lastName");
```

# Code Explanation:
- Declare a variable to hold the answer with a predefined answer.
- use `.some()` to check if the object has the contact and the property and save it to the variable.
- If it does not pass the previous test then check if it does not have the property and return the right answer.
- Outside of the `.some()` return the variable withthe answer.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
