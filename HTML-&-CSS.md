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
## Set the Font Family of an Element
## Import a Google Font
## Specify How Fonts Should Degrade
## Add Images to your Website
## Size your Images
## Add Borders Around your Elements
## Add Rounded Corners with a Border Radius
## Make Circular Images with a Border Radius
## Link to External Pages with Anchor Elements
## Nest an Anchor Element within a Paragraph
## Make Dead Links using the Hash Symbol
## Turn an Image into a Link
## Add Alt Text to an Image for Accessibility
## Create a Bulleted Unordered List
## Create an Ordered List
## Create a Text Field
## Add Placeholder Text to a Text Field
## Create a Form Element
## Add a Submit Button to a Form
## Use HTML5 to Require a Field
## Create a Set of Radio Buttons
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
