# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/alex-dixon/full/JogOpQ/](http://codepen.io/alex-dixon/full/JogOpQ/).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can play a game of Tic Tac Toe with the computer.
2. As a user, I can never actually win against the computer - at best I can tie.
3. As a user, my game will reset as soon as it's over so I can play again.
4. As a user, I can choose whether I want to play as X or O.

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets


```html
<section class="container">
  <h1>Janken pon!</h1>
  <h3>Play as
      <button type="button" class="btn btn-primary icon" id="X">X</button>
      or
      <button type="button" class="btn btn-primary icon" id="O">O</button>
      ?
    </h3>
  <div class="board">
    <div class="row">
      <div class="col-xs-1 field" id="r1c1"></div>
      <div class="col-xs-1 field" id="r1c2"></div>
      <div class="col-xs-1 field" id="r1c3"></div>
    </div>
    <div class="row">
      <div class="col-xs-1 field" id="r2c1"></div>
      <div class="col-xs-1 field" id="r2c2"></div>
      <div class="col-xs-1 field" id="r2c3"></div>
    </div>
    <div class="row">
      <div class="col-xs-1 field" id="r3c1"></div>
      <div class="col-xs-1 field" id="r3c2"></div>
      <div class="col-xs-1 field" id="r3c3"></div>
    </div>
  </div>
  <h3> Score!
      <br>
      <p>Player <span class="badge player X">0</span>
      Machine <span class="badge machine O">0</span></p>
    </h3>
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
  </a></p>
</footer>
```

## My CSS Code Snippets

```css
h1,
h3 {
  text-align: center;
  font-family: "Lucida Console", Monaco, monospace;
  color: #663300;
}

section {
  padding-top: 10px;
  padding-bottom: 10px;
  color: #fff;
  bottom: 10px;
}

body {
  background-image: url('http://www.aapopuskala.fi/_img/paper.jpg');
}

footer {
  background-color: black;
  color: gray;
  line-height: 20px;
  padding-top: 10px;
  padding-bottom: 6px;
  position: fixed;
  text-align: center;
  font-family: cursive, sans-serif;
  width: 100%;
  bottom: 0;
}

.field {
  border-color: black;
  width: 100px;
  height: 100px;
  border-width: 5px;
}

.board {
  margin: 40px auto;
  display: block;
  width: 295px;
}

.ico {
  margin: -10px auto;
  display: block;
  color: black;
  font-size: 80px;
}

.winningRow {
  background-color: red;
}

#r2c1 {
  border-style: solid solid solid none;
}

#r2c2 {
  border-style: solid none solid none;
}

#r2c3 {
  border-style: solid none solid solid;
}

#r1c1 {
  border-style: none solid none none;
}

#r1c3 {
  border-style: none none none solid;
}

#r3c1 {
  border-style: none solid none none;
}

#r3c3 {
  border-style: none none none solid;
}
```

## My JavaScript Code Snippets
I tried to follow the functional programming principles as I remember them.

- **MarkPosition** will lock the position that was clicked to prevent changes, call `DrawIcon`, `WinCheck` and update the number of moves made before changing the current player with `PToggler` and then make the machine move as long as the game is not over and the current number of moves is even.
- **SetIcon** will set the icon to the one clicked and will not change it until the page is refreshed. Player plays first.
- **PToggler** just changes from one player to the next using a ternary operator.
- **DrawChecker** will check for a draw by making sure there are no more possible moves and if there are none, it will wait a second before clearing the board.
- **WinCheck** will check for all possible ways to win for the current player and if one is found declare that the game is over to avoid the machine or player for making a quick move if possible and it will wait a second to update the score. It calls `DrawChecker` as the default behavior if no wins are found.
- **UpdateScore** will add one point to the player that won the game and then clear the board.
- **DrawLine** will just make the winning line noticeable so the player has a better change of detecting it.
- **Clear** will pretty much undo any code to prevent changes on the board, winning line, and icons. Basically a reset, but you can't switch icons still.
- **DrawIcon** will just add the current player's icon to the right place.
- **MachineAI** is the artificial intelligence for the machine. Currently a very basic implementation.


```js
// Declare Players
var player = 'X';
var machine = 'O';
var curPlayer = player;

// Other needed Variables
var gameOver = false;
var lockIcon = false;
var moves = 1;

$('.field').on('click', MarkPosition);

$('.icon').on('click', SetIcon);

// Set the icon for the players
function SetIcon() {
  if ($(this).attr('id') === 'X' && !lockIcon) {
    player = 'X';
    machine = 'O';
    lockIcon = true;
  } else if ($(this).attr('id') === 'O' && !lockIcon) {
    player = 'O';
    machine = 'X';
    lockIcon = true;
  }

  curPlayer = player;

  // Adjust the right setting
  $('.player').removeClass('X');
  $('.player').removeClass('O');
  $('.machine').removeClass('O');
  $('.machine').removeClass('X');
  $('.player').addClass(player);
  $('.machine').addClass(machine);
};

// Player Toggler
function PToggler(cplayer) {
  cplayer === player ? curPlayer = machine : curPlayer = player;
};

// Check for a draw
function DrawChecker() {
  if (moves === 9) {
    setTimeout(Clear, 1000);
  }
};

// Check for a win
function WinCheck() {
  switch (true) {
    case $('#r1c1').text() === curPlayer && $('#r1c2').text() === curPlayer &&
    $('#r1c3').text() === curPlayer:
      DrawLine('#r1c1', '#r1c2', '#r1c3');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r2c1').text() === curPlayer && $('#r2c2').text() === curPlayer &&
    $('#r2c3').text() === curPlayer:
      DrawLine('#r2c1', '#r2c2', '#r2c3');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r3c1').text() === curPlayer && $('#r3c2').text() === curPlayer &&
    $('#r3c3').text() === curPlayer:
      DrawLine('#r3c1', '#r3c2', '#r3c3');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r1c1').text() === curPlayer && $('#r2c1').text() === curPlayer &&
    $('#r3c1').text() === curPlayer:
      DrawLine('#r1c1', '#r2c1', '#r3c1');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r1c2').text() === curPlayer && $('#r2c2').text() === curPlayer &&
    $('#r3c2').text() === curPlayer:
      DrawLine('#r1c2', '#r2c2', '#r3c2');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r1c3').text() === curPlayer && $('#r2c3').text() === curPlayer &&
    $('#r3c3').text() === curPlayer:
      DrawLine('#r1c3', '#r2c3', '#r3c3');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r1c1').text() === curPlayer && $('#r2c2').text() === curPlayer &&
    $('#r3c3').text() === curPlayer:
      DrawLine('#r1c1', '#r2c2', '#r3c3');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    case $('#r1c3').text() === curPlayer && $('#r2c2').text() === curPlayer &&
    $('#r3c1').text() === curPlayer:
      DrawLine('#r1c3', '#r2c2', '#r3c1');
      gameOver = true;
      setTimeout(UpdateScore, 1000);
      break;
    default:

      DrawChecker();
  }
};

// Clarify the winning hand
function DrawLine(pos1, pos2, pos3) {
  var $pos1 = $(pos1);
  var $pos2 = $(pos2);
  var $pos3 = $(pos3);
  $pos1.addClass('winningRow');
  $pos2.addClass('winningRow');
  $pos3.addClass('winningRow');

  // Fix for the race problem of JS vs jQuery toggling the current player befre the score is changed.
  PToggler(curPlayer);
}

// Updates the score and clears the board by calling the Clear function.
function UpdateScore() {
  $('.' + curPlayer).text(+$('.' + curPlayer).text() + 1);
  Clear();
}

//Clear the board
function Clear() {
  // Clear board
  $('.field').empty();

  // Allow board to be clickable again
  $('.field').removeClass('clicked');

  // Clear winner line
  $('div').removeClass('winningRow');

  // Reset Moves
  moves = 1;

  // Reset gameover
  gameOver = false;

  // Reset Player to chosen one.
  SetIcon();

};

// FUnctiont o draw icon on the board.
function DrawIcon(id) {
  $('#' + id).html('<p class="ico">' + curPlayer + '</p>');
}

//Mark position clicked
function MarkPosition() {
  lockIcon = true;
  var id = $(this).attr('id');

  // Prevent changing already selected grid
  if (!$('#' + id).hasClass('clicked')) {
    $('#' + id).addClass('clicked');

    // Add Icon to the board
    DrawIcon(id);

    WinCheck();

    // Mark number of moves
    moves += 1;

    PToggler(curPlayer);

    // Add Icon to the board for machine
    if (gameOver === false && moves % 2 === 0) {
      MachineAI();
      WinCheck();
      moves += 1;
      PToggler(curPlayer);
    }
  }
};

// just place moves on the board, bare minimum implementation
function MachineAI() {
  switch (true) {
    case $('#r1c1').text() !== player && $('#r1c1').text() !== machine:
      DrawIcon('r1c1');
      break;
    case $('#r1c2').text() !== player && $('#r1c2').text() !== machine:
      DrawIcon('r1c2');
      break;
    case $('#r1c3').text() !== player && $('#r1c3').text() !== machine:
      DrawIcon('r1c3');
      break;
    case $('#r2c1').text() !== player && $('#r2c1').text() !== machine:
      DrawIcon('r2c1');
      break;
    case $('#r2c2').text() !== player && $('#r2c2').text() !== machine:
      DrawIcon('r2c2');
      break;
    case $('#r2c3').text() !== player && $('#r2c3').text() !== machine:
      DrawIcon('r2c3');
      break;
    case $('#r3c1').text() !== player && $('#r3c1').text() !== machine:
      DrawIcon('r3c1');
      break;
    case $('#r3c2').text() !== player && $('#r3c2').text() !== machine:
      DrawIcon('r3c2');
      break;
    case $('r3c3').text() !== player && $('#r2c3').text() !== machine:
      DrawIcon('r3c3');
      break;
  }
};
```

## Links
- [MiniMax Algorithm](http://neverstopbuilding.com/minimax)
- [More MiniMax](http://www3.ntu.edu.sg/home/ehchua/programming/java/JavaGame_TicTacToe_AI.html)
