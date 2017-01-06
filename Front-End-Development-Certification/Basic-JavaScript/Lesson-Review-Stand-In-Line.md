# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Details

Code by Rafase282, the rest of the information by Carole Anne.
**_About queues_**

In Computer Science a **queue** is an abstract _Data Structure_ where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the _queue_.

**_Instructions_**

Write a function queue which takes an "array" and an "item" as arguments.

Add the item onto the end of the array, then remove the first element of the array.

The queue function should return the element that was removed.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Lesson: Manipulate Arrays With push()](http://www.freecodecamp.com/challenges/manipulate-arrays-with-push)
- [Lesson: Manipulate Arrays With shift()](http://www.freecodecamp.com/challenges/manipulate-arrays-with-shift)
- [Lesson: Passing Values to Functions with Arguments](http://www.freecodecamp.com/challenges/passing-values-to-functions-with-arguments)

## Problem Explanation:
- Change the code below `//Your Code here` and up to `//Change this line`
- Take note that you are editing the inside of the queue function
- Use an array function you learned to add the `item` to the end of the array `arr`
- Use an array function you learned to remove the first element from array `arr`
- Return the element removed

## Hint: 1
- `push` adds an item to the end of an array.

## Hint: 2
- `shift` removes the first element of an array. It also gives that element back to you.

## Hint: 3
- The function queue uses `arr` and `item`. Those are what the tests will use to pass the arrays and elements they will test with and allows the function to be reusable. Do not hardcode any of the tests inside the function.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function queue(arr, item) {
  // Your code here
  arr.push(item);
  return arr.shift();;  // Change this line
}
```

# Code Explanation:
- Pushes item at the end of arr
- Calls shift on arr to get the first item and stores it in removed
- Returns removed

**_Example Run_**
- Test `queue([2], 1);` runs
- The `queue` function is called. `arr` becomes [2]. `item` becomes 1.
- `arr.push(item);` Pushes 1 to [2]. So `arr` is now [2,1]
- `var removed = arr.shift();` Removes the first element. So `arr` is now [1]. 2 has been removed and is stored in `removed`
- `return removed;` 2 is returned

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
