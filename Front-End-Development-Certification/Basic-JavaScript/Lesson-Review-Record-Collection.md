# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
You are given a JSON object representing (a small part of) your record collection. Each album is identified by a unique id number and has several properties. Not all albums have complete information.

## Instructions
Write a function which takes an **id**, a property (**prop**), and a **value**.

For the given **id** in **collection**:

If **value** is non-blank (**value !== ""**), then update or set the **value** for the **prop**.

If the **prop** is **"tracks"** and **value** is non-blank, push the **value** onto the end of the **tracks** array.

If **value** is blank, delete that **prop**.

Always return the entire collection object.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Waypoint: Accessing Objects Properties with Bracket Notation](http://www.freecodecamp.com/challenges/waypoint-accessing-objects-properties-with-bracket-notation)
- [Waypoint: Add New Properties to a JavaScript Object](http://www.freecodecamp.com/challenges/waypoint-add-new-properties-to-a-javascript-object)
- [Waypoint: Delete Properties from a JavaScript Object](http://www.freecodecamp.com/challenges/waypoint-delete-properties-from-a-javascript-object)
- [Waypoint: Accessing Nested Objects in JSON] ([http://www.freecodecamp.com/challenges/waypoint-accessing-nested-objects-in-json](http://www.freecodecamp.com/challenges/waypoint-accessing-nested-objects-in-json))

## Problem Explanation:
- Change the code below `// Only change code below this line` and up to `// Alter values below to test your code`
- Take note that you are editing the inside of the `update` function
- For the given `id` parameter, which is associated to the `collection` object:
  - If the `value` parameter isn't an empty string, update (or set) the `value` parameter for the `prop` parameter
  - If the `prop` parameter is equal to `"tracks"` and the `value` isn't an empty string, push the `value` onto the end of the `tracks` array
  - If `value` is an empty string, delete that `prop` from the object

- Finally, return the `collection` object

## Hint: 1
- Use an `else if` statement to check the needed steps.

## Hint: 2
- The second step listed in the instructions should be first in your `else if` statement.

## Hint: 3
- To access the value of a key in this object, you will use `collection[id][prop]`

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
// Setup
var collection = {
  2548: {
    album: "Slippery When Wet",
    artist: "Bon Jovi",
    tracks: [
      "Let It Rock",
      "You Give Love a Bad Name"
    ]
  },
  2468: {
    album: "1999",
    artist: "Prince",
    tracks: [
      "1999",
      "Little Red Corvette"
    ]
  },
  1245: {
    artist: "Robert Palmer",
    tracks: []
  },
  5439: {
    album: "ABBA Gold"
  }
};
// Keep a copy of the collection for tests
var collectionCopy = JSON.parse(JSON.stringify(collection));

// Only change code below this line
function update(id, prop, value) {
  if (value === '') {
    delete collection[id][prop];
  } else if (prop !== 'tracks') {
    collection[id][prop] = value;
  } else {
    collection[id][prop].push(value);
  }


  return collection;
}

// Alter values below to test your code
update(5439, "artist", "ABBA");
```

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
