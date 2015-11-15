# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Manage Packages with NPM
### Install NPM
The first thign to do is to install [Node.js](https://nodejs.org/en/download/) and read the [documentation.](https://nodejs.org/en/docs/)

Then from the terminal or console type `npm install -g how-to-npm` to install the guide.

You can verify your answers with `how-to-npm verify`

### Setup Development Envirioment
Then create a dev environment by creating a directory to work on. `mkdir "dirname"`

Next is to create an online account for which you will need to create a username, password, provide an email which will be public. This will let other users install modules created by you.

`npm adduser` is the command.

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

### Install a Module
The first thing that most people do with npm is install a dependency.

Dependencies are fetched from the registry, and unpacked in the `node_modules` folder.

To install a module, use the `npm install <modulename>` command.

```
rafase282:~/workspace/dev $ npm install @linclark/pkg
rafase282@1.0.0 /home/ubuntu/workspace/dev
└── @linclark/pkg@1.0.2  extraneous

npm WARN EPACKAGEJSON rafase282@1.0.0 No repository field.
```

### Listing Dependencies
npm isn't just for installing stuff.  It also shows you what you have installed.

You can do this using the `npm ls` command.

Run this command in your working dir, and then run `how-to-npm verify OK` if everything looks ok, or `how-to-npm verify NOT OK` if there was a problem.

```
rafase282:~/workspace/dev $ npm ls
rafase282@1.0.0 /home/ubuntu/workspace/dev
└── @linclark/pkg@1.0.2 extraneous

npm ERR! extraneous: @linclark/pkg@1.0.2 /home/ubuntu/workspace/dev/node_modules/@linclark/pkg
```

Your dependencies should be listed in the package.json file in an object called 'dependencies'.  However, when we installed '@linclark/pkg', we didn't update the package.json file to list out this dependency.

So, it shows up as 'extraneous', warning us that we have something there that we haven't listed as a dependency.

The easiest way to avoid this situation is to use the `--save` flag when installing dependencies.  You might not want to do this with things that you're just trying out, but when you decide on something, you can use this flag to update your package.json file easily.

Try running `npm install @linclark/pkg --save` to install the module, and also update your package.json file at the same time.

(Another option is to just edit package.json yourself in a text editor)

```
rafase282:~/workspace/dev $ npm install @linclark/pkg --save
rafase282@1.0.0 /home/ubuntu/workspace/dev
└── @linclark/pkg@1.0.2
```

Always pay attention to the error messages. For this you will need to use `how-to-npm verify OK` to finish it.

### NPM Test
Now you've installed something, and used `npm ls` to show what's going on.

If you look at the package.json file, it has this rather odd bit in it:

  "scripts": {     "test": "echo \"Error: no test specified\" && exit 1"   },

npm can be used as a task runner, and almost every module and project will have a test script that runs to make sure everything is good.  In order to help remind you to do this, npm puts a "always failing" test in there by default.

First, create a file called `test.js`.  It doesn't have to do anything, really.  (This is npm class, not testing class.)  But it has to exit without throwing an error, or else the test fails.

Then, edit your `package.json` file to make your scripts section look like this instead:

```
  "scripts": {
    "test": "node test.js"
  },
```

```
rafase282:~/workspace/dev $ npm ls
rafase282@1.0.0 /home/ubuntu/workspace/dev
└── @linclark/pkg@1.0.2
```

The test.js can be something as simple as a console log. Anything as long as it does not have an error. This is where you build a test case for your module.
