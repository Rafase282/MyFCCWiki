# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

## Install Node.js with NPM
Info from [here.](https://github.com/nodesource/distributions#debinstall)

C9:

```
nvm install stable
nvm alias default stable
```

Ubuntu 15.10, Node.js v5.x:

```
curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
sudo apt-get install -y nodejs
```

io.js v3.x:

```
curl -sL https://deb.nodesource.com/setup_iojs_3.x | sudo -E bash -
sudo apt-get install -y iojs
```

## Install MongoDB
Note that MongoDB only supports LTS versions of Ubuntu officially. More detailed instructions [here.](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/)

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```

```
echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```

```
sudo apt-get update
sudo apt-get install -y mongodb-org
```

## Initialize App
Run this command to create the `package.json`

`$ npm init`

Follow the instructions and you should have something similar to this:

```
{
  "name": "beginner-app",
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "MIT"
}
```

## Install Dependencies
`npm install --save express mongodb mongoose passport express-session react react-dom babelify babel-preset-react`

This will install:
- Express.js
- MongoDB
- Mongoose
- Passport
- Express Session
- React.js

Now we have the fullstack dependencies and even passport and session support for login in and such. For this stack the required ones are express, mongodb, react, and mostlikelly mongoose.

Now the `package.json` will look like this:

```js
{
  "name": "voting-app",
  "version": "0.0.1",
  "description": "A voting app that lets you create your own polls.",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/Rafase282/Voting-App.git"
  },
  "keywords": [
    "MongoDB",
    "Mongoose",
    "full stack",
    "Express",
    "Node",
    "React",
    "javascript",
    "vote"
  ],
  "author": "Rafael (Rafase282)",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/Rafase282/Voting-App/issues"
  },
  "homepage": "https://github.com/Rafase282/Voting-App#readme",
  "dependencies": {
    "express": "^4.13.3",
    "express-session": "^1.12.1",
    "mongodb": "^2.1.0",
    "mongoose": "^4.3.0",
    "passport": "^0.3.2",
    "react": "^0.14.3"
  }
}
```

## Directory structure
Now let's spend a few moments to create the file structure we'll be using.

```
+-- Project Folder
    +-- app
    |   \-- controllers
    |   \-- routes
    |
    +-- public
    |   \-- css
    |   \-- img
```

More details [here.](http://www.clementinejs.com/tutorials/tutorial-beginner.html)

# React Tutorials
- [React.js Tutorial Pt 1: A Comprehensive Guide to Building Apps with React.js](http://tylermcginnis.com/reactjs-tutorial-a-comprehensive-guide-to-building-apps-with-react/)
- [React.js Tutorial Pt 2: Building React Applications with Gulp and Browserify.](http://tylermcginnis.com/reactjs-tutorial-pt-2-building-react-applications-with-gulp-and-browserify/)
