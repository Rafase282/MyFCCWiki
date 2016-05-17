# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Make Unique Objects by Passing Parameters to our Constructor
When you have a constructor but don't want to keep creating the same object, all you have to do is add parameters to the constructor the following way:

```js
var Car = function(wheels, seats, engines) {

  this.wheels = wheels;

  this.seats = seats;

  this.engines = engines;

};
```

Now you can pass in arguments when you call the constructor. `var myCar = new Car(6, 3, 1);`

This will result in:

```js
{

  wheels: 6,

  seats: 3,

  engines: 1

}
```
