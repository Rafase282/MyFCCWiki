# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Lesson: Comparison with the Equality Operator
There are many `Comparison Operators` in JavaScript. All of these operators return a boolean `true` or `false` value.

The most basic operator is the equality operator `==`. The equality operator compares two values and returns `true` if they're equivalent or `false` if they are not. Note that equality is different from assignment (=), which assigns the value at the right of the operator to a variable in the left.

## Example

```js
function equalityTest(myVal) {
  if (myVal == 10) {
     return "Equal";
  }
  return "Not Equal";
}
```

If `myVal` is equal to `10`, the function will return "Equal". If it is not, the function will return "Not Equal".

The equality operator will do its best to convert values for comparison.

## Example

```js
   1   ==  1        // true
  "1"  ==  1        // true
   1   == '1'       // true
   0   == false     // true
   0   == null      // false
   0   == undefined // false
 null  == undefined // true
```
