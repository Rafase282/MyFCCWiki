# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
 Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/GeoffStorbeck/full/RPbGxZ/](http://codepen.io/GeoffStorbeck/full/RPbGxZ/).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
  In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can start a 25 minute pomodoro, and the timer will go off once 25 minutes has elapsed.
2. As a user, I can reset the clock for my next pomodoro.
3. As a user, I can customize the length of each pomodoro.

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets
The HTML part is very simple, nothing complicated. I keep using the same style I have used since my [portfolio](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Build-a-Personal-Portfolio-Webpage) which is 90%of view point for the main section and the rest for the footer. I like adding a footer to all my pages. So far I keep it simple.

This is the whole html file. I have a label and an interface to configure the break-time and work-time so you can setup the timer.

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Pomodoro Clock v2</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel='stylesheet prefetch' href='http://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css'>
  <link rel='stylesheet prefetch' href='https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css'>
  <link rel="stylesheet" href="css/style.css">
</head>

<body>

  <section class='container-fluid'>
    <div class="row">
      <div class="col-xs-12">
        <h1 class='text-primary'>Pomodoro Clock V2!</h1>
      </div>
    </div>

    <div class="row top-row">
      <div class="col-xs-6 text-primary">
        <h3>Break Length</h3>
      </div>
      <div class="col-xs-6 text-primary">
        <h3>Session Length</h3>
      </div>
    </div>

    <div class="row">
      <div class="col-xs-6">
        <button type="button" class="btn btn-link btn-sm" id="minus">-</button>
        <button type="button" class="btn btn-link btn-lg" id="break-time">5</button>
        <button type="button" class="btn btn-link btn-sm" id="plus">+</button>
      </div>
      <div class="col-xs-6">
        <button type="button" class="btn btn-link btn-sm" id="minus2">-</button>
        <button type="button" class="btn btn-link btn-lg" id="work-time">25</button>
        <button type="button" class="btn btn-link btn-sm" id="plus2">+</button>
      </div>
    </div>

    <div class="row top-row text-primary">
      <h2 id="status">Work!</h2>
      <canvas id="progress"></canvas>
      <div id="timer"></div>
    </div>
    <div class="row top-row text-primary bottom">
      <button type="button" id="start"> Start
      </button>
      <button type="button" id="pause"> Pause
      </button>
      <button type="button" id="reset"> Reset
      </button>
    </div>

  </section>

  <footer>
    <p>Copyright © Rafael J. Rodriguez 2015. All Rights Reserved</p>
  </footer>

  <script src='http://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js'></script>
  <script src='http://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js'></script>
  <script src="js/index.js"></script>

</body>

</html>
```

## My CSS Code Snippets
The CSS is also simple, a background color with things centered.

```css
h1, p, .row {
  text-align: center;
  font-size: 130%;
}
section {
  min-height: 90vh;
}
footer {
  min-height: 10vh;
  padding-top: 30px;
  padding-bottom: 1px;
  background-color: black;
  color: #e4f1fe;
}
body {
  position: relative;
  background-color: #ACECF7;
}
.top-row {
  margin-top: 50px
}
.bottom {
  margin-bottom: 50px;
}
```

## My JavaScript Code Snippets
This is where the magic happens!

Firs I setup my global variables for jQuery:

```js
$workT = $('#work-time');
$breakT = $('#break-time');
$status = $('#status');
```

Might not be much but is a way to practice how to make variables using jQuery and also to shorten the things I have to type.

Next is to add code to control the minutes that will be added or removed.

```js
// Controls for Break Length
$('#minus').click(function() {
  $status.text('Break!');
  if (+$breakT.text() > 1) {
    $breakT.text(+$breakT.text() - 1);
  }
});

$('#plus').click(function() {
  $status.text('Break!');
  $breakT.text(+$breakT.text() + 1);
});

// Controls for Session Length
$('#minus2').click(function() {
  $status.text('Work!');
  if (+$workT.text() > 1) {
    $workT.text(+$workT.text() - 1);
  }
});

$('#plus2').click(function() {
  $status.text('Work!');
  $workT.text(+$workT.text() + 1);
});
```

I didn't want to have zero minutes as that would be silly so I made sure to check when removing time to make sure that it cannot be set to zero or anything lower than one minute.

As for the alarm part, I used HTML5 to take care of that.

```js
var audio = new Audio('http://soundbible.com/grab.php?id=1377&type=mp3');

function beep() {

  audio.play();
}
```

It is important to have the new audio outside the function, before I had it inside and it was creating a new sound every time it function was called which was not needed.

Then because I wanted double digits all the time I had to create a function to keep double digits no matter what.

```js
function pad(val) {
  return ('00' + val).slice(-2);
}
```

The I'm creating a function to update the display with the right time. This needs to be used together with the update function.

```js
var el = document.getElementById('timer');

function updateDisplay(t) {
  var hours = Math.floor(t / 3600);
  t -= hours * 3600;
  var minutes = Math.floor(t / 60);
  t -= minutes * 60;
  var seconds = Math.floor(t);
  el.innerHTML = pad(hours) + ':' + pad(minutes) + ':' + pad(seconds);
}
```

Before anything, lets setup the timer:

```js
time = 0;
updateDisplay(time);
var running = true;
var tlast = (new Date()).getTime();
```

using `new Date()` is crucial!

NOw, the update function is very meaty as most of the code is here, given that it is the core of the program.

```js
function update() {
  if (time <= 0.0) { // Already done
    return;
  }

  var tnow = (new Date()).getTime();
  var dt = (tnow - tlast) / 1000.0;
  tlast = tnow;
  time -= dt;
```

This part is to get the right color for the specific timer running for the progress animation.

```js
  if ($status.text() === 'Work!') {
    totalTime = ($workT.text() * 60);
    water = 'rgba(25, 139, 201, 1)';
  }

  if ($status.text() === 'Break!') {
    totalTime = ($breakT.text() * 60);
    water = 'rgba(255, 0, 0, 1)';
  }
```

Takes the time and turns it into a value between 0 and 1 for the progress circle animation.

  `fraction = 1 - (time / totalTime);``

Calls the updated animation.

```js
  $('#progress').waterbubble({
    data: fraction,
    animation: false,
    waterColor: water,
  });
```

If the time has finished then we need to switch to the other timer and also change the label and sound the alarm.

```js
  if (time <= 0.0) {
    if ($status.text() === 'Work!') {
      beep();
      $status.text('Break!');
      time = $breakT.text() * 60;

    } else {
      beep();
      $status.text('Work!');
      time = $workT.text() * 60;

    }
  }
```

Then we keep things goin on!

```js
  updateDisplay(time);
  if (running) {
    requestAnimationFrame(update);
  }

}
```

The run function is what gets the timer to start up and work things. I use `requestAnimationFrame` for this version. I have another version that is not quited finished with regards to the animations but the functionality is there using `setinterval`

```js
function run() {
  $status.text('Work!');
  if (time <= 0.0) {
    time = $workT.text() * 60;
  }

  tlast = (new Date()).getTime();
  running = true;
  requestAnimationFrame(update);
}
```

The easiest part due the the way the code works is to pause the timer.

```js
function pause() {
  running = false;
}
```

When stopping the timer, I want to reset everything so I have to take care of many things like the displayed time, the labels, and then default timers along with resetting the animation.

```js
function stop() {
  running = false;
  time = 0;
  el.innerHTML = '00:00:00';
  $status.text('Work!');
  $workT.text(25);
  $breakT.text(5);
  $('#progress').waterbubble({
    data: 0.0,
    animation: false,
    waterColor: 'rgba(25, 139, 201, 1)',
  });
}
```

We are almost done, I just have to set the buttons with their onclick call.

```js
var bStart = document.getElementById('start');
var bPause = document.getElementById('pause');
var bReset = document.getElementById('reset');

bStart.onclick = run;
bPause.onclick = pause;
bReset.onclick = stop;
```

There is one last thing, setting up the progress bar animation. The first part was linking the files which I did on the html part, now we need the manual configuration.

```js
$('#progress').waterbubble(

  {

    // bubble size
    radius: 100,

    // border width
    lineWidth: undefined,

    // data to present
    data: 0.0,

    // color of the water bubble
    waterColor: 'rgba(25, 139, 201, 1)',

    // text color
    textColor: 'rgba(06, 85, 128, 0.8)',

    // custom font family
    font: '',

    // show wave
    wave: true,

    // custom text displayed inside the water bubble
    txt: undefined,

    // enable water fill animation
    animation: false,

  });
```

# First version
If you want to check my previous version I will provide a link [here](https://github.com/Rafase282/My-FreeCodeCamp-Code/tree/master/Basic%20Front%20End%20Development%20Projects/Pomodoro%20Clock) however, I will not go on and explain he code.

## Credit
I received help from many people, in particular @mutantspore with the progress bar that I got from here [Liquid Bubble](http://www.jqueryscript.net/chart-graph/Customizable-Liquid-Bubble-Chart-With-jQuery-Canvas.html)

The base for this code was thanks to @noob247365 who showed me how to implement the `requestAnimationFrame`
