# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128) submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Say Hello to HTML Elements
HTML elements are written with a start tag, with an end tag, with the content in between:

`<tagname>content</tagname>` The HTML element is everything from the start tag to the end tag:

`<p>My first HTML paragraph.</p>`

Opening tags look like this: `<h1>. Closing tags look like this: </h1>`  Note that the only difference between opening tags and closing tags is that closing tags have a slash after their opening angle bracket.

## Headline with the h2 Element
You can create different levels of Heading elements by using h1, h2, h3, h4, h5, h6 which will result on different sizes.

```
<h1>Hello World</h1>
<h2> CatPhotoApp</h2>
```

## Inform with the Paragraph Element
**p** elements are the preferred element for normal-sized paragraph text on websites. P is short for "paragraph".

You can create a p element like so: `<p>I'm a p tag!</p>`.

```
<h1>Hello World</h1>
<h2>CatPhotoApp</h2>
<p>Hello Paragraph</p>
```

## Uncomment HTML
Commenting is a way that you can leave comments within your code without affecting the code itself.

Commenting is also a convenient way to make code inactive without having to delete it entirely.

You can start a comment with `<!-- and end a comment with -->`.

```
<!--
<h1>Hello World</h1>

<h2>CatPhotoApp</h2>

<p>Hello Paragraph</p>
-->
```

## Comment out HTML
Remember that in order to start a comment, you need to use `<!-- and to end a comment, you need to use -->.`

```
<!--
<h1>Hello World</h1>
-->
<h2>CatPhotoApp</h2>
<!--
<p>Hello Paragraph</p>
-->
```

## Fill in the Blank with Placeholder Text
Web developers traditionally use lorem ipsum text as placeholder text. It's called lorem ipsum text because those are the first two words of a famous passage by Cicero of Ancient Rome.

lorem ipsum text has been used as placeholder text by typesetters since the 16th century, and this tradition continues on the web.

```
<h1>Hello World</h1>

<h2>CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

## Delete HTML Elements
Deleting elements is very simple. All you have to do is remove everything from the opening to the closing of the element and it will be removed. No extra code is needed.

## Change the Color of Text
CSS allows us to change  many styles. To change the color of an element he use **color**.

Here's how you would set your h2 element's text color to blue: `<h2 style="color: blue">CatPhotoApp</h2>`.

```
<h2 style="color: red">CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

## Use CSS Selectors to Style Elements
Instead of giving style attributes one by one, we can do this to multiple elements at the same time.

> At the top of your code, create a style element like this: <style></style>.

Inside that style element, you can create a CSS selector for all h2 elements. For example, if you wanted all h2 elements to be red, your style element would look like this: <style>h2 {color: red;}</style>.

Note that it's important to have both opening and closing curly braces ({ and }) around each element's style. You also need to make sure your element's style is between the opening and closing style tags. Finally, be sure to add the semicolon to the end of each of your element's styles.

```
<style>
h2{
  color: blue;
}
</style>

<h2>CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

## Use a CSS Class to Style an Element
Classes are reusable styles that can be added to HTML elements. You can apply a class to an HTML element like this: `<h2 class="blue-text">CatPhotoApp</h2>`.

Note that in your CSS style element, classes should start with a period. In your HTML elements' class declarations, classes shouldn't start with a period.

```
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

## Style Multiple Elements with a CSS Class
Remember that you can attach classes to HTML elements by using class="your-class-here" within the relevant element's opening tag.

Remember that CSS selectors require a period at the beginning like this: `.blue-text { color: blue; }`, but that class declarations don't use a period, like this: `<h2 class="blue-text">CatPhotoApp<h2>`.

```
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

## Change the Font Size of an Element
Font size is controlled by the font-size CSS attribute, like this: `h1 { font-size: 30px; }`.

```
<style>
  .red-text {
    color: red;
  }
  p{
    font-size: 16px;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p >Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Set the Font Family of an Element
You can set an element's font by using the font-family attribute.

For example, if you wanted to set your h2 element's font to Sans-serif, you would use the following CSS: `h2 { font-family: Sans-serif; }`.

```
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Import a Google Font
To import font from Google or any other site, this is the format that you should follow: `<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">`

```
<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;

  }
  h2{
    font-family: Lobster;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p class="red-text">Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Specify How Fonts Should Degrade
There are several default fonts that are available in all browsers. These include **Monospace, Serif** and **Sans-Serif**.

For example, if you wanted an element to use the Helvetica font, but also degrade to the Sans-Serif font when Helvetica wasn't available, you could use this CSS style: `p { font-family: Helvetica, Sans-Serif; }`.

```
<!--<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css"> -->
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p class="red-text">Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Add Images to your Website
You can add images to your website by using the img element, and point to an specific image's URL using the src attribute.

An example of this would be `<img src="www.your-image-source.com/your-image.jpg">`. Note that in most cases, img elements are self-closing.

```
<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<img src = "https://bit.ly/fcc-relaxing-cat">
<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p class="red-text">Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Size your Images
CSS has an attribute called width that controls an element's width. Just like with fonts, we'll use px (pixels) to specify the image's width.

For example, if we wanted to create a CSS class called larger-image that gave HTML elements a width of 500 pixels, we'd use: `<style> .larger-image { width: 500px; } </style>`.

```
<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  .smaller-image{
    width: 100px;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<img class="smaller-image" src="https://bit.ly/fcc-relaxing-cat">

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p class="red-text">Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Add Borders Around your Elements
CSS borders have attributes like style, color and width.

For example, if we wanted to create a red, 5 pixel border around an HTML element, we could use this class: `<style> .thin-red-border { border-color: red; border-width: 5px; border-style: solid; } </style>`.

```
<link href="http://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .smaller-image {
    width: 100px;
  }

  .thick-green-border{
    border-color: green;
    border-width: 10px;
    border-style: solid;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<img class="smaller-image thick-green-border" src="https://bit.ly/fcc-relaxing-cat">

<p class="red-text">Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
<p class="red-text">Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
```

## Add Rounded Corners with a Border Radius
To make round corners it is all about **border-radius** and pixels.

> You can specify a border-radius with pixels. This will affect how rounded the corners are.

```
.thick-green-border {
  border-color: green;
  border-width: 10px;
  border-style: solid;
  border-radius: 10px;
}
```

## Make Circular Images with a Border Radius
You can also use percentage to **border*radius** to make things round.

```
.thick-green-border {
  border-color: green;
  border-width: 10px;
  border-style: solid;
  border-radius: 50%;
}
```

## Link to External Pages with Anchor Elements
> **a** elements, also known as anchor elements, are used to link to content outside of the current page.

Here's an example: `<p>Here's a <a href="http://freecodecamp.com"> link to Free Code Camp</a> for you to follow.</p>`.

## Nest an Anchor Element within a Paragraph
Nesting is simple, just add one element inside another: `<p> click here for <a href="http://www.catphotoapp.com">cat photos</a></p>`

## Make Dead Links using the Hash Symbol
Sometimes you want to add a elements to your website before you know where they will link.

This is also handy when you're changing the behavior of a link using jQuery, which we'll learn about later.

Replace your a element's href attribute with a #, also known as a hash symbol, to turn it into a dead link. `Sometimes you want to add a elements to your website before you know where they will link.

This is also handy when you're changing the behavior of a link using jQuery, which we'll learn about later.

Replace your a element's href attribute with a #, also known as a hash symbol, to turn it into a dead link.`

## Turn an Image into a Link
Creating images that link to things is essential and one of the most used things in Web Dev. Nest your image within an a element. Here's an example: `<a href="#"><img src="http://bit.ly/fcc-running-cats"/></a>`.

## Add Alt Text to an Image for Accessibility
**alt** attributes, also known as alt text, are what browsers will display if they fail to load the image. alt attributes are also important for blind or visually impaired users to understand what an image portrays. And search engines also look at alt attributes.

In short, every image should have an alt attribute!

You can add an alt attribute right in the img element like this: `<img src="www.your-image-source.com/your-image.jpg" alt="your alt text"/>`.

## Create a Bulleted Unordered List
HTML has a special element for creating unordered lists, or bullet point-style lists.

Unordered lists start with a **<ul>** element. Then they contain some number of **<li>** elements.

For example:

```
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

would create a bullet point-style list of "milk" and "cheese".

## Create an Ordered List
HTML has a special element for creating ordered lists, or numbered-style lists.

Ordered lists start with a **<ol>** element. Then they contain some number of **<li>** elements.

For example:

```
<ol>
  <li>hydrogen</li>
  <li>helium</li>
</ol>
```

would create a numbered list of "hydrogen" and "helium".

## Create a Text Field
Text inputs are a convenient way to get input from your user.

You can create one like this: `<input type="text">`. Note that input elements are self-closing.

## Add Placeholder Text to a Text Field
Your placeholder text is what appears in your text input before your user has inputed anything.

You can create placeholder text like so: `<input type="text" placeholder="this is placeholder text">`.

`<input type="text" placeholder="cat photo URL">`

## Create a Form Element
> You can build web forms that actually submit data to a server using nothing more than pure HTML. You can do this by specifying an action on your form element.

For example: `<form action="/url-where-you-want-to-submit-form-data"></form>`.

`<form action="/submit-cat-photo"><input type="text" placeholder="cat photo URL"></form>`

## Add a Submit Button to a Form
You will need to create a button element. Here's an example submit button: `<button type="submit">this button submits the form</button>`.

```
<form action="/submit-cat-photo">
  <input type="text" placeholder="cat photo URL">
  <button type="submit">Submit</button>
</form>
```

## Use HTML5 to Require a Field
You can require specific form fields so that your user will not be able to submit your form until he or she has filled them out.

For example, if you wanted to make a text input field required, you can just add the word required within your input element, you would use: `<input type="text" required>`.

```
<form action="/submit-cat-photo">
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
</form>
```

## Create a Set of Radio Buttons
> You can use radio buttons for questions where you want the user to only give you one answer.

Radio buttons are a type of input. They should all be nested in their own label element. Furthermore, all related radio buttons should have the same name attribute.

Here's an example of a radio button: `<label><input type="radio" name="indoor-outdoor"> Indoor</label>`.

## Create a Set of Checkboxes
## Check Radio Buttons and Checkboxes by Default
## Nest Many Elements within a Single Div Element
## Give a Background Color to a Div Element
## Set the ID of an Element
## Use an ID Attribute to Style an Element
## Adjusting the Padding of an Element
## Adjust the Margin of an Element
## Add a Negative Margin to an Element
## Add Different Padding to Each Side of an Element
## Add Different Margins to Each Side of an Element
## Use Clockwise Notation to Specify the Padding of an Element
## Use Clockwise Notation to Specify the Margin of an Element
## Style the HTML Body Element
## Inherit Styles from the Body Element
## Prioritize One Style Over Another
## Override Styles in Subsequent CSS
## Override Class Declarations by Styling ID Attributes
## Override Class Declarations with Inline Styles
## Override All Other Styles by using Important
## Use Hex Code for Specific Colors
## Use Hex Code to Color Elements White
## Use Hex Code to Color Elements Red
## Use Hex Code to Color Elements Green
## Use Hex Code to Color Elements Blue
## Use Hex Code to Mix Colors
## Use Hex Code to Color Elements Gray
## Use Hex Code for Specific Shades of Gray
## Use Abbreviated Hex Code
## Use RGB values to Color Elements
## Use RGB to Color Elements White
## Use RGB to Color Elements Red
## Use RGB to Color Elements Green
## Use RGB to Color Elements Blue
## Use RGB to Mix Colors
## Use RGB to Color Elements Gray
