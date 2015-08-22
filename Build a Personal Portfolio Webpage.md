# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [Infinito Web Design Studio](http://codepen.io/ThiagoFerreir4/full/eNMxEp).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Story:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can access all of the portfolio webpage's content just by scrolling.
2. As a user, I can click different buttons that will take me to the portfolio creator's different social media pages.
3. As a user, I can see thumbnail images of different projects the portfolio creator has built (if you haven't built any websites before, use placeholders.)
4. As a user, I navigate to different sections of the webpage by clicking buttons in the navigation.

## Notes:
Don't worry too much about not having anything to showcase, if you keep working on the FCC course, you will have plenty of projects to add to the portfolio.

**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jquery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My Code Snippets
### The Navigation panel:
It has to stay at the top and be responsive so it does not take too much screen space on smaller devices.

```
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
      <a class="navbar-brand" href="#">Rafael Rodriguez</a>
    </div>
    <div class="collapse navbar-collapse" id="myNavbar">
      <ul class="nav navbar-nav navbar-right">
        <li class="active"><a href="#"><span class="glyphicon glyphicon-home"></span> Home</a></li>
        <li><a href="#"><span class = "glyphicon glyphicon-info-sign"></span> About</a></li>
        <li><a href="#"><span class="glyphicon glyphicon-briefcase"></span> Portfolio</a></li>
        <li><a href="#"><span class="glyphicon glyphicon-comment"></span> Contact</a></li>
      </ul>
    </div>
  </div>
</nav>
```

Make sure to add `https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/3.3.5/js/bootstrap.min.js` to the JS part on CodePen so the dropdown menu for mobile works.
