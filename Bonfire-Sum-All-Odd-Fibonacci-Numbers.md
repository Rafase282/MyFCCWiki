# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) |  [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details
- Difficulty: 2/5

Return the sum of all odd Fibonacci numbers up to and including the passed number if it is a Fibonacci number. The first few numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8, and each subsequent number is the sum of the previous two numbers. As an example, passing 4 to the function should return 5 because all the odd Fibonacci numbers under 4 are 1, 1, and 3.

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links
- [Remainder](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder_(.25))
- [Fibonacci Numbers](https://en.wikipedia.org/wiki/Fibonacci_number)

# Problem Script:

```js
function sumFibs(num) {
  return num;
}

sumFibs(4);
```

## Explanation:
You will need to gather all the **Fibonacci** numbers and then check for the odd ones. Once you get the odd ones then you will add them all. The last number should be the number given as a parameter if it actually happens to be an off Fibonacci number.

## Hint: 1
To get the next number of the series, you need to add the current one to the previous and that will give you the next one.

## Hint: 2
To check if a number is even all you have to check is if that number % 2 == 0.

## Hint: 3
As you get the next odd one, don't forget to add it to a global variable that can be returned at the end. `result += currNumber;` Will do the trick.

## My code:

```js
function sumFibs(num) {
    var prevNumber = 0;
    var currNumber = 1;
    var result = 0;
    while (currNumber <= num) {
        if (currNumber % 2 !== 0) {
            result += currNumber;
        }
        var added = currNumber + prevNumber;
        prevNumber = currNumber;
        currNumber = added;
    }

    return result;
}
```

## My Code Explanation:
- Create a variable to keep record of the current and previous numbers along with the result that will be returned.
- Use a while loop to make sure we do not go over the number given as parameter.
- We use the modulo operand to check if the current number is odd or even. If even add it to the result.
- Complete the Fibonacci circle by rotating getting the next number and swapping values after.
- Return the result.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
