# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Learn how Script Tags and Document Ready Work
For some reason FCC likes to introduce `jQuery` before JavaScript itself.

To add JS to your HTML, you need a `script` tag.  Your browser will run any JavaScript inside a script element, including jQuery.

Inside your script element, add this code: `$(document).ready(function() {` to your script. Then close it on the following line (still inside your script element) with: `});`

```js
<script> $(document).ready(function(){

});</script>
```

## Target HTML Elements with Selectors Using jQuery
After we have created our `document ready function` we can now have code that will run after the page loads. This will assure that your code does not run before the HTML is rendered to avoid bugs.

jQuery often selects an HTML element with a selector, then does something to that element.  

The following code will make the buttons have a bouncy animation on page load.

```js
<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
  });
</script>
```

## Target Elements by Class Using jQuery
Just as we did before, we can also target elements by classes.

`$(".well").addClass("animated shake");`

## Target Elements by ID Using jQuery
You can also target elements by their id attributes. Note that, just like with CSS declarations, you type a # before the id's name.

`$("#target3").addClass("animated fadeOut");`

## Delete your jQuery Functions
To delete the functions it is just as any other piece of code that you want to remove, select it and delete with the keyboard.

## Target the same element with multiple jQuery Selectors
The multiple jQuery selectors are:
1. By type: `$("button")`
2. By class: `$(".btn")`
3. By id: `$("#target1")`

```html
<script>
  $(document).ready(function() {
    $("button").addClass("animated");
    $(".btn").addClass("shake");
    $("#target1").addClass("animated shake btn-primary");
  });
</script>
```

## Remove Classes from an element with jQuery
The same way we can add classes using jQuery, we an also remove them with `removeClass()`.

`$("button").removeClass("btn-default");`

## Change the CSS of an Element Using jQuery
We can also change the CSS of an HTML element directly with jQuery.

Query has a function called `.css()` that allows you to change the CSS of an element.

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");

  });
</script>
```

## Disable an Element Using jQuery
You can also change the non-CSS properties of HTML elements with jQuery. For example, you can disable buttons.

When you disable a button, it will become grayed-out and can no longer be clicked.

jQuery has a function called `.prop()` that allows you to adjust the properties of elements.

Here's how you would disable all buttons: `$('#button').prop('disabled', true);`

## Remove an Element Using jQuery
jQuery has a function called `.remove()` that will remove an HTML element entirely. `$("#target4").remove();`

## Use appendTo to Move Elements with jQuery
jQuery has a function called `appendTo()` that allows you to select HTML elements and append them to another element.

For example, if we wanted to move target4 from our right well to our left well, we would use `$("#target4").appendTo("#left-well");`

## Clone an Element Using jQuery
jQuery has a function called`clone()` that makes a copy of an element.

For example, if we wanted to copy target2 from our left-well to our right-well, we would use `$("#target2").clone().appendTo("#right-well");`

## Target the Parent of an Element Using jQuery
Every HTML elements has a parent element from which it inherits properties.

For example, your jQuery Playground `h3` element has the parent element of`<div class="container-fluid">`, which itself has the parent body.

jQuery has a function called `parent()` that allows you to access the parent of whichever element you've selected.

Here's an example of how you would use the `parent()` function: `$("#left-well").parent().css("background-color", "blue")`

## Target the Children of an Element Using jQuery
Many HTML elements have children elements from which they inherit properties.

jQuery has a function called `children()` that allows you to access the children of whichever element you've selected.

Here's an example of how you would use the `children()` function: `$("#left-well").children().css("color", "blue");`

## Target a Specific Child of an Element Using jQuery
jQuery uses CSS Selectors to target elements. `target:nth-child(n)` css selector allows you to select all the nth element with the target class or element type.

Here's how you would give the third element in each well bounce: `$(".target:nth-child(3)").addClass("animated bounce");`

`$(".btn:nth-child(2)").addClass("animated bounce");`

## Target Even Numbered Elements Using jQuery
You can also target all the even-numbered elements.

Here's how you would target all the `odd-numbered` elements with class target and give them classes: `$('.target:odd').addClass('animated shake');`

This will shake all the even ones: `$('.target:even').addClass("shake");`

## Use jQuery to Modify the Entire Page
jQuery can target the body element as well.

Here's how we would make the entire body fade out: `$('body').addClass('animated fadeOut');`

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
    $("#target1").prop("disabled", true);
    $("#target4").remove();
    $("#target2").appendTo("#right-well");
    $("#target5").clone().appendTo("#left-well");
    $("#target1").parent().css("background-color", "red");
    $("#right-well").children().css("color", "green");
    $("#left-well").children().css("color", "green");
    $(".target:nth-child(2)").addClass("animated bounce");
    $(".target:even").addClass("animated shake");
    $("body").addClass("animated hinge");

  });
</script>

<!-- You shouldn't need to modify code below this line -->

<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1">#target1</button>
        <button class="btn btn-default target" id="target2">#target2</button>
        <button class="btn btn-default target" id="target3">#target3</button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4">#target4</button>
        <button class="btn btn-default target" id="target5">#target5</button>
        <button class="btn btn-default target" id="target6">#target6</button>
      </div>
    </div>
  </div>
</div>
```
