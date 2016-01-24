# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a full stack JavaScript app that successfully reverse-engineers this: [https://shurli.herokuapp.com/](https://shurli.herokuapp.com/) and deploy it to Heroku.

Note that for each Basejump, you should create a new GitHub repository and a new Heroku project. If you can't remember how to do this, revisit [https://cryptic-ridge-9197.herokuapp.com/api/imagesearch/lolcats%20funny?offset=10](https://cryptic-ridge-9197.herokuapp.com/api/imagesearch/lolcats%20funny?offset=10) and browse recent search queries like this: [https://cryptic-ridge-9197.herokuapp.com/api/latest/imagesearch/](https://cryptic-ridge-9197.herokuapp.com/api/latest/imagesearch/). Then deploy it to Heroku.

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:
- I can get the image URLs, alt text and page urls for a set of images relating to a given search string.
- I can paginate through the responses by adding a ?offset=2 parameter to the URL.
- I can get a list of the most recently submitted search strings.

## Links
- [App Repo](https://github.com/Rafase282/Image-Search-Abstraction-Layer)
- [App Link](https://img-sal.herokuapp.com)
- [Bing API Handler](https://www.npmjs.com/package/bing.search)
- [Bing API](https://datamarket.azure.com/dataset/bing/search)
- [Mongoose](http://mongoosejs.com/docs/index.html)

## Environment Variables
While heroku can use them as is, cloud9 needs extra work to get them from the `.env` file that you would create.

## Notes
The Bing search api is a pain. I recommend using a npm package to handle it, there are many and I listed one of them. You will also have to sign up to get a key which I recommend using from the `.env` file as to not leak your key. It has a main key but it is better to create a new one that you can delete if it gets compromised, because the main one can't be changed.

Learning about Mongoose was fun. Basically you have to require it, create a scheme, turn it into a model and then youc an use it to create documents.

1. Require Mongoose and declare Schema.
```js
var mongoose = require('mongoose');
var Schema = mongoose.Schema;
```

2. Create Schema
```js
var kittySchema = mongoose.Schema({
    name: String
});
```

3.  Turn the schema into a model, and connect to it.
```js
var Kitten = mongoose.model('Kitten', kittySchema);
var mongouri = process.env.MONGOLAB_URI || "mongodb://" + process.env.IP + ":27017/img-sal";
mongoose.connect(mongouri);
```
While you can do 1 to 3 on the server like I did, the step for and any other can be done anywhere else as long as you know how to export the model.

4. Create new documents based on the model
```js
var silence = new Kitten({ name: 'Silence' });
console.log(silence.name); // 'Silence'
```

How to export the model to my api.

```js
api(app, Kitten);
```

then on the api file:
`module.exports = function(app, History) {`

The search and find can be found on the documentation along with the rest of teh steps I have listed aside from exporting.
