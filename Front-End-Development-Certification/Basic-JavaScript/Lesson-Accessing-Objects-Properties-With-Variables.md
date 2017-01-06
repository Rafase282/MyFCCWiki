# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Lesson: Accessing Objects Properties with Variables
Another use of bracket notation on objects is to use a variable to access a property. This can be very useful for iterating through lists of the object properties or for doing the lookup.

Here is an example of using a variable to access a property:

```js
var someProp = "propName";
var myObj = {
  propName: "Some Value"
}
```

`myObj[someProp]; // "Some Value"` **Note** that we do not use quotes around the variable name when using it to access the property because we are using the value of the variable, not the name
