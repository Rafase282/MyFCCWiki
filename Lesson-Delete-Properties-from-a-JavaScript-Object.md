# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Delete Properties from a JavaScript Object
We can also delete properties from objects like this:

```js
delete ourDog.bark;
```

The **delete operator** removes a property from an object.

### Syntax
`delete expression` where expression should evaluate to a property reference, e.g.:

```js
delete object.property
delete object['property']
```

### Parameters
**object**  The name of an object, or an expression evaluating to an object.

 **property**   The property to delete.

### Return value
Throws in [strict](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions_and_function_scope/Strict_mode) mode if the property is an own non-configurable property (returns false in non-strict). Returns true in all other cases.

[Read more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
