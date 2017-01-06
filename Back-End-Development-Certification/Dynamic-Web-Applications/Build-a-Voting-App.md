### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Build a Voting App
   
- [Objective:](#objective)   
- [User Stories:](#user-stories)   
- [Links](#links)   
- [Server](#server)   
- [App.js](#appjs)   

## Objective:

Build a full stack JavaScript app that successfully reverse-engineers this: <http://votingapp.herokuapp.com/> and deploy it to Heroku.

Note that for each Basejump, you should create a new GitHub repository and a new Heroku project. If you can't remember how to do this, revisit <http://freecodecamp.com/challenges/get-set-for-basejumps>.

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:

- As an authenticated user, I can keep my polls and come back later to access them.
- As an authenticated user, I can share my polls with my friends.
- As an authenticated user, I can see the aggregate results of my polls.
- As an authenticated user, I can delete polls that I decide I don't want anymore.
- As an authenticated user, I can create a poll with any number of possible items.
- As an unauthenticated or authenticated user, I can see and vote on everyone's polls.
- As an unauthenticated or authenticated user, I can see the results of polls in chart form. (This could be implemented using Chart.js or Google Charts.)
- As an authenticated user, if I don't like the options on a poll, I can create a new option.

## Links

- [App Repo](https://github.com/Rafase282/Voting-App)
- [App Link](https://voting-app-rafase282.c9users.io/)

## Server

```javascript
'use strict';

var express = require('express');
var mongo = require('mongodb');
var routes = require('./app/routes/index.js');

var app = express();

mongo.connect('mongodb://localhost:27017/clementinejs', function(err, db) {

  if (err) {
    throw new Error('Database failed to connect!');
  } else {
    console.log('Successfully connected to MongoDB on port 27017.');
  }

  // The format follows as, alias to use for real path, also allows permission to such path.
  app.use('/public', express.static(process.cwd() + '/public'));
  app.use('/controllers', express.static(process.cwd() + '/app/controllers'));
  app.use('/src', express.static(process.cwd() + '/app/src'));

  routes(app, db);

  var port = process.env.PORT || 8080;
  app.listen(port, function() {
    console.log('Node.js listening on port ' + port);
  });

});
```

## App.js

```javascript
var React = require('react');
var ReactDOM = require('react-dom');
var NavBar = require('./navbar.js');
var HeaderArea = require('./header.js');
var MainArea = require('./main.js');
var Footer = require('./footer.js');

var App = React.createClass({
  render: function() {
    return (
      < div >
      < NavBar / >
      < HeaderArea / >
      < MainArea / >
      < Footer / >
      < /div>
    );
  }
});
ReactDOM.render(
  < App / >,
  document.getElementById('body')
);
```
