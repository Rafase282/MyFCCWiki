# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) |  [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details
- Difficulty: 2/5

Find the smallest number that is evenly divisible by all numbers in the provided range.

The range will be an array of two numbers that will not necessarily be in numerical order.

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links
- [Smallest Common Multiple](https://www.mathsisfun.com/least-common-multiple.html)

# Problem Script:

```js
function smallestCommons(arr) {
  return arr;
}


smallestCommons([1,5]);
```

## Explanation:
This particular problem can be confusing because most people look for the smallest common multiple of the two number but forget the keyword **range.** This means that if you get `[1,5]` then you have to check for the smallest common multiple for all these numbers [1,2,3,4,5] that is evenly divisible by all of them.

## Hint: 1
Create an array with all the numbers that are missing from the original array to make it easier to check when having to check for even division.

## Hint: 2
You can use modulo `%` to check if the reminder is 0, which means it is evenly divisible.

## Hint: 3
If you sort the array from greater to lowest then you can check for the first two numbers as it is more likely to the the smallest common multiple than the lower numbers.

## My code:

```js
function smallestCommons(arr) {
  // Sort array from greater to lowest
  // This line of code was from Adam Doyle (http://github.com/Adoyle2014)
  arr.sort(function(a, b) {
    return b - a;
  });

  // Create new array and add all values from greater to smaller from the original array.
  var newArr = [];
  for (var i = arr[0]; i >= arr[1]; i--) {
    newArr.push(i);
  }

  // Variables needed declared outside the loops.
  var quot = 0;
  var loop = 1;
  var n;

  // run code while n is not the same as the array lenght.
  do {
    quot = newArr[0] * loop * newArr[1];
    for (n = 2; n < newArr.length; n++) {
      if (quot % newArr[n] !== 0) {
        break;
      }
    }

    loop++;
  } while (n !== newArr.length);

  return quot;
}

smallestCommons([1, 13]);
```

## My Code Explanation:
- Because the possibility of the smallest common denominator being among the two biggest numbers, it makes sense to check those first, so sort the array.
- Create a new array to sore all the numbers.
- Use a descending for loop to add the numbers from the biggest to the smallest in the new array.
- Declare the variables for the quotient, the number of loops and the variable that we will use in a for loop on another scope, this will allow us access outside the loop.
- Use a do while loop to check what we need while **n** is not the same length as the new array.
- In the **do** part, we are going to multiply the very first number, times the number of loops, times the second number.
- The loop part will allows us to increase the number beyond the greatest number we have without having to change the algorithm.
- We enter a for loop that will go from n being 2 and going up by one while it is smaller than the array with all the numbers.
- If the quotient is not even then stop the loop. If it is even then it check for the next elements in the array until it is not even or we find our answer.
- Outside the loop, increase the value of loop.
- At the end of the loop return the quotient.

If the array only has two elements then the for loop never gets used and the return value is the product of said numbers. Otherwise, from the third element and until n is the same and the array length check if the reminder of the quotient and the third value of the array is not 0, if it is not 0 then stop loop increases and then we start over. If the reminded was 0 then keep checking until the end of the array.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
