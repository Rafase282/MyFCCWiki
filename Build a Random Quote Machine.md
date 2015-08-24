# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [Random Quotes Rewritten](http://codepen.io/AdventureBear/full/vEoVMw).

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can click a button to show me a new random quote.
2. As a user, I can press a button to tweet out a quote.

## Notes:
Note that you can either put your quotes into an array and show them at random, or use an API to get quotes, such as [http://forismatic.com/en/api/](http://forismatic.com/en/api/).

## My HTML Code Snippets
## My CSS Code Snippets
There is no much CSS used here. First I used this site [http://colorsafe.co/](http://colorsafe.co/) for picking colors, size and fonts. I also checked this site [http://www.w3schools.com/cssref/css_websafe_fonts.asp](http://www.w3schools.com/cssref/css_websafe_fonts.asp) for the default family fonts.
- I gave a new font family to all the paragraphs and anything under the class `container-fluid`.
- I aligned everything at the center.
- gave them respective margins on the sides for styling.
- I gave a new font color, and background color for the body and footer.
- I played around with the `section` elements and footer to make it take the whole page so the footer is at the bottom.

```
p,
.container-fluid {
  text-align: center;
  padding-bottom: 20px;
  margin-left: 10%;
  margin-right: 10%;
  color: #e4f1fe;
  font-family: 'Comic Sans MS';
}

body {
  position: relative;
  background-color: #0d493b;
}

.well {
  margin-left: 3%;
  margin-right: 3%;
  background-color: #0d493b;
}

footer {
  min-height: 1vh;
  padding-top: 20px;
  padding-bottom: 1px;
  background-color: black;
}

section {
  min-height: 91.8vh;
  font-size: 18px;
  font-weight: 300;
}
```
