# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Details
- Difficulty: 4/5

Design a cash register drawer function that accepts purchase price as the first argument, payment as the second argument, and cash-in-drawer (cid) as the third argument.

cid is a 2d array listing available currency.

Return the string "Insufficient Funds" if cash-in-drawer is less than the change due. Return the string "Closed" if cash-in-drawer is equal to the change due.

Otherwise, return change in coin and bills, sorted in highest to lowest order.

Remember to use [ Read-Search-Ask](http://github.com/FreeCodeCamp/freecodecamp/wiki/How-to-get-help-when-you-get-stuck) if you get stuck. Try to pair program. Write your own code.

## Useful Links
- [Global Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

## Problem Script:

```js
function drawer(price, cash, cid) {
  var change;
  // Here is your change, ma'am.
  return change;
}

// Example cash-in-drawer array:
// [['PENNY', 1.01],
// ['NICKEL', 2.05],
// ['DIME', 3.10],
// ['QUARTER', 4.25],
// ['ONE', 90.00],
// ['FIVE', 55.00],
// ['TEN', 20.00],
// ['TWENTY', 60.00],
// ['ONE HUNDRED', 100.00]]

drawer(19.50, 20.00, [['PENNY', 1.01], ['NICKEL', 2.05], ['DIME', 3.10], ['QUARTER', 4.25], ['ONE', 90.00], ['FIVE', 55.00], ['TEN', 20.00], ['TWENTY', 60.00], ['ONE HUNDRED', 100.00]]);
```

## Problem Explanation:
- You have to create a program that will handle when the register does not have enough cash or will have no cash after the transaction. Other than that it needs to return an array of the change in the form of an array, so that will be a 2D array.

## Hint: 1
- Is easier to handle if you will have to close the register or if you will not have enough money to complete the transaction if you know beforehand how much money is on your register. For this it would be recommended to have a function get the information assigned to a variable.

## Hint: 2
- Life is easier when you get to know the value of each currency type in the register instead of how much money is composed of that particular currency. So be sure to watch out for that.

## Hint: 3
- You will have to get as much change from one type before moving to the next from greater value to lesser, and keep going until you have covered the whole change.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function drawer(price, cash, cid) {

  // Total Amount to return to client
  var totalChange = +(cash - price).toFixed(2);

  //Standard currency Value
  var stdCurr = [0.01, 0.05, 0.10, 0.25, 1, 5, 10, 20, 100];

  //Name of current currency
  var currType;

  // How many of the current standard currency
  var stdCurrAmount;
  var currCurrency;

  // Change to be returned in proper format.
  var changeArr = [];

  var totalCash = +cid.map(function(money) {
    // Gets 1D array of values
    return money[1];
  }).reduce(function(cash1, cash2) {
    // Reduces the values to one number
    return cash1 + cash2;

    // Rounds to two decimal places
  }).toFixed(2);

  // Handle the case where we don't have enough money or will be left without money.
  if (totalChange > totalCash) {
    return 'Insufficient Funds';
  } else if (totalChange === totalCash) {
    return 'Closed';
  }

  // Loops array from right to left.
  for (var i = +cid.length - 1; i >= 0; i--) {
    // Gets the monetary value of the current array and the type.
    currCurrency = +cid[i][1].toFixed(2);
    currType = cid[i][0];

    //If the currency is less than the change left to hand then get the right amount from the current type of change.
    if (+stdCurr[i].toFixed(2) <= +totalChange.toFixed(2)) {

      stdCurrAmount = Math.floor(currCurrency / stdCurr[i]);

      if ((stdCurr[i] * stdCurrAmount) >= totalChange) {
        stdCurrAmount = Math.floor(totalChange / stdCurr[i]);
      }

      //Get the current currency to use and udate the amount left to hand out.
      currCurrency = +(stdCurr[i] * stdCurrAmount).toFixed(2);
      totalChange = +(totalChange - currCurrency).toFixed(2);

      // Update the values so we always have the current amount left in the register.
      cid[i][1] = currCurrency;

      //Push the change right change to hand out
      changeArr.push([currType, currCurrency]);
    }
  }

  return changeArr;
};
```

# Code Explanation:
- Read comments in code.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)
