# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Return the factorial of the provided integer.

If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.

Factorials are often represented with the shorthand notation n!

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120f`

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Arithmetic Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)

## Problem Script:

```js
function factorialize(num) {
  return num;
}

factorialize(5);
```

## Explanation:
This problem is very straightforward, yet it has two possible ways to get the solution.
1. `for` loops.
2. Recursion.

## Hint: 1
You need to take the number and multiply it for one less until you get to one.

## Hint: 2
You can use a for loop and have a variable store the product of the current value and one less than it.

## Hint: 3
Remember the control, the last number has to be `1` and the initial number should be minimum 2, if one then return it, otherwise handle the error.

## My code:

```js
function factorialize(num) {
  var factorial = 1;
  for (var n = 2; n <= num; n++) {
    factorial = factorial * n;
  }

  return factorial;
}
```

## My Code Explanation:
I decided to use the loop option. Because any number by one is the same number, we don't need to cover one. So we start with two and increase to the number, since the property of multiplication allows us to start in any order it works by multiplying the current number which is 1 by default by the value of n.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
