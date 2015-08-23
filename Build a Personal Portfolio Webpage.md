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
It has to stay at the top and be responsive so it does not take too much screen space on smaller devices. This navigation bar will turn into a dropdown menu on smaller screens. Furthermore, as you scroll down the page, the different tabs will be selected.
- `navbar-inverse`: Makes it black instead of white.
- `navbar-fixed-top`: Makes it stay at the top.
- 'container-fluid': Makes it fluid instead of fixed.
- 'class="navbar-toggle" data-toggle="collapse" data-target=".myNavbar"': This will make the buttons on a toggle style, and also make it collapse when the screen is small enough with the target being the buttons of the right side under the class 'myNavBar'
- The whole navbar is divided in two, one on the left for logo and name, and one of the right for the buttons.
- For the scrolling while toggling the proper button, the effect is linked by the `href` which uses `id` so it would be good to use `class` and `id` with the same name.
- The icons are added using `span` elements, and require bootstrap to be added to the site.

More about the [Scrollspy plugin.](http://www.w3schools.com/bootstrap/bootstrap_scrollspy.asp)

```
<!-- The scrollable area -->

<body data-spy="scroll" data-target=".navbar" data-offset="50">
  <!-- Navigation Part -->
  <nav class="navbar navbar-inverse navbar-fixed-top">
    <div class="container-fluid">
      <div class="navbar-header">
        <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".myNavbar">
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <a class="navbar-brand" href="#">Rafael Rodriguez</a>
      </div>
      <div class="collapse navbar-collapse myNavbar">
        <ul class="nav navbar-nav navbar-right">
          <li class="active">
            <a href="#home">
              <span class="glyphicon glyphicon-home"></span> Home</a>
          </li>
          <li>
            <a href="#experience">
              <span class="glyphicon glyphicon-info-sign"></span> Experience</a>
          </li>
          <li>
            <a href="#portfolio">
              <span class="glyphicon glyphicon-briefcase"></span> Portfolio</a>
          </li>
          <li>
            <a href="#contact">
              <span class="glyphicon glyphicon-comment"></span> Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
```

Make sure to add `https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/3.3.5/js/bootstrap.min.js` to the JS part on CodePen so the dropdown menu for mobile works and also the glyphicons.

### The Home section
While I could have used `<div></div>` and give it a class to create the section. It is better to use html5 and use the `section` element.

Here is a diagram of it:

![HTML5](http://www.w3schools.com/html/img_sem_elements.gif)

As you can see, there is no need to use `div` to create custom sections. For detailed information on the semantic elements check [this.](http://www.w3schools.com/html/html5_semantic_elements.asp)
- I gave the same name for the `class` and `id` since the `id` is used for the scroll effect on the tabs.
- `img-responsive` Will make the image responsive.
- `img-circle` will turn the image from whatever shape into a circle shape.
- `displayed` is used to center the image on the screen, check the CSS code.
- `me` is a class I created to identify that this is the photo with my face as it will behave differently as the images used on the portfolio.
- `img-text` is a class I created identify the text color for images.

```
<!-- Home -->
<section class="home" id="home">
  <h1>Rafael Rodriguez</h1>
  <h2>Creative Solutions</h2>
  <img class="img-responsive img-circle displayed me" src="https://avatars.githubusercontent.com/u/285138?v=3">
  <div class="img-text">
    <p>My name is Rafael Rodriguez. I’m a Computer Science graduate from Lehman College, NY. A single parent, co-founder of TealSeagull LLC (still cooking), I work as a freelancer for the time being, I write reviews, talk about my personal projects and
      even have two small books published at the moment.</p>
  </div>
</section>
```

### The Experience section
For this section I have used `section` and gave it a class and id with the same name for the reasons already explained.
- I used an [accordion](http://www.w3schools.com/bootstrap/bootstrap_collapse.asp) appearance using `collapsible` from bootstrap.

```
<!-- Experience -->
<section class="experience" id="experience">
  <div class="container">
    <h1>My Experience</h2>
      <p>Here is some of my past employment history.</p>
      <div class="panel-group" id="accordion">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4 class="panel-title">
              <a data-toggle="collapse" data-parent="#accordion" href="#collapse1">Freelancer UpWork</a>
            </h4>
          </div>
          <div id="collapse1" class="panel-collapse collapse in">
            <div class="panel-body">Over the past year I have polished and improved my Amazon services regarding publishing, eBook creation, ghostwriting, Amazon research, and technical support for Kindle services. Besides my writing experience with Amazon, I have also done
              blogs, articles, web research, and data entry jobs in occasions. I also work on the technical side and do plenty of help-desk related task, email handling, and QA for software and systems. I have experience in python, Go, java,and other
              programming languages, although I have done more web development recently. I put a lot of dedication in my work, however simple the task might be to ensure the work is done correctly and as fast as efficiently possible. I work full time
              as a freelancer so I'm easy to reach any day.</div>
          </div>
        </div>
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4 class="panel-title">
              <a data-toggle="collapse" data-parent="#accordion" href="#collapse2">Independent Contrator for NYC Board of Education</a>
            </h4>
          </div>
          <div id="collapse2" class="panel-collapse collapse">
            <div class="panel-body">November 2014 – Present (10 months)
              <h5>Job Responsibilities
                <h5>
                  I provide Help-desk and other on demand solutions to the NYC public schools. Currently I have worked on M.S. 219, setting up a computer lab for the school, upgrading and setting up iPads and other Help-desk related tasks.
            </div>
          </div>
        </div>
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4 class="panel-title">
              <a data-toggle="collapse" data-parent="#accordion" href="#collapse3">Information Technology Intern</a>
            </h4>
          </div>
          <div id="collapse3" class="panel-collapse collapse">
            <div class="panel-body">
              September 2010 – July 2014 (3 years 11 months) Bronx, NY
              <h5>Job Responsibilities</h5>
              <ul>
                <li>Assist in the setup of new computer equipment in classroom and offices.</li>
                <li>Install software.</li>
                <li>Ensure that LCD projector, smart boards, and other related audio/video equipment remains functional.</li>
                <li>Troubleshoot hardware and software problems in conjunction with Department of Education (DOE) Help Center and borough technology staff.</li>
                <li>Configure wireless devices to access DOE network.</li>
                <li>Maintain classroom servers.</li>
                <li>Maintain technology equipment inventory.</li>
                <li>Monitor equipment in the technology laboratory.</li>
                <li>Coordinate with MOUSE Squad, if applicable.</li>
                <li>Local and network ghosting.</li>
                <li>Troubleshoot and setup network printers.</li>
                <li>Network administrator for Windows Server 2008.</li>
                <li>Desktop support for teachers.</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
  </div>
</section>
```

### The portfolio section
The portfolio section is a bit more complicated. It uses columns to align the images and information evenly.

```
<!-- Portfolio -->
<section class="portfolio" id="portfolio">
  <h1>Portfolio</h1>
  <p>My upcoming projects will be here!</p>
  <div class="container">

    <!-- Example row of columns -->
    <div class="row">
      <div class="col-md-3">
        <div class="well">
          <a href="#" class="thumbnail">
            <img src="http://lorempixel.com/output/technics-h-c-171-180-4.jpg" alt="Project 1">
          </a>
          <h2 class="gray-text">Project Title</h2>
          <p class="gray-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </div>
      <div class="col-md-3">
        <div class="well">
          <a href="#" class="thumbnail">
            <img src="http://lorempixel.com/output/nightlife-h-c-171-180-10.jpg" alt="Project 2">
          </a>
          <h2 class="gray-text">Project Title</h2>
          <p class="gray-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </div>
      <div class="col-md-3">
        <div class="well">
          <a href="#" class="thumbnail">
            <img src="http://lorempixel.com/output/sports-h-c-171-180-7.jpg" alt="Project 3">
          </a>
          <h2 class="gray-text">Project Title</h2>
          <p class="gray-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </div>
      <div class="col-md-3">
        <div class="well">
          <a href="#" class="thumbnail">
            <img src="http://lorempixel.com/output/food-h-c-171-180-1.jpg" alt="Project 4">
          </a>
          <h2 class="gray-text">Project Title</h2>
          <p class="gray-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </div>
    </div>
  </div>
</section>
```
