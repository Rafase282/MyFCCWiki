# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/GeoffStorbeck/full/GJKRxZ](http://codepen.io/GeoffStorbeck/full/GJKRxZ).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
- As a user, I can see whether Free Code Camp is currently streaming on Twitch.tv.
- As a user, I can click the status output and be sent directly to the Free Code Camp's Twitch.tv channel.
- As a user, if Free Code Camp is streaming, I can see additional details about what they are streaming.
- As a user, I can search through the streams listed.
- As a user, I will see a placeholder notification if a streamer has closed their Twitch account. You can verify this works by adding brunofin and comster404 to your array of Twitch streamers.

## Hints:
1. Here's an example call to Twitch.tv's JSON API: [https://api.twitch.tv/kraken/streams/freecodecamp](https://api.twitch.tv/kraken/streams/freecodecamp).
2. The relevant documentation about this API call is here: [https://github.com/justintv/Twitch-API/blob/master/v3_resources/streams.md#get-streamschannel](https://github.com/justintv/Twitch-API/blob/master/v3_resources/streams.md#get-streamschannel).
3. Here's an array of the Twitch.tv usernames of people who regularly stream coding: `["freecodecamp", "storbeck", "terakilobyte", "habathcx","RobotCaleb","thomasballinger","noobs2ninjas","beohoff"]`

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets
For the HTML part there was nothing special other than  getting the form for the search function and also the [Toggable / Dynamic Tabs](http://www.w3schools.com/bootstrap/bootstrap_tabs_pills.asp)

I generate more html using JavaScript.

```html
<section>
  <div class="container-fluid">
    <div class="row">
      <div class="col-sm-4 col-xs-1"></div>
      <div class="col-sm-4 col-xs-10">
        <ul class="nav nav-tabs">
          <li class="active"><a data-toggle="tab" href="#home">All</a></li>
          <li><a data-toggle="tab" href="#menu1">Online</a></li>
          <li><a data-toggle="tab" href="#menu2">Offline</a></li>
        </ul>
        <div class="tab-content">
          <form action="" class="search-form">
            <div class="form-group has-feedback">
              <label for="search" class="sr-only">Search</label>
              <input type="text" class="form-control" name="search" id="search" placeholder="search">
              <span class="glyphicon glyphicon-search form-control-feedback"></span>
            </div>
          </form>
          <div id="home" class="tab-pane fade in active">
            <h3>All Streams</h3>
            <div>
              <ul class="list"></ul>
            </div>
          </div>
          <div id="menu1" class="tab-pane fade">
            <h3>Online Channels</h3>
            <div>
              <ul class="list2"></ul>
            </div>
          </div>
          <div id="menu2" class="tab-pane fade">
            <h3>Offline Channels</h3>
            <div>
              <ul class="list3"></ul>
            </div>
          </div>
          <div class="col-sm-4 col-xs-1"></div>
        </div>
      </div>
    </div>
  </div>
</section>
<!-- The footer -->
<footer>
  Copyright © Rafael J. Rodriguez 2015. All Rights Reserved
</footer>
```

## My CSS Code Snippets
The Search Bar has its own CSS so I just copied it.

```css
.search-form .form-group {
  float: right !important;
  transition: all 0.35s, border-radius 0s;
  width: 32px;
  height: 32px;
  background-color: #fff;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.075) inset;
  border-radius: 25px;
  border: 1px solid #ccc;
}
.search-form .form-group input.form-control {
  padding-right: 20px;
  border: 0 none;
  background: transparent;
  box-shadow: none;
  display: block;
}
.search-form .form-group input.form-contr ol::-webkit-input-placeholder {
  display: none;
}
.search-form .form-group input.form-control:-moz-placeholder {
  /* Firefox 18- */
  display: none;
}
.search-form .form-group input.form-control::-moz-placeholder {
  /* Firefox 19+ */
  display: none;
}
.search-form .form-group input.form-control:-ms-input-placeholder {
  display: none;
}
.search-form .form-group:hover, .search-form .form-group.hover {
  width: 100%;
  border-radius: 4px 25px 25px 4px;
}
.search-form .form-group span.form-control-feedback {
  position: absolute;
  top: -1px;
  right: -2px;
  z-index: 2;
  display: block;
  width: 34px;
  height: 34px;
  line-height: 34px;
  text-align: center;
  color: #3596e0;
  left: initial;
  font-size: 14px;
}
```

The rest was standard, it was the footer that has a new way to show other than the vh with min-height as I was doing before. this one is vertically and horizontally aligned.

```css
footer {
  background-color: black;
  color: gray;
  width: 100%;
  heigth: 50px;
  line-height: 50px;
  bottom: 0;
  position: relative;
  text-align: center;
}
```

## My JavaScript Code Snippets
The variables that will be used across the program.
- The Array with the accounts.
- The default logo in case the user does not have one.
- The API url for streams and users.
- A variable to store objects.

```
var accounts = ['freecodecamp', 'storbeck', 'terakilobyte', 'habathcx', 'RobotCaleb', 'thomasballinger', 'noobs2ninjas', 'beohoff', 'MedryBW', 'brunofin', 'comster404', 'quill18'];
var firstPassPos = 1;
var secondPassPos = 1;
var logo = 'http://i.imgur.com/vPEp5RQ.png';
var streams = 'https://api.twitch.tv/kraken/streams/';
var users = 'https://api.twitch.tv/kraken/users/';
var AccInfo = {};
```

I will use this constructor to create my objects with the info I want. It will be inside the `$(document).ready(function() {});` with everything else.

```js
function Account(name, logo, status, url, viewers, data) {
  this.name = name;
  this.logo = logo;
  this.status = status;
  this.url = url;
  this.viewers = viewers;
  this.data = data;
}
```

My render function will categorize, generate and populate the user lists. Now, there are a few tricky things, like working with a copy of the objects, and check with a regex, it can be passed but I pass the render without any parameters when I call it.

The main thing is to use a `for in` loop to check each object and generate the proper html and display it on the right tab with `$('.list').append(CAccInfo[stream].data);`

```js
function render(RegEx) {
  var CAccInfo;
  CAccInfo = AccInfo;
  if (typeof RegEx !== 'undefined') {
    var CAccInfo = AccInfo.filter(function(val) {
      return (val.match(RegEx));
    });
  }

  for (var stream in CAccInfo) {
    if (CAccInfo[stream].status === undefined) {
      CAccInfo[stream].data = '<div class= "user ' + CAccInfo[stream].name + '"><img class= \'logo\' src = "' + CAccInfo[stream].logo + '">' + CAccInfo[stream].name + '  <span class="glyphicon glyphicon-info-sign"></span><p class= \'stat\'>Offline</p></div>';
      $('.list3').append(CAccInfo[stream].data);
    } else if (CAccInfo[stream].status === 'Account Closed') {
      CAccInfo[stream].data = '<div class= "user ' + CAccInfo[stream].name + '"><img class= \'logo\' src = "' + CAccInfo[stream].logo + '">' + CAccInfo[stream].name + '  <span class="glyphicon glyphicon-warning-sign"></span><p class= \'stat\'>Account Closed</p></div>';

    } else {
      CAccInfo[stream].data = '<div class= "user ' + CAccInfo[stream].name + '"><img class= \'logo\' src = "' + CAccInfo[stream].logo + '">' + CAccInfo[stream].name + '  <span class="glyphicon glyphicon-ok-sign"></span> <a href="' + CAccInfo[stream].url + '" target="_blank"><p class= \'stat\'>' + CAccInfo[stream].status + '</p></a>' + '<p class= \'stat\'> <span class="glyphicon glyphicon-eye-open"></span> ' + CAccInfo[stream].viewers + '</p></div>';
      $('.list2').append(CAccInfo[stream].data);

    }

    $('.list').append(CAccInfo[stream].data);

  }
}
```

Then I have a function to get the user info, mostly the logo and proper username. It does call another function to get the stream information.

```js
function getUserInfo(CurrentName) {
  $.getJSON(users + CurrentName + '?callback=?', function(response) {
    if (response.logo === null) {
      CurrentName = new Account(response.display_name, logo);
    } else {
      CurrentName = new Account(response.display_name, response.logo);
    };

    firstPassPos++;
    AccInfo[CurrentName.name] = CurrentName;
    if (firstPassPos === accounts.length) {
      for (var key in AccInfo) {
        getStreamInfo(AccInfo[key]);
      }
    }
  });
}
```

This is the function that gets the stream information if it is online or provide the right information if it is offline or the account was closed.

```js
function getStreamInfo(currentStream) {
  $.getJSON(streams + currentStream.name + '?callback=?', function(feed) {
    secondPassPos++;
    if (feed.status === 422) {
      currentStream.status = 'Account Closed';
      if (secondPassPos === accounts.length) {
        render();
      }
    }

    if (feed.stream !== null && feed.stream !== undefined) {
      currentStream.status = feed.stream.channel.status;
      currentStream.url = feed.stream.channel.url;
      currentStream.viewers = feed.stream.viewers;
      if (secondPassPos === accounts.length) {
        render();
      }
    };
  });
}
```

Outside of the when ready function we have the code for the search bar. What it does basically is create a regex each time the user types on the bar, when there are characters it will hide everything that is not on the regex and when nothing is there it will show everything again.

```js
function search() {
  if ($('#search').val().length > 0) {
    // Display matching names by hiding anything that is not what we want from the  class= "user"
    var reg = new RegExp($('#search').val(), 'ig');
    $('.user').css('display', 'none');

    for (var a in AccInfo) {
      if (reg.test(AccInfo[a].name)) {
        $('.' + AccInfo[a].name).css('display', 'block');
      }
    }

  } else if ($('#search').val().length < 1) {
    // display everything again
    $('.user').css('display', 'block');
  }

  $('#search').unbind('keyup');
  $('#search').keyup(function() {
    search();
  });
}

$('#search').keyup(function() {
  search();
});
```

## Extras:
- [Search Bar](http://bootsnipp.com/snippets/featured/expanding-search-button-in-css)
- [KeyUp](http://www.w3schools.com/jquery/event_keyup.asp)
