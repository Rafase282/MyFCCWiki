# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Get JSON with the jQuery getJSON Method
Application Programming Interfaces - are tools that computers use to communicate with one another.

Most web APIs transfer data in a format called JSON. JSON stands for JavaScript Object Notation. JSON is nothing more than object properties and their current values, sandwiched between a `{` and a `}`.

These properties and their values are often referred to as "key-value pairs".

Here is a sample of what it looks like.

```js
$.getJSON("/json/cats.json", function(json) {

   $(".message").html(JSON.stringify(json));

 });
```
