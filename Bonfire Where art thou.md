# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Make a function that looks through an array (first argument) and returns an array of all objects that have equivalent property values (second argument).

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Global Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Object.hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
- [Object.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)

## Problem Script:

```
function where(collection, source) {
  var arr = [];
  // What's in a name?
  return arr;
}

where([{ first: 'Romeo', last: 'Montague' }, { first: 'Mercutio', last: null }, { first: 'Tybalt', last: 'Capulet' }], { last: 'Capulet' });
```

## Explanation:
We have to create a program that will take an array for the first argument and return the object that matches the properties on the second parameter. You will need to be familiar with objects a little bit.

## Hint: 1
Remember how to check for an element in a double array? `Array[index][subIndex]` That will be the first key.

## Hint: 2
You remember how to access properties using Bracket and dot notation? `Obj[key]` and `Obj.key` You will be using them together the the first hint to access the information.

## Hint: 3
The rest is to check if they are the same and add it to a variable to be returned at the end.

## My code:

```
function where(collection, source) {
  var arr = [];
  for (var ob in collection) {
    if (collection[ob][Object.keys(source)] === source[Object.keys(source)]) {
      arr.push(collection[ob]);
    }
  }
  return arr;
}
```

## My Code Explanation:
We first create an empty array, then go through the collection of objects and check if each of them has the same key that we are searchign for. If they do, then we push them to the array we created.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
