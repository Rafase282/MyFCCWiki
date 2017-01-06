# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Use Conditional Logic with If-Else Statements
We can use if statements in JavaScript to only execute code if a certain condition is met.

Each if statement requires a `boolean` condition to evaluate. If the _boolean_ evaluates to `true`, the statements inside the curly braces will execute. Otherwise, if it evaluates to `false`, the code will not execute.

Example:

```js
function test(myVal) {
  if (myVal > 10) {
     return "Greater Than";
  }
  return "Not Greater Than";
}
```

If `myVal` is greater than 10, the function will return "Greater Than". If it is not, the function will return "Not Greater Than".

Furthermore, if you add an `else` statement you can have it do something different in case that `myVal` is equal or less than 10 inthe following way:

```js
function test(myVal) {
  if (myVal > 10) {
     return "Greater Than";
  } else {
    // do something else
  }
  return "Not Greater Than";
}
```

You could take it even further and use an `else-if` and then another `else` for nesting once you are more familiar with conditions.

```js
if (true) {
  // do something
}else if (true) {
  // otherwise check this and do that
}else {
  // otherwise do this instead
}

//consitune with more code here
```
