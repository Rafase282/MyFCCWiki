# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

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
When we store data in a data structure, we call it a variable. JavaScript variables are written in `camel case`. An example of camel case is: `camelCase`.

You can declare a variable this way `var myName = "Rafael";`

## Declare String Variables
A String variable. It is nothing more than a "string" of characters. JavaScript strings are always wrapped in quotes.

`var myFirstName = 'Rafael';`

## Check the Length Property of a String Variable
Data structures have properties. For example, strings have a property called `.length` that will tell you how many characters are in the string.

`lastNameLength = lastName.length;`

## Use Bracket Notation to Find the First Character in a String
Bracket notation is a way to get a character at a specific index within a string.

Computers don't start counting at `1` like humans do. They start at `0`. `firstLetterOfLastName = lastName[0];`

## Use Bracket Notation to Find the Nth Character in a String
You can also use bracket notation to get the character at other positions within a string.

Remember that computers start counting at `0`, so the first character is actually the zeroth character.

`var thirdLetterOfLastName = lastName[2];`

## Use Bracket Notation to Find the Last Character in a String
In order to get the last letter of a string, you can subtract one from the string's length.

For example, if `var firstName = "Charles"`, you can get the value of the last letter of the string by using `firstName[firstName.length - 1]`.

`var lastLetterOfLastName = lastName[lastName.length -1];`

## Use Bracket Notation to Find the Nth-to-Last Character in a String
You can get the value of the third-to-last letter of the `var firstName = "Charles"` string by using `firstName[firstName.length - 3]`.

## Add Two Numbers with JavaScript
JavaScript uses the `+` symbol for addition. It can also be used instead of `parseInt()` but that is beyond this.

`var sum = 10 + 10;`

## Subtract One Number from Another with JavaScript
We can also subtract one number from another.

JavaScript uses use the - symbol for subtraction. `var difference = 45 - 33;`

## Multiply Two Numbers with JavaScript
JavaScript uses use the `*` symbol for multiplication.

`var product = 8 * 10;`

## Divide One Number by Another with JavaScript
JavaScript uses use the `/` symbol for division. `var quotient = 66 / 33;`

## Create Decimal Numbers with JavaScript
JavaScript number variables can have decimals. `var myDecimal = 2.8;`

## Perform Arithmetic Operations on Decimals with JavaScript
In JavaScript, you can perform calculations with decimal numbers, just like whole numbers.

`var quotient = 4.4 / 2.0; // equals 2.2`

## Store Multiple Values in one Variable using JavaScript Arrays
With JavaScript array variables, we can store several pieces of data in one place.

You start an array declaration with an opening bracket, end it with a closing bracket, and put a comma between each entry, like this: `var sandwich = ["peanut butter", "jelly", "bread"]`.

`myArray = [2,'j'];`

## Nest one Array within Another Array
You can nest arrays within other arrays, like this:`[["Bulls", 43]]`.

## Access Array Data with Indexes
We can access the data inside arrays using indexes.

Array indexes are written in the same bracket notation that strings use, except that instead of specifying a character, they are specifying an entry in the array.

For example:

```js
var array = [1,2,3];
array[0]; //equals 1
var data = array[1];
```

## Modify Array Data With Indexes
We can also modify the data stored in arrays by using indexes.

For example:

```js
var ourArray = [3,2,1];
ourArray[0] = 1; // equals [1,2,1]
```

## Manipulate Arrays With pop()
Another way to change the data in an array is with the `.pop()` function.

`.pop()` is used to "pop" a value off of the end of an array. We can retrieve this value by performing `pop()` in a variable declaration.

Any type of variable can be "popped" off of an array.

## Manipulate Arrays With push()
Not only can you `pop()` data off of the end of an array, you can also `push()` data onto the end of an array.

`myArray.push(["dog", 3]);`

## Manipulate Arrays With shift()
`shift()` removes the first element unlike `pop()` which removes the last.

## Manipulate Arrays With unshift()
`myArray.unshift('Paul');` Basically you call `unshift` and pass what was deleted.

## Write Reusable JavaScript with Functions
In JavaScript, we can divide up our code into reusable parts called functions.

Here's an example of a function:

```js
function functionName (a, b) {
  return(a + b);
}
```

We can "call" our function like this: `functionName();`, and it will run and return it's return value to us.

## Build JavaScript Objects
Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.

Here's a sample object:

```js
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
The most common type of JavaScript loop is called a `for loop` because it runs `for` a specific number of times.

```js
var ourArray = [];
for(var i = 0; i < 5; i++) {
  ourArray.push(i);
}
```

ourArray will now contain [0,1,2,3,4]

## Iterate with JavaScript While Loops
Another type of JavaScript loop is called a `while loop` because it runs `while` something is true, and stops once that something is no longer true.

```js
var ourArray = [];
var i = 0;
while(i < 5) {
  ourArray.push(i);
  i++;
}
```

## Generate Random Fractions with JavaScript
JavaScript has a `Math.random()` function that generates a random decimal number.

## Generate Random Whole Numbers with JavaScript
It's great that we can create random decimal numbers, but it's even more useful if we lot more useful to generate a random whole number.

To achieve this we can multiply the random number by ten and use the `Math.floor()` to convert the decimal number to a whole number

`return(Math.floor(Math.random()*10));`

## Generate Random Whole Numbers within a Range
We can use a certain mathematical expression to get a random number between two numbers.

`Math.floor(Math.random() * (max - min + 1)) + min`

By using this we can control the output of a random number.

## Use Conditional Logic with If-Else Statements
We can use if statements in JavaScript to only execute code if a certain condition is met.

if statements require some sort of `boolean` condition evaluate.

```js
Example:

 if (1 == 2) {
  return(true);
}
else {
  return(false);
}
```

## Sift through Text with Regular Expressions
`Regular expressions` are used to find certain words or patterns inside of strings.

Regular expressions are usually surrounded by `/` symbols.

For example, if we wanted to find the number of times the word the occurred in the string The dog chased the cat, we could use the following regular expression: `/the+/gi`

Let's break this down a bit:

the is the pattern we want to match.
- `+` means we want to find one or more occurrences of this pattern.
- `g` means that we want to search the entire string for this pattern.
- `i` means that we want to ignore the case (uppercase or lowercase) when searching for the pattern.

## Find Numbers with Regular Expressions
We can use special selectors in Regular Expressions to select a particular type of value.

One such selector is the digit selector `\d` which is used to grab the numbers in a string.

It is used like this: `/\d+/g`.

## Find White Space with Regular Expressions
We can also use selectors like`\s` to find spaces in a string.

It is used like this:

`/\s+/g`

## Invert Regular Expression Matches with JavaScript
Use`/\S/gi`; to match everything that isn't a space in the string.

You can invert any match by using the uppercase version of the selector `\s` versus `\S` for example.

## Create a JavaScript Slot Machine
For this we have to generate three random numbers using the formula they give us and not the general one. `Math.floor(Math.random() * (3 - 1 + 1)) + 1;`

```js
slotOne = Math.floor(Math.random() * (3 - 1 + 1)) + 1;
slotTwo = Math.floor(Math.random() * (3 - 1 + 1)) + 1;
slotThree = Math.floor(Math.random() * (3 - 1 + 1)) + 1;
```

## Add your JavaScript Slot Machine Slots
For this part we should notify if they same number is returned three times or return `null` otherwise.

```js
if(slotOne !== slotTwo || slotTwo !== slotThree){
      return (null);
    }
```

If slot one and to are different, or slot two and three are not the same, then return `null`.

## Bring your JavaScript Slot Machine to Life
Let's use the jQuery selector `$(".slot")` to select all of the slots.

Once they are all selected, we can use bracket notation to access each individual slot:

```js
$($(".slot")[0]).html(slotOne);
$($(".slot")[1]).html(slotTwo);
$($(".slot")[2]).html(slotThree);
```

## Give your JavaScript Slot Machine some stylish images
We've already set up the images for you in an array called images. We can use different indexes to grab each of these.

Here's how we would set the first slot to show a different image depending on which number its random number generates:

`$($('.slot')[0]).html('<img src = "' + images[slotOne-1] + '">');`

```html
<script>
  function runSlots(){
    var slotOne;
    var slotTwo;
    var slotThree;

    var images = ["http://i.imgur.com/9H17QFk.png", "http://i.imgur.com/9RmpXTy.png", "http://i.imgur.com/VJnmtt5.png"];

    slotOne = Math.floor(Math.random() * (3 - 1 + 1)) + 1;
    slotTwo = Math.floor(Math.random() * (3 - 1 + 1)) + 1;
    slotThree = Math.floor(Math.random() * (3 - 1 + 1)) + 1;

    $('.logger').html('');
    $('.logger').html('Not A Win');

    // Only change code below this line.
    $($('.slot')[0]).html('<img src = "' + images[slotOne-1] + '">');
    $($('.slot')[1]).html('<img src = "' + images[slotTwo-1] + '">');
    $($('.slot')[2]).html('<img src = "' + images[slotThree-1] + '">');


    // Only change code above this line.

    if(slotOne !== slotTwo || slotTwo !== slotThree){
      return(null);
    }

    if(slotOne !== undefined && slotTwo !== undefined && slotThree !== undefined){
      $('.logger').html(slotOne);
      $('.logger').append(' ' + slotTwo);
      $('.logger').append(' ' + slotThree);
    }

    return([slotOne, slotTwo, slotThree]);
  }

  $(document).ready(function(){
     $('.go').click(function(){
       runSlots();
     });
   });
</script>

<div>
 <div class = 'container inset'>
   <div class = 'header inset'>
     <img src='https://s3.amazonaws.com/freecodecamp/freecodecamp_logo.svg.gz' alt='learn to code javascript at Free Code Camp logo' class='img-responsive nav-logo'>
     <h2>FCC Slot Machine</h2>
   </div>
   <div class = 'slots inset'>
     <div class = 'slot inset'>

     </div>
     <div class = 'slot inset'>

     </div>
     <div class = 'slot inset'>

     </div>
   </div>
   <br/>
   <div class = 'outset'>
     <button class = 'go inset'>
       Go
     </button>
   </div>
   <br/>
   <div class = 'foot inset'>
     <span class = 'logger'></span>
   </div>
 </div>
</div>

<style>
 .slot > img {
  margin: 0!important;
  height: 71px;
  width: 50px;
 }
 .container {
   background-color: #4a2b0f;
   height: 400px;
   width: 260px;
   margin: 50px auto;
   border-radius: 4px;
 }
 .header {
   border: 2px solid #fff;
   border-radius: 4px;
   height: 55px;
   margin: 14px auto;
   background-color: #457f86
 }
 .header h2 {
   height: 30px;
   margin: auto;
 }
 .header h2 {
   font-size: 14px;
   margin: 0 0;
   padding: 0;
   color: #fff;
   text-align: center;
 }
 .slots{
   display: flex;
   background-color: #457f86;
   border-radius: 6px;
   border: 2px solid #fff;
 }
 .slot{
   flex: 1 0 auto;
   background: white;
   height: 75px;
   width: 50px;
   margin: 8px;
   border: 2px solid #215f1e;
   border-radius: 4px;
   text-align: center;
 }
 .go {
   width: 100%;
   color: #fff;
   background-color: #457f86;
   border: 2px solid #fff;
   border-radius: 2px;
   box-sizing: none;
   outline: none!important;
 }
 .foot {
   height: 150px;
   background-color: 457f86;
   border: 2px solid #fff;
 }

 .logger {
   color: white;
   margin: 10px;
 }

 .outset {
   -webkit-box-shadow: 0px 0px 15px -2px rgba(0,0,0,0.75);
   -moz-box-shadow: 0px 0px 15px -2px rgba(0,0,0,0.75);
     box-shadow: 0px 0px 15px -2px rgba(0,0,0,0.75);
 }

 .inset {
   -webkit-box-shadow: inset 0px 0px 15px -2px rgba(0,0,0,0.75);
   -moz-box-shadow: inset 0px 0px 15px -2px rgba(0,0,0,0.75);
   box-shadow: inset 0px 0px 15px -2px rgba(0,0,0,0.75);
 }
</style>
```
