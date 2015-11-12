# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

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

## My HTML Code Snippets

```html
<section>
  <div class="app-container">
    <div data-tile="4" class="tiles green"> </div>
    <div data-tile="1" class="tiles red"> </div>
    <div data-tile="3" class="tiles yellow"> </div>
    <div data-tile="2" class="tiles blue"> </div>
    <div class="board">
      <div class="circle">
        <div class="brand">
          <span>Simon</span>
        </div>
        <div class="middle-row">
          <div class="display">
            <div class="round-number"></div>
            <span class="label">ROUND</span>
          </div>
          <div class="start">
            <div class="start-button"></div>
            <span class="label">START</span>
          </div>
          <div class="strict">
            <div class="strict-button"></div>
            <span class="label">STRICT</span>
          </div>
        </div>
        <div class="bottom-row">
          <span class="off">OFF</span>
          <div class="power-bg">
            <div class="power-button float-left"></div>
          </div>
          <span class="on">ON</span>
        </div>
      </div>
    </div>
  </div>
</section>
```

## My CSS Code Snippets

```css
.button-bright {
  background-image: none !important;
}

.float-right {
  float: right;
}

.float-left {
  float: left;
}

.flex-centered, section, section .app-container, section .app-container .board, section .app-container .board .circle, section .app-container .board .circle .brand, section .app-container .board .circle .bottom-row {
  display: flex;
  align-items: center;
  justify-content: center;
}

.boxes, section .app-container .green, section .app-container .red, section .app-container .yellow, section .app-container .blue {
  height: 50%;
  width: 50%;
  border: 20px solid black;
  background-image: linear-gradient(to top, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.4));
  background-blend-mode: darken;
}

.brighten {
  background-image: linear-gradient(to top, rgba(255, 255, 255, 0.6), rgba(211, 211, 211, 0.4)) !important;
  background-blend-mode: screen !important;
}

section {
  position: relative;
  height: 90vh;
  width: 100%;
}

section .app-container {
  flex-wrap: wrap;
  position: relative;
  height: 70vmin;
  width: 70vmin;
}

section .app-container .green {
  background-color: rgba(0, 128, 0, 0.8);
  border-top-left-radius: 100%;
  border-right: 10px solid black;
  border-bottom: 10px solid black;
}

section .app-container .red {
  background-color: rgba(255, 0, 0, 0.85);
  border-top-right-radius: 100%;
  border-left: 10px solid black;
  border-bottom: 10px solid black;
}

section .app-container .yellow {
  background-color: rgba(255, 255, 0, 0.8);
  border-bottom-left-radius: 100%;
  border-right: 10px solid black;
  border-top: 10px solid black;
}

section .app-container .blue {
  background-color: rgba(0, 0, 255, 0.85);
  border-bottom-right-radius: 100%;
  border-top: 10px solid black;
  border-left: 10px solid black;
}

section .app-container .board {
  position: absolute;
  top: 25%;
  left: 25%;
  height: 50%;
  width: 50%;
  border-radius: 50%;
}

section .app-container .board .circle {
  flex-wrap: wrap;
  height: 100%;
  width: 100%;
  background-image: none;
  background-color: white;
  border: 10px solid black !important;
  border-radius: 50%;
  /* BRAND NAME */
  /* MAIN GAME CONTROLS */
  /* POWER BUTTON */
}

section .app-container .board .circle .brand {
  width: 100%;
  height: 40%;
}

section .app-container .board .circle .brand span {
  font-size: 7.5vmin;
  font-weight: bold;
  color: black;
  padding: 0;
  margin: 0;
}

section .app-container .board .circle .middle-row {
  display: flex;
  justify-content: space-around;
  width: 95%;
  height: 35%;
  margin: 0;
}

section .app-container .board .circle .middle-row .display, section .app-container .board .circle .middle-row .start, section .app-container .board .circle .middle-row .strict {
  position: relative;
  height: 61.8%;
  width: 30%;
  box-sizing: border-box;
}

section .app-container .board .circle .middle-row span.label {
  position: absolute;
  width: 100%;
  bottom: -3vmin;
  left: 0;
  font-size: 1.5vmin;
  color: black;
  text-align: center;
}

section .app-container .board .circle .middle-row .display {
  display: inline-block;
  background-color: rgba(0, 0, 0, 0.7);
  border: 3px solid rgba(0, 0, 0, 0.8);
  border-radius: 10%;
}

section .app-container .board .circle .middle-row .start {
  display: inline-flex;
  justify-content: center;
  align-items: center;
}

section .app-container .board .circle .middle-row .start .start-button {
  background-color: rgba(139, 0, 0, 0.85);
  height: 5vmin;
  width: 5vmin;
  border: 5px solid rgba(0, 0, 0, 0.8);
  border-radius: 50%;
}

section .app-container .board .circle .middle-row .strict {
  display: inline-flex;
  justify-content: center;
  align-items: center;
}

section .app-container .board .circle .middle-row .strict .strict-button {
  background-color: rgba(255, 255, 0, 0.85);
  background-image: linear-gradient(to top, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.4));
  background-blend-mode: darken;
  height: 5vmin;
  width: 5vmin;
  border: 5px solid rgba(0, 0, 0, 0.8);
  border-radius: 50%;
}

section .app-container .board .circle .bottom-row {
  height: 25%;
  width: 100%;
}

section .app-container .board .circle .bottom-row .power-bg {
  display: block;
  height: 3vmin;
  width: 25%;
  padding: 1px;
  background-color: rgba(0, 0, 0, 0.8);
}

section .app-container .board .circle .bottom-row .power-button {
  height: 100%;
  width: 45%;
  background-color: pink;
}

section .app-container .board .circle .bottom-row .on {
  margin-left: 0.5vmin;
  font-size: 2vmin;
  font-weight: 600;
}

section .app-container .board .circle .bottom-row .off {
  margin-right: 0.5vmin;
  font-size: 2vmin;
  font-weight: 600;
}
```

## My JavaScript Code Snippets

```js


```

## Links
- [Building Simon Game JavaScript](http://codeplanet.io/building-simon-says-javascript/)
- [CSS Half Circle](http://stackoverflow.com/questions/22415651/half-circle-with-css-border-outline-only)
- [Playing Audio With JavaScript](http://stackoverflow.com/questions/9419263/playing-audio-with-javascript)
