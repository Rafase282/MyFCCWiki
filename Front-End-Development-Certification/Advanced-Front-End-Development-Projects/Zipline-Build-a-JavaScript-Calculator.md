# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/GeoffStorbeck/full/zxgaqw](http://codepen.io/GeoffStorbeck/full/zxgaqw).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can add, subtract, multiply and divide two numbers.
2. I can clear the input field with a clear button.
3. I can keep chaining mathematical operations together until I hit the equal button, and the calculator will tell me the correct output.

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets
I used a table generator that I found to make the layout of the calculator using a custom table. Then I added my buttons and all the code needed.

```html
<section>
  <h1>FreeCodeCamp</h1>
  <h2>Calculator</h2>
  <div class="Frame">
    <div class="tg-wrap">
      <table class="tg">
        <tr>
          <th class="tg-a8gl" colspan="4" id="result"></th>
        </tr>
        <tr>
          <td class="tg-ftb4">
            <button type="button" class="red" id="clear-all">AC</button>
          </td>
          <td class="tg-lewp">
            <button type="button" id="op">(</button>
          </td>
          <td class="tg-ljlu">
            <button type="button" id="clo">)</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="division">÷</button>
          </td>
        </tr>
        <tr>
          <td class="tg-6dgb">
            <button type="button" id="seven">7</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="eight">8</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="nine">9</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="mult">x</button>
          </td>
        </tr>
        <tr>
          <td class="tg-6dgb">
            <button type="button" id="four">4</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="five">5</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="six">6</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="minus">-</button>
          </td>
        </tr>
        <tr>
          <td class="tg-6dgb">
            <button type="button" id="one">1</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="two">2</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="three">3</button>
          </td>
          <td class="tg-6dgb">
            <br>
            <button type="button" class="plus" id="plus">+</button>
          </td>
        </tr>
        <tr>
          <td class="tg-6dgb">
            <button type="button" id="zero">0</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="dec">.</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="mod">%</button>
          </td>
          <td class="tg-6dgb">
            <button type="button" id="eq">=</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</section>
```

## My CSS Code Snippets

```css
h2 {
  text-align: center;
  font-family: cursive, sans-serif;
  color: #663300;
}
h1 {
  font-size: 52px;
  text-align: center;
  font-family: cursive, sans-serif;
  color: #663300;
}
section {
  min-height: 90vh;
  padding-top: 10px;
  padding-bottom: 10px;
  color: #fff;
  background-color: #00bcd4;
  bottom: 10px;
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

/*Calculator*/

.red {
  background-color: red;
  border-color: red;
}
.plus {
  margin-top: -20px;
}
button {
  background-color: black;
  border-color: black;
  width: 100%;
  padding: 20px 30px;
}
.tg {
  border-collapse: collapse;
  border-spacing: 0;
  border-color: #999;
  margin: 0 auto;
}
.tg td {
  font-family: Arial, sans-serif;
  font-size: 14px;
  border-style: solid;
  border-width: 1px;
  overflow: hidden;
  word-break: normal;
  border-color: #999;
  color: #444;
  background-color: #F7FDFA;
}
.tg th {
  font-family: Arial, sans-serif;
  font-size: 14px;
  font-weight: normal;
  padding: 20px 20px;
  border-style: solid;
  border-width: 1px;
  overflow: hidden;
  word-break: normal;
  border-color: #999;
  color: #fff;
  background-color: #26ADE4;
}
.tg .tg-ljlu {
  font-weight: bold;
  font-size: 16px;
  font-family: "Lucida Console", Monaco, monospace !important;
  background-color: #330001;
  color: #ffffff;
  text-align: center;
}
.tg .tg-a8gl {
  font-size: 16px;
  font-family: "Lucida Console", Monaco, monospace !important;
  background-color: #cac1c0;
  color: #333333;
  text-align: right;
  vertical-align: top;
  height: 65px;
}
.tg .tg-ftb4 {
  font-weight: bold;
  font-size: 16px;
  font-family: "Lucida Console", Monaco, monospace !important;
  background-color: #fe0000;
  color: #ffffff;
  text-align: center;
}
.tg .tg-lewp {
  font-weight: bold;
  font-size: 16px;
  font-family: "Lucida Console", Monaco, monospace !important;
  background-color: #fe0000;
  color: #ffffff;
  text-align: center;
  vertical-align: top;
}
.tg .tg-6dgb {
  font-weight: bold;
  font-size: 16px;
  font-family: "Lucida Console", Monaco, monospace !important;
  ;
  background-color: #330001;
  color: #ffffff;
  text-align: center;
  vertical-align: top;
}
@media screen and (max-width: 767px) {
  .tg {
    width: auto !important;
  }
  .tg col {
    width: auto !important;
  }
  .tg-wrap {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    margin: auto 0;
  }
}
```

## My JavaScript Code Snippets

```js
var operands = ['+', '-', '*', '/', '%', '.'];

function Check() {
  var lastChar = $('#result').text().slice(-1);
  for (var i = 0; i < operands.length; i++) {
    if (operands[i] == lastChar) {
      $('#result').text('Err');
    }
  }
}
$('#clear-all').click(function() {
  $('#result').text('');
});

$('#clear').click(function() {
  $('#result').text('');
});

$('#plus').click(function() {
  Check();
  $('#result').text($('#result').text() + '+');
});

$('#op').click(function() {
  Check();
  $('#result').text($('#result').text() + '(');
});

$('#clo').click(function() {
  Check();
  $('#result').text($('#result').text() + ')');
});

$('#minus').click(function() {
  Check();
  $('#result').text($('#result').text() + '-');
});

$('#mult').click(function() {
  Check();
  $('#result').text($('#result').text() + '*');
});

$('#division').click(function() {
  Check();
  $('#result').text($('#result').text() + '/');
});

$('#mod').click(function() {
  Check();
  $('#result').text($('#result').text() + '%');
});

$('#dec').click(function() {
  Check();
  $('#result').text($('#result').text() + '.');
});

$('#eq').click(function() {
  $('#result').text(eval($('#result').text()));
});

$('#nine').click(function() {
  $('#result').text($('#result').text() + 9);
});

$('#eight').click(function() {
  $('#result').text($('#result').text() + 8);
});

$('#seven').click(function() {
  $('#result').text($('#result').text() + 7);
});

$('#six').click(function() {
  $('#result').text($('#result').text() + 6);
});

$('#five').click(function() {
  $('#result').text($('#result').text() + 5);
});

$('#four').click(function() {
  $('#result').text($('#result').text() + 4);
});

$('#three').click(function() {
  $('#result').text($('#result').text() + 3);
});

$('#two').click(function() {
  $('#result').text($('#result').text() + 2);
});

$('#one').click(function() {
  $('#result').text($('#result').text() + 1);
});

$('#zero').click(function() {
  $('#result').text($('#result').text() + 0);
});
```

## Links
- [Table Generator](http://www.tablesgenerator.com/html_tables)
- [Evaluate string to code](https://www.everythingfrontend.com/posts/studying-javascript-eval.html)
