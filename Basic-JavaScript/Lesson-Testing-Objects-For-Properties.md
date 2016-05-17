# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Lesson: Testing Objects for Properties
Sometimes it is useful to check if the property of a given object exists or not. We can use the `.hasOwnProperty([propname])` method of objects to determine if that object has the given property name. `.hasOwnProperty()` returns _true_ or _false_ if the property is found or not.

## Example

```js
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle");
```
