# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Lesson: Returning Boolean Values from Functions
You may recall from Comparison with the `Equality Operator` that all comparison operators return a boolean `true` or `false` value.

A common `anti-pattern` is to use an `if/else` statement to do a comparison and then return `true/false`:

```js
function isEqual(a,b) {
  if(a === b) {
    return true;
  } else {
    return false;
  }
}
```

Since `===` returns `true` or `false`, we can simply return the result of the comparison:

```js
function isEqual(a,b) {
  return a === b;
}
```
