# Creating Modules
To create a module we first create a variable for the app, then we will use the angular library to create a module, we give it a name and an array of dependencies, it can be an empty array if there are no dependencies.

```js
var app = angular.module('store', []);
```

Don't forget to add the library to the html though.

# Including the module
This is very simple, you just have to add it as any other script or library, add a link to the `<body>`

```html
<body>
  <script type="text/javascript" src="app.js"></script>
</body>
```

Then on the `<html>` tag we include `np-app="store"`

# Expressions
They allows us to insert dynamic values into our HTML.

```html
<p>
  I am {{4 + 6}}
</p>
```

This will be the same as `<p>I am 10</p>`

It also works for strings too. There are more examples [here.](http://docs.angularjs.org/guide/expression)

# Controllers
Controllers are where we define out app's behavior by defining functions and values.

```js
(function(){
  var app = angular.module('store', []);

  app.controller('StoreController', function(){
    this.product = gem;
});
})();
```

This will do the magic in this scope only.

```html
<div ng-controller="StoreCOntroller as store">
  <h1> {{store.product.name}} </h1>
  <h2> ${{store.product.price}} </h2>
  <p> {{store.product.description}} </p>
</div>
```
