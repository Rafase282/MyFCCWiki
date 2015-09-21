# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

Remember, you can iterate through an array with a simple for loop, and access each member with array syntax arr[i] .

If you are writing your own Chai.js tests, be sure to use a deep equal statement instead of an equal statement when comparing arrays.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

## Problem Script:

```js
function largestOfFour(arr) {
  // You can do this!
  return arr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

## Explanation:
You will get an array that contains sub arrays of numbers and you need to return an array with the largest number from each of the sub arrays.

## Hint: 1
You will need to keep track of the array with the answer and the largest number of each sub-array.

## Hint: 2
You can work with multidimensional arrays by `Array[Index][SubIndex]`

## Hint: 3
Pay close attention to the timing of the storing of variables when working with loops

## My code:

```js
function largestOfFour(arr) {
  var results = [];
  for (var n in arr) {
      var largestNumber = 0;
      for (var sb in arr[n]) {
          if (arr[n][sb] > largestNumber) {
              largestNumber = arr[n][sb];
          }
      }
    results[n] = largestNumber;
}
  return results;
}
```

## My Code Explanation:
- Create a variable to store the results as an array.
- Create an outer loop to iterate through the main array.
- Before going into the inner loop, create a variable to hold the largest number. This must be outside the inner loop.
- Create another for loop to work with the sub-arrays.
- Check if the element of the sub array is larger than the current largest number. If so, then save the number.
- After the inner loop, save the largest number in the variable for the results.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
