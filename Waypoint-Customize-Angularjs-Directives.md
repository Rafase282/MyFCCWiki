# How to build Custom Directives
To declutter your code you can create a new html file with the angular code and use `ng-include` to add it to the main html. The `nh-include` expects a variable with the name of the file to include, to pass the name directly you can use a string with single quotes inside the double quotes.

```html
<h3 ng-include="'product-title.html'"> </h3>
```

**Directives** allow you to write HTML that expresses the behavior of your application. **Template-expanding Directives** are the simples, they define a custom tag or attribute that is expanded or replaced, and can include **Controller** logic if needed.

Directives can also be used for:
- Expressing complex UI
- Calling events and registering event handles
- Reusing common components
