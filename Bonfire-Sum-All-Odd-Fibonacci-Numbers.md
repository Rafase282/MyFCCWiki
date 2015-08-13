# Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128) submitted by Rafase282 | https://github.com/Rafase282

* FreeCodeCamp Profile: http://www.freecodecamp.com/rafase282
* CodePed Profile: http://codepen.io/Rafase282/
* LinkedIn: https://www.linkedin.com/in/rafase282

# [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details

* Difficulty: 2/5

Return the sum of all odd Fibonacci numbers up to and including the passed number if it is a Fibonacci number.
The first few numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8, and each subsequent number is the sum of the previous two numbers.
As an example, passing 4 to the function should return 5 because all the odd Fibonacci numbers under
4 are 1, 1, and 3.

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links

* [Remainder](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder_(.25))
* [Fibonacci Numbers](https://en.wikipedia.org/wiki/Fibonacci_number)

# Problem Script:
```
function sumFibs(num) {
  return num;
}

sumFibs(4);
```

## Explanation:

You will need to gather all the **Fibonacci** numbers and then check for the odd ones. Once you get the odd ones then you will add them all. The last number should be the number given as a parameter if it actually happens to be an off Fibonacci number.

## Hint: 1
Soon

## Hint: 2
Soon

## Hint: 3
Soon

## My code:

```
function sumFibs(num) {
	// Create variable to keep Record
    var prevNumber = 0;
    var currNumber = 1;
    var result = 0;
    // Makes sure we do not go over the original number
    while (currNumber <= num) {
    	// CHecks for odd fibonacci numbers
        if (currNumber % 2 !== 0) {
        	// Add them to the return variable
            result += currNumber;
        }
        // Complete the fibonnaci circle by rotating values.
        var added = currNumber + prevNumber;
        prevNumber = currNumber;
        currNumber = added;
    }
    
    return result;
}
```

## My Code Explanation:

* Soon
