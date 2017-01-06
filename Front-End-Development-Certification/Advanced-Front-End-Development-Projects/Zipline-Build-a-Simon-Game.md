# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/Em-Ant/full/QbRyqq/](http://codepen.io/Em-Ant/full/QbRyqq/).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I am presented with a random series of button presses.
2. As a user, each time I input a series of button presses correctly, I see the same series of button presses but with an additional step.
3. As a user, I hear a sound that corresponds to each button both when the series of button presses plays, and when I personally press a button.
4. As a user, if I press the wrong button, I am notified that I have done so, and that series of button presses starts again to remind me of the pattern so I can try again.
5. As a user, I can see how many steps are in the current series of button presses.
6. As a user, if I want to restart, I can hit a button to do so, and the game will return to a single step.
7. As a user, I can play in strict mode where if I get a button press wrong, it notifies me that I have done so, and the game restarts at a new random series of button presses.
8. As a user, the tempo of the game speeds up incrementally on the 5th, 9th and 13th step.
9. As a user, I can win the game by getting a series of 20 steps correct. I am notified of my victory, then the game starts over.

## Hint:
Here are mp3s you can use for each button:

 [https://s3.amazonaws.com/freecodecamp/simonSound1.mp3](https://s3.amazonaws.com/freecodecamp/simonSound1.mp3), [https://s3.amazonaws.com/freecodecamp/simonSound2.mp3](https://s3.amazonaws.com/freecodecamp/simonSound2.mp3), [https://s3.amazonaws.com/freecodecamp/simonSound3.mp3](https://s3.amazonaws.com/freecodecamp/simonSound3.mp3), [https://s3.amazonaws.com/freecodecamp/simonSound4.mp3](https://s3.amazonaws.com/freecodecamp/simonSound4.mp3).

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

I worked together with @guylemon on this one. I was able to get familiar with sass and jade as it is his choice for html and css.

## My HTML Code Snippets

```jade
section
  .win.hidden YOU WIN!
    .modal-buttons
      span.play-again PLAY AGAIN
      span.quit QUIT
  .lose.hidden OH NO!
    .modal-buttons
      span.play-again PLAY AGAIN
      span.quit QUIT
  // the game
  .app-container
    .tiles.green(data-tile='4')
    .tiles.red(data-tile='1')
    .tiles.yellow(data-tile='3')
    .tiles.blue(data-tile='2')
    .board
      .circle
        .brand
          span Simon
          span.reg &#174;
        .middle-row
          .display
            .round-number
            span.label ROUND
          .start
            .start-button
            span.label#start START
          .strict
            .strict-button
            span.label STRICT
        .bottom-row
          span.off OFF
          .power-bg
            .power-button.float-left
          span.on ON
          // TO-DO: COME UP WITH A PROPER FOOTER FOR THE TEAM
 footer
 p Copyright © Rafael J. Rodriguez & #[a(href='mailto: guy@guylemon.com') Guy Lemon] 2015. All Rights Reserved
 p
   a(href='mailto:rafase282@gmail.com')
     i.fa.fa-envelope.fa-fw
   a(href='https://github.com/Rafase282',target='_blank')
     i.fa.fa-github.fa-fw
   a(href='https://www.linkedin.com/in/rafase282',target='_blank')
     i.fa.fa-linkedin
   a(href='http://codepen.io/Rafase282',target='_blank')
     i.fa.fa-codepen
   a(href='https://rafase282.wordpress.com',target='_blank')
     i.fa.fa-wordpress
   a(href='https://rafase282.wordpress.com',target='_blank')  (
     i.fa.fa-fire.fa-fw )
```

## My CSS Code Snippets

```sass
//FONTS
@import url(https://fonts.googleapis.com/css?family=Alfa+Slab+One)
$font-stack: 'Alfa Slab One', cursive


//VARIABLES
$simon-height: 70vmin

/* colors & borders */
$red: rgba(255, 54, 48, 1)
$burgundy: rgba(35, 11, 10, 0.85)
$blue: rgba(54, 97, 196, 1)
$light-blue: rgba(89, 196, 206, 1)
$green: rgba(41, 217, 53, 1)
$yellow: rgba(255, 241, 48, 1)
$gray: rgba(50, 50, 50, 1)
$shadow: rgba(10, 10, 10, 1)
$bg-shadow: linear-gradient(to top, rgba($gray, 0.2), rgba($shadow, 0.3))
$tile-border: 1.5vmin solid $gray
$outer-border: 3.2vmin solid $gray

//HELPER CLASSES
.button-bright
  background-image: none !important
.float-right
  float: right
.float-left
  float: left
  //toggle this
.flex-centered
  display: flex
  align-items: center
  justify-content: center
.boxes
  height: 50%
  width: 50%
  border: $outer-border
  box-shadow: 1vmin 1vmin 3vmin $shadow
  background-image: $bg-shadow
  background-blend-mode: darken

.brighten
  background-image: linear-gradient(to top, rgba(white, 0.6), rgba(lightgray, 0.4)) !important
  background-blend-mode: screen !important

//APP STYLING
section
  @extend .flex-centered
  position: relative
  height: 90vh
  width: 100%
  background:
    image: url(https://cloud.githubusercontent.com/assets/13574207/11134180/7f5e3224-8960-11e5-924d-463c78063cb9.jpg)
    size: cover
    position: center
    /*blend-mode: overlay
    //color: rgba($shadow 0.5)*/
  .win, .lose
    position: absolute
    height: 100%
    width: 100%
    top: 0
    left: 0
    display: flex
    align-items: center
    justify-content: center
    background-color: rgba($blue, 0.8) + rgba(0,0,0,0.8)
    font-size: 11vmin
    font-weight: bold
    color: white
    letter-spacing: -0.5vmin
    text-shadow: 1vmin 1vmin 6vmin $shadow
    z-index: 1
    .modal-buttons
      display: flex
      align-items: center
      justify-content: space-around
      position: absolute
      top: 60%
      left: 25%
      width: 50%
      height: 10%
      //background-color: pink

      .play-again, .quit
        @extend .flex-centered
        background-image: $bg-shadow
        background-color: $green
        height: 61.8%
        width: 40%
        max-width: 175px
        border-radius: 1vmin
        box-shadow: 0.4vmin 0.4vmin 1vmin $shadow
        color: black
        text-shadow: none
        font-size: 3vmin
        font-weight: 500
        letter-spacing: 0

        &:active
          box-shadow: none



  .app-container
    @extend .flex-centered
    flex-wrap: wrap
    position: relative
    height: $simon-height
    width: $simon-height
    //border: solid 20px black
    //border-radius: 50%

    //TILES
    .green
      @extend .boxes
      background-color: $green
      border-top-left-radius: 100%
      border-right: $tile-border
      border-bottom: $tile-border


    .red
      @extend .boxes
      background-color: $red
      border-top-right-radius: 100%
      border-left: $tile-border
      border-bottom: $tile-border

    .yellow
      @extend .boxes
      background-color: $yellow
      border-bottom-left-radius: 100%
      border-right: $tile-border
      border-top: $tile-border

    .blue
      @extend .boxes
      background-color: $blue
      border-bottom-right-radius: 100%
      border-top: $tile-border
      border-left: $tile-border

    //CENTER SECTION
    .board
      @extend .flex-centered
      position: absolute
      top: 25%
      left: 25%
      height: 50%
      width: 50%
      //border: solid 1px red
      border-radius: 50%
      //MIDDLE PORTION
      .circle
        @extend  .flex-centered
        flex-wrap: wrap
        height: 100%
        width: 100%
        background-image: none
        background-color: white
        border: $tile-border /*!important*/
        border-radius: 50%
        box-shadow: 0.2vmin 0.2vmin 0.5vmin $shadow



        /* BRAND NAME */
        .brand
          @extend .flex-centered
          //background-color: pink
          width: 100%
          height: 40%


          span
            //border: solid 1px black
            font-size: 6vmin
            font-family: $font-stack
            color: black
            padding: 0
            margin-top: 3vmin
            //background-color: pink
          .reg
            font-family: Helvetica, sans-serif
            font-size: 2vmin
            margin-bottom: 2vmin

        /* MAIN GAME CONTROLS */
        .middle-row
          display: flex
          justify-content: space-around
          //background-color: pink
          width: 90%
          height: 33%
          margin: 0
          .display, .start, .strict
            position: relative
            //border: 1px solid black
            height: 61.8%
            width: 30%
            box-sizing: border-box
          span.label
            //border: 1px solid red
            position: absolute
            width: 100%
            bottom: -2.2vmin
            left: 0
            padding: 0
            margin: 0
            font-size: 1.5vmin
            color: black
            text-align: center

          /*ROUND DISPLAY  */
          .display
            display: inline-flex
            justify-content: center
            align-items: center
            background-color: $burgundy
            border: 3px solid $shadow
            border-radius: 10%
            .round-number
              color: $burgundy + rgba(175, 44, 44, 0.85)
              font-size: 4.5vmin

          /* START BUTTON */
          .start
            display: inline-flex
            justify-content: center
            align-items: center
            .label
              bottom: -1.88vmin
            .start-button
              background-color: $red
              height: 5vmin
              width: 5vmin
              border: 0.6vmin solid $gray
              border-radius: 50%
              box-shadow: 0.2vmin 0.2vmin 0.4vmin $shadow

          /* STRICT BUTTON */
          .strict
            display: inline-flex
            justify-content: center
            align-items: center
            .label
              bottom: -1.88vmin
            .strict-button
              background-color: $yellow - rgb(44,44,44)
              height: 5vmin
              width: 5vmin
              border: 0.6vmin solid $gray
              border-radius: 50%
              box-shadow: 0.2vmin 0.2vmin 0.4vmin $shadow

        /* POWER BUTTON */
        .bottom-row
          @extend .flex-centered
          height: 23%
          width: 100%

          .power-bg
            display: block
            height: 3vmin
            width: 20%
            padding: 1px
            background-color: $shadow
            border-radius: 0.5vmin
          .power-button
            height: 100%
            width: 50%
            background-color: $light-blue
            border-radius: 0.5vmin
            border: 0.3vmin solid $gray
          /* POWER BUTTON LABELS */
          .on
            margin-left: .3vmin
            font-size: 1.5vmin
            font-weight: 600

          .off
            margin-right: .5vmin
            font-size: 1.5vmin
            font-weight: 600

// FOOTER
footer
  background-color: black
  color: gray
  line-height: 20px
  padding-top: 10px
  padding-bottom: 6px
  position: fixed
  text-align: center
  font-family: cursive, sans-serif
  width: 100%
  bottom: 0
```

## My JavaScript Code Snippets

This is part of the code, this handles the player input when playing. For the rest of the code just switch to the code version of this repo where the full app is stored.

```js
function playerMove() {
  // Time for the user to play
  if (power == true && lock == true) {
    var position = $(this).data('tile');
    player.push(position);

    //If the player entry is incorrect at any point, play the buzzersound and start the sequence again. [1,2,3,4]
    if (player[player.length - 1] !== sequence[player.length - 1]) {
      beep('audioBuzzer');
      strictON();
    } else {
      var audio = 'audio' + $(this).data('tile');
      beep(audio);

      // exp = while sequence is greater than player or it is one.
      var exp = sequence.length === player.length;
      if (exp) {
        // If it is round 20, set win to true and call gameover.
        if (round === 20) {
          win = true;
          gameOver();
        } else {
          NewRound();
        }
      }
    }
  }
}
```

## Links
- [Building Simon Game JavaScript](http://codeplanet.io/building-simon-says-javascript/)
- [CSS Half Circle](http://stackoverflow.com/questions/22415651/half-circle-with-css-border-outline-only)
- [Playing Audio With JavaScript](http://stackoverflow.com/questions/9419263/playing-audio-with-javascript)
- [Cloning arrays, fastest way](http://jsperf.com/new-array-vs-splice-vs-slice/113)
