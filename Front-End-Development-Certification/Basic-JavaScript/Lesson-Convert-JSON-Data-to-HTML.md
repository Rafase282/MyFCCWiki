# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Convert JSON Data to HTML
Once you know how to get data from the JSON call then is time to learn how to iterate through it. We can use the .map() method to loop through our data and modify our HTML elements.

Here is a code that does that:

```js
// calling map on the json variable and using a custom callback function.
json.map(function(val) {

  // Adding each object keys
  var keys = Object.keys(val);
  // Generating new html
  html += "<div class = 'cat'>";
  // Adding the custom html to each key
  keys.map(function(key) {

    html += "<b>" + key + "</b>: " + val[key] + "<br>";

  });

  html += "</div><br>";

});
```
