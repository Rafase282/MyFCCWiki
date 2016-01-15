# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Make Instances of Objects with a Constructor Function
A function that creates objects is called a _constructor_, my favorite way of creating objects when you have to create more than one of the same object. You can also edit the second object to add more properties if needed. This is called creating _instances_ of an object.

Each new instance of this object inherits all the properties and methods of your original object.

```js
var Car = function() {
   this.wheels = 4;
};

// New instance of Car object.
var myCar = new Car();

//Add the property "engines" to myCar, and make it a number.
myCar.engines = 1;
```
