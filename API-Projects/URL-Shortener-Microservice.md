### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Timestamp Microservice
   
- [User Stories:](#user-stories)   
- [Links](#links)   
- [Environment Variables](#environment-variables)   
- [Notes](#notes)   

### Objective:

Build a full stack JavaScript app that successfully reverse-engineers this: <https://shurli.herokuapp.com/> and deploy it to Heroku.

Note that for each Basejump, you should create a new GitHub repository and a new Heroku project. If you can't remember how to do this, revisit <http://freecodecamp.com/challenges/get-set-for-basejumps>.

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:

- I can pass a URL as a parameter and I will receive a shortened URL in the JSON response.
- If I pass an invalid URL that doesn't follow the valid <http://www.example.com> format, the JSON response will contain an error instead.
- When I visit that shortened URL, it will redirect me to my original link.

## Links

- [App Repo](https://github.com/Rafase282/URL-Shortener)
- [App Link](https://little-url.herokuapp.com)
- [DotEnv](https://www.npmjs.com/package/dotenv)
- [Redirect](http://expressjs.com/en/4x/api.html#res.redirect)
- [URL Validator URL](https://gist.github.com/dperini/729294)
- [callback Hell](http://callbackhell.com/)
- [db.collection.findOne()](https://docs.mongodb.org/manual/reference/method/db.collection.findOne/)

## Environment Variables

While heroku can use them as is, cloud9 needs extra work to get them from the `.env` file that you would create.

## Notes

There were quite a few things that I learned from this, first, everyone prefers to use Mongoose over plain MongoDB. Second, I need to create a collection or scheme if I use Mongoose.

This will do with plain MongoDB.

```javascript
db.createCollection("sites", {
  capped: true,
  size: 5242880,
  max: 5000
});
```

Since I used MongoLab and I did not want to provide the url with username and password embedded to the whole wide word, something that everyone will want to avoid in production, I opted for using custom environment variables like `process.env.MONGOLAB_URI` For this to actually work on c9, not necessarily heroku I had to use

```javascript
 require('dotenv').config({
   silent: true
 });
```

Otherwise it would not work. I have provided a link to learn more about it.

As for html and modifications on the fly, it is better to use `jade` so that is something I will be learning too. `npm install jade -S` will get you started.

You will then use render instead of sending a html file on the custom router like this:

```javascript
res.render('index', {
  err: "Error: You need to add a proper url"
});
```

which will be handled by:

```jade
if (err)
    div
        h2(style = "color: red;")= err
```

on the jade file.

As for node and mongo, they work `async` which is something that skipped my mind while trying to return the results from a `findone` search.

Speaking of which, doing a `find` didn't yield the results I wanted so I opted for `findone` instead. Knowing this will save you much time and trouble.

Also you will have to pass the db as a parameter or you will have to connect and close each time.

- From the server files: `api(app, db);`
- From the API: `module.exports = function(app, db) {`
- From local functions: `function save(obj, db) {`

There are different ways to handle the url with the api:

- `app.route('/:url')` to get the short url to redirect.
- `app.get('/new/:url*', handlePost);` to handle a request to encode the url after `new` even though new is not a real directory.
- `app.route('/')` to display the main html file on root.
- `app.route('/new')` for handling errors to the user about bad usage, it should be used with an url to be encoded.
