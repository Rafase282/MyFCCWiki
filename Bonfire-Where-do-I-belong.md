# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 1/5

Return the lowest index at which a value (second argument) should be inserted into a sorted array (first argument).

For example, where([1,2,3,4], 1.5) should return 1 because it is greater than 1 (0th index), but less than 2 (1st index).

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Array.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

## Problem Script:

```js
function where(arr, num) {
  // Find my place in this sorted array.
  return num;
}

where([40, 60], 50);
```

## Explanation:
This can be a tricky problem to understand. You need to find where in the array a number should be inserted by order, and return the index where it should go.

## Hint: 1
The first thing to do is sort the array from lower to bigger, just to make the code easier. This is where sort comes in, it needs a callback function so you have to create it.

## Hint: 2
Once the array is sorted, then just check for the first number that is bigger and return the index.

## Hint: 3
If there is no index for that number then you will have to deal with that case too.

## My code:

```js
function where(arr, num) {
    arr.sort(function(a, b) {
        return a - b;
        });
    for (var a in arr){
        if (arr[a] >= num)
            return parseInt(a);
    }
    return arr.length;
}
```

## My Code Explanation:
- First I sort the array using `.sort(callbackFuntion)` to sort it by lowest to highest, from left to right.
- Then I use a for loop to compare the items in the array starting from the smallest one. When an item on the array is greater than the number we are comparing against, then we return the index as an integer.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
