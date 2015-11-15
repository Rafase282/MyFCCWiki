# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Manage Packages with NPM
### Install NPM
The first thign to do is to install [Node.js](https://nodejs.org/en/download/) and read the [documentation.](https://nodejs.org/en/docs/)

Then from the terminal or console type `npm install -g how-to-npm` to install the guide.

You can verify your answers with `how-to-npm verify`

### Setup Dev Envirioment
Then create a dev environment by creating a directory to work on. `mkdir "dirname"`

Next is to create an online account for which you will need to create a username, password, provide an email which will be public. This will let other users install modules created by you.

`npm adduser` is the commnad.

### Start A project
npm helps you build projects, but for npm to be able to do that, you need to tell npm a little bit about your project. You can tell npm about your project in a file called package.json.

Run `npm init --scope=<username>`, and replace <username> with the user you created in the last lesson. This will create a package.json file.

You will get the following output and prompt:

```
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg> --save` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
name: (@Rafase282/dev)
Sorry, name can no longer contain capital letters.
name: (@Rafase282/dev) rafase282
version: (1.0.0)
description: Test
entry point: (index.js)
test command:
git repository:
keywords:
author: Rafase282
license: (ISC)
About to write to /home/ubuntu/workspace/dev/package.json:

{
  "name": "rafase282",
  "version": "1.0.0",
  "description": "Test",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Rafase282",
  "license": "ISC"
}


Is this ok? (yes)
```

### INstall a Module
