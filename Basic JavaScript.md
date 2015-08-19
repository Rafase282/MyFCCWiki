# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128) Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Comment your JavaScript Code
Comments are a great way to leave notes to yourself and to other people who will later need to figure out what it does. Any code in it will be ignored.

Let's take a look at the two ways you can write comments in JavaScript.
- The double-slash comment will comment out the remainder of the text on the current line:

`// This is a comment.`
- The slash-star-star-slash comment will comment out everything between the `/*` and the `*/` characters:

`/* This is also a comment */`

## Understand Boolean Values
Booleans can only hold the value of either true or false. They are basically little on-off switches.

## Declare JavaScript Variables
When we store data in a data structure, we call it a variable. JavaScript variables are written in **camel case**. An example of camel case is: `camelCase`.

You can declare a variable this way `var myName = "Rafael";`

## Declare String Variables
A String variable. It is nothing more than a "string" of characters. JavaScript strings are always wrapped in quotes.

`var myFirstName = 'Rafael';`

## Check the Length Property of a String Variable
Data structures have properties. For example, strings have a property called .length that will tell you how many characters are in the string.

`lastNameLength = lastName.length;`

## Use Bracket Notation to Find the First Character in a String
Bracket notation is a way to get a character at a specific index within a string.

Computers don't start counting at 1 like humans do. They start at 0. `firstLetterOfLastName = lastName[0];`

## Use Bracket Notation to Find the Nth Character in a String
You can also use bracket Notationto get the character at other positions within a string.

Remember that computers start counting at 0, so the first character is actually the zeroth character.

`var thirdLetterOfLastName = lastName[2];`

## Use Bracket Notation to Find the Last Character in a String
In order to get the last letter of a string, you can subtract one from the string's length.

For example, if `var firstName = "Charles"`, you can get the value of the last letter of the string by using `firstName[firstName.length - 1]`.

`var lastLetterOfLastName = lastName[lastName.length -1];`

## Use Bracket Notation to Find the Nth-to-Last Character in a String
You can get the value of the third-to-last letter of the `var firstName = "Charles"` string by using `firstName[firstName.length - 3]`.

## Add Two Numbers with JavaScript
JavaScript uses the + symbol for addition. It can also be used instead of **parseInt()** but that is beyond this.

`var sum = 10 + 10;`

## Subtract One Number from Another with JavaScript
We can also subtract one number from another.

JavaScript uses use the - symbol for subtraction. `var difference = 45 - 33;`

## Multiply Two Numbers with JavaScript
JavaScript uses use the * symbol for multiplication.

`var product = 8 * 10;`

## Divide One Number by Another with JavaScript
JavaScript uses use the / symbol for division. `var quotient = 66 / 33;`

## Create Decimal Numbers with JavaScript
JavaScript number variables can also have decimals. `var myDecimal = 2.8;`

## Perform Arithmetic Operations on Decimals with JavaScript
In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

`var quotient = 4.4 / 2.0; // equals 2.2`

## Store Multiple Values in one Variable using JavaScript Arrays
With JavaScript array variables, we can store several pieces of data in one place.

You start an array declaration with an opening bracket, end it with a closing bracket, and put a comma between each entry, like this: `var sandwich = ["peanut butter", "jelly", "bread"]`.

`myArray = [2,'j'];`

## Nest one Array within Another Array
You can also nest arrays within other arrays, like this:`[["Bulls", 43]]`.

## Access Array Data with Indexes
We can access the data inside arrays using indexes.

Array indexes are written in the same bracket notation that strings use, except that instead of specifying a character, they are specifying an entry in the array.

For example:

```
var array = [1,2,3];
array[0]; //equals 1
var data = array[1];
```

## Modify Array Data With Indexes
We can also modify the data stored in arrays by using indexes.

For example:

```
var ourArray = [3,2,1];
ourArray[0] = 1; // equals [1,2,1]
```

## Manipulate Arrays With pop()
Another way to change the data in an array is with the **.pop()** function.

.pop()is used to "pop" a value off of the end of an array. We can retrieve this value by performing pop() in a variable declaration.

Any type of variable can be "popped" off of an array.

## Manipulate Arrays With push()
Not only can you pop() data off of the end of an array, you can also **push()** data onto the end of an array.

`myArray.push(["dog", 3]);`

## Manipulate Arrays With shift()
**shift()** removes the first element unlike **pop()** which removes the last.

## Manipulate Arrays With unshift()
`myArray.unshift('Paul');` Basically you call unshift and pass what was deleted.

## Write Reusable JavaScript with Functions
In JavaScript, we can divide up our code into reusable parts called functions.

Here's an example of a function:

```
function functionName (a, b) {
  return(a + b);
}
```

We can "call" our function like this: functionName();, and it will run and return it's return value to us.

## Build JavaScript Objects
Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.

Here's a sample object:

```
var cat = {
 "name": "Whiskers",
 "legs": 4,
 "tails": 1,
 "enemies": ["Water", "Dogs"]
};
```

Objects are useful for storing data in a structured way, and can represents real world objects, like a cats.

## Manipulate JavaScript Objects
We can add properties to objects like this:

`myObject.myProperty = "myValue";`

We can also delete them like this:

`delete(myObject.myProperty);`

## Iterate with JavaScript For Loops
The most common type of JavaScript loop is called a "for loop" because it runs "for" a specific number of times.

```
var ourArray = [];
for(var i = 0; i < 5; i++) {
  ourArray.push(i);
}
```

ourArray will now contain [0,1,2,3,4]

## Iterate with JavaScript While Loops
Another type of JavaScript loop is called a "while loop" because it runs "while" something is true, and stops once that something is no longer true.

```
var ourArray = [];
var i = 0;
while(i < 5) {
  ourArray.push(i);
  i++;
}
```

## Generate Random Fractions with JavaScript
## Generate Random Whole Numbers with JavaScript
## Generate Random Whole Numbers within a Range
## Use Conditional Logic with If-Else Statements
## Sift through Text with Regular Expressions
## Find Numbers with Regular Expressions
## Find White Space with Regular Expressions
## Invert Regular Expression Matches with JavaScript
## Create a JavaScript Slot Machine
## Add your JavaScript Slot Machine Slots
## Bring your JavaScript Slot Machine to Life
## Give your JavaScript Slot Machine some stylish images
