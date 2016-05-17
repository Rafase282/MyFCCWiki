### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Timestamp Microservice

- [User Stories:](#user-stories)
- [Links](#links)
- [Notes](#notes)

### Objective:

Build a full stack JavaScript app that successfully reverse-engineers this: <http://votingapp.herokuapp.com/> and deploy it to Heroku.

Note that for each Basejump, you should create a new GitHub repository and a new Heroku project. If you can't remember how to do this, revisit <http://freecodecamp.com/challenges/get-set-for-basejumps>.

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:

1. I can pass a string as a parameter, and it will check to see whether that string contains either a unix timestamp or a natural language date (example: January 1, 2016.
2. If it does, it returns both the Unix timestamp and the natural language form of that date.
3. If it does not contain a date or Unix timestamp, it returns null for those properties.

## Links

- [App Repo](https://github.com/Rafase282/Timestamp-API)
- [App Link](http://r282-timestamp-api.herokuapp.com/)
- [Moment Js](http://momentjs.com/docs/)

### Notes

I used Momentjs which is a library for dealing with time and many different formats.

Initially I was just using plain `Date` which is also fine, but you will have to make your own conversion for months, days and so on for the natural time.

I decided to create two functions that will convert from Unix to natural and from natural to Unix, then have a pair of check to handle the scenarios where the string given via url is Unix by checking if it is a number. Given that the Unix time is basically milliseconds passed since `Jan 01 1970\. (UTC)` till now it must be minimum `0` thus any negative number should return a null value. Likewise if the string does not parse to a number then it must be a natural date format, so I just had to check if it validates to a date with Momentjs.

Something that I learned from there unrelated to dates is how to get queries without requiring the `?` in the url for APIs.

```javascript
app.get('/:query', function(req, res) {
       var date = req.params.query;
```

the `:query` part is a variable name used to get whatever is after the `/` that can be accessed via the `req.params` as noted above.

I was also able to learn how to separate my API routes from the main routes which while not needed for this app, is something useful for more complex apps.

This is done by adding `module.exports = function(app) {` tot he file with the route and by `requiring` it on the server file like this `var api = require('./app/api/timestamp.js');`
