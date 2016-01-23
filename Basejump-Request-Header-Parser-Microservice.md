# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a full stack JavaScript app that is functionally similar to this: [https://cryptic-ridge-9197.herokuapp.com/api/whoami/](https://cryptic-ridge-9197.herokuapp.com/api/whoami/) and deploy it to Heroku.

As you build your app, you should frequently commit changes to your codebase. You can do this by running `git commit -am "your commit message"`. Note that you should replace "your commit message" with a brief summary of the changes you made to your code.

You can push these new commits to GitHub by running `git push origin master`, and to Heroku by running `grunt --force && grunt buildcontrol:heroku`.

## User Stories:
- I can get the IP address, language and operating system for my browser.

## Links
- [App Repo](https://github.com/Rafase282/header-parser)
- [App Link](https://header-parser.herokuapp.com/)
- [Get IP](http://stackoverflow.com/questions/10849687/express-js-how-to-get-remote-client-address)

## Environment Variables
While heroku can use them as is, cloud9 needs extra work to get them from the `.env` file that you would create.

## Notes
This was simpler than expected. The first thign that I did was figure out how to get the user ip. One might think of using an API but when you think about it, an API depending on another API that already does the work would be redundant so I started searching for how to get the API from Express, after all, all servers get the cleint's IP.

A quick search will yield many results, the challenge is to know what to look for. Int he same fashion you can also look for how to get the other information and create your object from it. I recommand matching the info to

```js
{"ipaddress":"xxx.xxx.xxx.xxx","language":"en-US","software":"X11; Linux x86_64"}
```
