# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Use Responsive Design with Bootstrap Fluid Containers
Bootstrap will figure out how wide your screen is and respond by resizing your HTML elements - hence the name Responsive Design.

With responsive design, there is no need to design a mobile version of your website. It will look good on devices with screens of any width.

You can add Bootstrap to any app just by including it with `<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css"/>` at the top of your HTML.

## Make Images Mobile Responsive
When using Bootstrap, if you want an image to be responsive, all you have to do is add the class `img-responsive` to it. `<img class="img-responsive" src="http://bit.ly/fcc-running-cats">`

## Center Text with Bootstrap
Now that we're using Bootstrap, we can center our heading elements to make them look better. All we need to do is add the class text-center to our h1 and h2 elements.

Remember that you can add several classes to the same element by separating each of them with a space, like this: `<h2 class="text-red text-center">your text</h2>`.

## Create a Bootstrap Button
Bootstrap has its own styles for button elements, which look much better than the plain HTML ones.

`<button type="submit" class="btn">Like</button>`

## Create a Block Element Bootstrap Button
Normally, your button elements are only as wide as the text that they contain. By making them block elements, your button will stretch to fill your page's entire horizontal space. Note that these buttons still need the `btn` class.

`<button class="btn btn-block">Like</button>`

## Taste the Bootstrap Button Color Rainbow
The `btn-primary` class is the main color you'll use in your app. It is useful for highlighting actions you want your user to take. Note that this button will still need the `btn` and `btn-block` classes.

`<button class="btn btn-block btn-primary">Like</button>`

## Call out Optional Actions with Button Info
Bootstrap comes with several pre-defined colors for buttons. The `btn-info` class is used to call attention to optional actions that the user can take. Note that these buttons still need the `btn` and`btn-block` classes.

`<button class= "btn btn-block btn-info">Info</button>`

## Warn your Users of a Dangerous Action
The `btn-danger` class is the button color you'll use to notify users that the button performs a destructive action, such as deleting a cat photo. Note that these buttons still need the `btn` and `btn-block` classes.

`<button class="btn btn-block btn-danger">Delete</button>`

## Use the Bootstrap Grid to Put Elements Side By Side
Bootstrap uses a responsive grid system that makes it easier to put elements into rows and tell each element's relative width.

![Bootstrap 12 column grid layout](https://www.evernote.com/shard/s116/sh/f0944d97-08b8-4615-8273-a327bf41fb05/de1a3acbceef89ae/deep/0/)

Note that in this illustration, the `col-md-_` class is being used. Here, md means medium, and _ is a number specifying how many columns wide the element should be. In this case, the column width of an element on a medium-sized screen, such as a laptop, is being specified.

```html
<div class="row">

  <div class="col-xs-4"><button class="btn btn-block btn-primary">Like</button></div>
  <div class="col-xs-4"><button class="btn btn-block btn-info">Info</button></div>
  <div class="col-xs-4"><button class="btn btn-block btn-danger">Delete</button></div>

</div>
```

## Ditch Custom CSS for Bootstrap
We can clean up our code and make our Cat Photo App look more conventional by using Bootstrap's built-in styles instead of the custom styles we created earlier.

All you need to know is the built in [classes](http://getbootstrap.com/css/).

## Use Spans for Inline Elements
You can use use spans to create inline elements. By using the span element, you can put several elements together, and even style different parts of the same element differently.

`<p><span class = "text-danger">Things cats love:</span></p>`

## Create a Custom Heading
Using `div` and the custom grid layout we can create our own heading.

```html
<div class="row">
   <div class="col-xs-8">
     <h2 class="text-primary text-center">CatPhotoApp</h2>
   </div>
   <div class="col-xs-4">
     <a href="#"><img class="img-responsive thick-green-border" src="https://bit.ly/fcc-relaxing-cat"></a>
   </div>
```

## Add Font Awesome Icons to our Buttons
Font Awesome is a convenient library of icons. These icons are vector graphics, stored in the .svg file format. These icons are treated just like fonts. You can specify their size using pixels, and they will assume the font size of their parent HTML elements.

`<i class="fa fa-thumbs-up"><button class="btn btn-block btn-primary">Like</i></button>`

## Add Font Awesome Icons to all of our Buttons
`<i class="fa fa-trash"></i>` Will add a trash can icon.

`<i class="fa fa-info-circle"></i>` Will add an info icon.

## Responsively Style Radio Buttons
You can use Bootstrap's `col-xs-*` classes on `form` elements. That will make radio buttons evenly spread out across the page regardless of how wide the screen might be.

Nest all of your radio buttons within a `<div class="row">` element. Then nest each of them within a `<div class="col-xs-6">` element.

```html
<form action="/submit-cat-photo">
  <div class="row">
    <div class="col-xs-6"><label><input type="radio" name="indoor-outdoor"> Indoor</label></div>
    <div class="col-xs-6"><label><input type="radio" name="indoor-outdoor"> Outdoor</label></div>
    <div class="col-xs-6"><label><input type="checkbox" name="personality"> Loving</label></div>
    <div class="col-xs-6"><label><input type="checkbox" name="personality"> Lazy</label></div>
    <div class="col-xs-6"><label><input type="checkbox" name="personality"> Crazy</label></div>
  </div>
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
</form>
```

## Responsively Style Checkboxes
You can use Bootstrap's `col-xs-*` classes on form elements, too! This way, our checkboxes will be evenly spread out across the page, regardless of how wide the screen resolution is.

Nest all your checkboxes in a `<div class="row">` element. Then nest each of them in a `<div class="col-xs-4">` element.

## Style Text Inputs as Form Controls
You can add the `fa-paper-plane` Font Awesome icon by adding `<i class="fa fa-paper-plane"></i>` within your submit button element.

`<button type="submit" class="btn btn-primary"><i class="fa fa-paper-plane">Submit</i>`

## Line up Form Elements Responsively with Bootstrap
We line up the form elements the same way we do with others, using divs.

```html
<div class="row">
<div class="col-xs-7"><input type="text" class="form-control" placeholder="cat photo URL" required></div>
<div class=col-xs-5><button type="submit" class="btn btn-primary"><i class="fa fa-paper-plane"></i> Submit</button></div>
</div>
```

## Create a Bootstrap Headline
`<h3 class="text-primary text-center"> jQuery Playground </h3>`

## House our page within a Bootstrap Container Fluid Div
To make the content responsive, we use the `container-fluid` class.

```html
<div class="container-fluid">
<h3 class="text-primary text-center">jQuery Playground</h3>
</div>
```

## Create a Bootstrap Row
Create a div element with the class row. `<div class="row"></div>`

## Split your Bootstrap Row
Create two `div` elements within your row, both with the class `col-xs-6`.

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6"> </div>
    <div class="col-xs-6"></div>
  </div>
</div>
```

## Create Bootstrap Wells
Bootstrap has a class called `well` that can create a visual sense of depth for your columns.

Nest one div element with the class well within each of your `col-xs-6 div` elements.

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
  </div>
</div>
```

## Add Elements within your Bootstrap Wells
Once you have gone deep enough in `divs` you can start adding your Bootstrap buttons.

## Apply the Default Bootstrap Button Style
Bootstrap has a button class called `btn-default`

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
  </div>
</div>
```

## Create a Class to Target with jQuery Selectors
Not every class needs to have corresponding CSS. Sometimes we create classes just for the purpose of selecting these elements more easily using jQuery.

For this we use the `target` class on the `button` elements.

## Add ID Attributes to Bootstrap Elements
Recall that in addition to class attributes, you can give each of your elements an id attribute.

Each id should be unique to a specific element. Remember that you can give an element an id like this: `<div class="well" id="center-well">`

## Label Bootstrap Wells
You can add labels to the wells by using the headers `<h4>` above the well divs.

## Give Each Element a Unique ID
We will also want to be able to use jQuery to target each button by its unique id. So we add an unique id to each button.

## Label Bootstrap Buttons
Just like we labeled our wells, we want to label our buttons.

## Use Comments to Clarify Code
When we start using jQuery, we will modify HTML elements without needing to actually change them in HTML.

This is a great way to make websites with a particular structure. Remember that you can start a comment with `<!-- and end a comment with -->`

```html
<!--You shouldn't need to modify code below this line -->
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
