# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a full stack JavaScript app that successfully reverse-engineers this: [https://shurli.herokuapp.com/](https://shurli.herokuapp.com/) and deploy it to Heroku.

Note that for each Basejump, you should create a new GitHub repository and a new Heroku project. If you can't remember how to do this, revisit [http://freecodecamp.com/challenges/get-set-for-basejumps](http://freecodecamp.com/challenges/get-set-for-basejumps).

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:
- I can pass a URL as a parameter and I will receive a shortened URL in the JSON response.
- If I pass an invalid URL that doesn't follow the valid [http://www.example.com](http://www.example.com) format, the JSON response will contain an error instead.
- When I visit that shortened URL, it will redirect me to my original link.

## Links
- [App Repo](https://github.com/Rafase282/URL-Shortener)
- [App Link](https://little-url.herokuapp.com)
- [DotEnv](https://www.npmjs.com/package/dotenv)

## Envirioment Variables
While heroku can use them as is, cloud9 needs extra work to get them from the `.env` file that you would create.
