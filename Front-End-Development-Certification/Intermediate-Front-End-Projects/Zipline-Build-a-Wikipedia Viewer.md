# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/GeoffStorbeck/full/MwgQea](http://codepen.io/GeoffStorbeck/full/MwgQea).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
- As a user, I can search Wikipedia entries in a search box and see the resulting Wikipedia entries.
- As a user, I can click a button to see a random Wikipedia entry.
- As a user, when I type in the search box, I can see a dropdown menu with autocomplete options for matching Wikipedia entries.

## Hints:
1. Here's an entry on using Wikipedia's API: [http://www.mediawiki.org/wiki/API:Main_page.](http://www.mediawiki.org/wiki/API:Main_page)

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippet
For the search bar I used one from this [demo.](http://codepen.io/912lab/pen/LsplC?editors=110)

```html
<section>
  <div class="container-fluid">
    <h1>Wikipedia Viewer</h1>
    <article class="search-position">
      <p class="search-icon">
        <input name="search" id="search" type="search">
      </p>
    </article>
    <article class="random">
      <a href="https://en.wikipedia.org/wiki/Special:Random" target="_blank">
        <button type="button" class="btn btn-primary">Random Article!</button>
      </a>
      </articles>
      <article class="results">
      </article>
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

```css
h1 {
  font-size: 52px;
  font-family: Courier;
  text-align: center;
  font-family: Courier New, Courier, monospace;
}
section {
  min-height: 90vh;
  padding-top: 10px;
  padding-bottom: 10px;
  color: #fff;
  background-color: #34addb;
  bottom: 10px;
}
.well {
  margin-right: 100px;
  margin-left: 100px;
}
.results {
  margin-top: 10%;
}
.random {
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
.search-position {
  position: absolute;
  left: 50%;
  top: 20%;
  transform: translate(-50%, -50%);
}

/* Search Bar CSS */

#search {
  -webkit-appearance: none;
  font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
  width: 24px;
  padding: 0 10px;
  height: 24px;
  font-size: 14px;
  color: #666;
  line-height: 24px;
  border: 0;
  border-radius: 50px;
  box-shadow: 0 0 0 1px rgba(0, 150, 200, .5), inset 0 2px 5px rgba(0, 100, 150, .3), 0 2px 0 rgba(255, 255, 255, .6);
  position: relative;
  z-index: 5;
  -webkit-transition: .3s ease;
  -moz-transition: .3s ease;
}

/* When clicked */

#search:focus {
  outline: none;
  width: 200px;
}
.search-icon {
  margin: 50px auto 0 -50%;
  left: 50%;
  z-index: 4;
  position: relative;
  padding: 5px;
  line-height: 0;
  border-radius: 100px;
  background: #b9ecfe;
  background-image: -webkit-linear-gradient(#dbf6ff, #b9ecfe);
  background-image: -moz-linear-gradient(#dbf6ff, #b9ecfe);
  display: inline-block;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, .6), 0 2px 5px rgba(0, 100, 150, .4);
}
.search-icon:hover {
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, .6), 0 2px 3px 2px rgba(100, 200, 255, .5);
}
.search-icon:after {
  content: '';
  display: block;
  position: absolute;
  width: 5px;
  height: 20px;
  background: #b9ecfe;
  bottom: -10px;
  right: -3px;
  border-radius: 0 0 5px 5px;
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  box-shadow: inset 0 -1px 0 rgbA(255, 255, 255, .6), -2px 2px 2px rgba(0, 100, 150, .4);
}
.search-icon:hover:after {
  box-shadow: inset 0 -1px 0 rgba(255, 255, 255, .6), -2px 2px 2px 1px rgba(100, 200, 255, .5);
}
```

## My JS Code Snippets

```js
var arrResults = [];
var html = '';

// Create structure for the data
function Result(title, snippet) {
  this.title = title;
  this.snippet = snippet;
}

function search() {
  // Use Ajax to handle things
  $.ajax({
    url: 'https://en.wikipedia.org/w/api.php?action=query&list=search&format=json&srsearch=' + $('#search').val(),
    dataType: 'jsonp',
    type: 'POST',
    headers: {
      'Api-User-Agent': 'Example/1.0'
    },
    success: function(data) {

      // First we clear the children from our class to make sure no previous results are showing.
      $('.results').empty();

      // Then we also clear the array with the results before providing new information.
      arrResults.length = 0;
      var resArr = data.query.search;

      //For each result, generate the html data.
      for (var result in resArr) {
        arrResults.push(new Result(resArr[result].title, resArr[result].snippet));
        html = '<div id="articles" class="well"><a href="https://en.wikipedia.org/wiki/' + resArr[result].title + '"target="_blank"><h3>' + resArr[result].title + '</h3><p>' + resArr[result].snippet + '</p></a></div>';

        // Displays the elements to the page
        $('.results').append(html);
      }
    }
  });

  // This will handle when to display results based on the search bar.
  if ($('#search').val().length > 0) {
    $('.articles').css('display', 'none');

  } else if ($('#search').val().length < 1) {
    // display everything again
    $('.articles').css('display', 'block');
  }

  // This make things tick with each key stroke
  $('#search').unbind('keyup');
  $('#search').keyup(function() {
    search();
  });
}

$('#search').keyup(function() {
  search();
});
```

## Links
- [Centering Percentage Width/Height Elements](https://css-tricks.com/centering-percentage-widthheight-elements/)
- [Search Bar](http://jsfiddle.net/daneden/tr5bs/embedded/result/)
- [CSS Margins](http://www.w3schools.com/css/css_margin.asp)
