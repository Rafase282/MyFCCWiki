# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/MarufSarker/full/ZGPZLq/](http://codepen.io/MarufSarker/full/ZGPZLq/).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
- As a user, I can browse recent posts from Camper News.
- As a user, I can click on a post to be taken to the story's original URL.
- As a user, I can see how many upvotes each story has.

## Hints:
1. Here's the Camper News Hot Stories API endpoint: [http://www.freecodecamp.com/news/hot](http://www.freecodecamp.com/news/hot).

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippet
The HTML part is quite simple, I just have to create a heading, a section where the html will be generated and my footer.

```html
<section>
  <h1>FreeCodeCamp</h1>
  <h2>Camper News</h2>
  <div class="row">
  </div>
</section>
<footer>
  <p>Copyright © Rafael J. Rodriguez 2015. All Rights Reserved</p>
  <p>
    <a href="mailto:rafase282@gmail.com">
      <i class="fa fa-envelope fa-fw"></i>
    </a>
    <a href="https://github.com/Rafase282" target='_blank'>
      <i class="fa fa-github fa-fw"></i>
    </a>
    <a href="https://www.linkedin.com/in/rafase282" target='_blank'>
      <i class="fa fa-linkedin"></i>
    </a>
    <a href="http://codepen.io/Rafase282" target='_blank'>
      <i class="fa fa-codepen"></i>
    </a>
    <a href="https://rafase282.wordpress.com/" target='_blank'>
      <i class="fa fa-wordpress"></i>
    </a>
    <a href="http://www.freecodecamp.com/rafase282" target='_blank'>
  (<i class="fa fa-fire fa-fw"></i>)
</a>
  </p>
</footer>
```

## My CSS Code Snippets
The CSS part is also straight forward. There are not that many elements after all.

```css
h2 {
  font-family: cursive, sans-serif;
  color: gray;
  margin-bottom: 50px;
}
h1 {
  font-size: 52px;
  font-family: cursive, sans-serif;
  color: #663300;
}
section {
  min-height: 90vh;
  padding-top: 10px;
  padding-bottom: 10px;
  color: #fff;
  background-color: #B29980;
  bottom: 10px;
  text-align: center;
}
footer {
  background-color: black;
  color: gray;
  line-height: 20px;
  padding-top: 10px;
  padding-bottom: 6px;
  position: relative;
  text-align: center;
  font-family: cursive, sans-serif;
}
.logo {
  border-radius: 5%;
  height: 250px;
  width: 200px;
  margin-right: 10px;
}
.well {
  width: 230px;
  height: 370px;
  color: black;
  margin-right: 10px;
  margin-left: 20px;
}
.row {
  margin: auto;
  width: 95%;
}
```

## My JS Code Snippets
Now, this part was interesting and not so difficult. Mostly things I have used before. I did however, discovered a new library that is quite old.

It is the [Datejs](https://github.com/datejs/Datejs) library. Quite useful for formatting strings. Saves me the trouble of doing it myself and writing more code. You will need to add this to your code: `<script src='http://www.datejs.com/build/date.js'></script>`

For the trunc function, I got it from [here.](http://stackoverflow.com/questions/1199352/smart-way-to-shorten-long-strings-with-javascript)

```js
// Function to truncate strings to custom lenght.
String.prototype.trunc = String.prototype.trunc ||
  function(n) {
    return this.length > n ? this.substr(0, n - 1) + '&hellip;' : this;
  };

$(document).ready(function() {
  // Set default values for key variables
  var url = 'http://www.freecodecamp.com/news/hot';
  var username = 'Unknown';
  var picture = 'http://i.imgur.com/vPEp5RQ.png';
  var headline = 'Undefined';
  var link = '';
  var upvotes = 0;
  var fcc = 'http://freecodecamp.com/';
  var time = 0;
  var html;

  // Call API
  $.getJSON(url, function(data) {
    // For each object in the json file, asign the right data to the variables.
    for (var news in data) {
      username = data[news].author.username;
      picture = data[news].author.picture;
      headline = data[news].headline;
      link = data[news].link;
      upvotes = data[news].upVotes.length;
      time = new Date(data[news].timePosted);

      // Generate HTML5 elements to be displayed

      html = '<article class="col-xs-2 well well-sm"><img class="logo" src="' + picture + '"><a href="' + fcc + username + '" target="_blank"><p>by' + username + '(<i class="fa fa-fire fa-fw"></i>)<span class="glyphicon glyphicon glyphicon-arrow-up"></span>' + upvotes + '</p></a><a href="' + link + '"target="_blank"><p>' + headline.trunc(50) + '</p></a><p> Posted on: ' + time.toString('ddd d, MMM yyyy') + '</p></article>';

      // Displays the elements to the page
      $('.row').append(html);
    }
  });
});
```
