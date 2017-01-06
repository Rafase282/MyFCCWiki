# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

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

### Package Niceties
So, we've created a package.json file, but it's missing a few things that people usually expect.  If you type `npm install`, you'll see something like this:

```
npm WARN package.json rafase282@1.0.0 No description
npm WARN package.json rafase282@1.0.0 No repository field.
npm WARN package.json rafase282@1.0.0 No README data
```

Before we can share this work of art with the world, we need to make it a bit more polished so that people know how to use it.

First, create a README.md file, with a bit of words in it.

Then, add a "repository" field in your package.json file, with a url where people can access the code.

You can edit your package.json file by hand, or run `npm init` again.

### Publish
What good is a package manager without packages?

Not very good.

Luckily, that is not a problem for npm, because it's very easy for all npm users to publish their modules and share them with the world.

Packages get into the registry by using the `npm publish` command.

If YOu haven't added a user yet then youw ill get this message:

```
rafase282:~/workspace/dev $ npm publish
npm ERR! Linux 4.2.0-c9
npm ERR! argv "/home/ubuntu/.nvm/versions/node/v4.1.1/bin/node" "/home/ubuntu/.nvm/versions/node/v4.1.1/bin/npm" "publish"
npm ERR! node v4.1.1
npm ERR! npm  v3.4.0
npm ERR! code ENEEDAUTH

npm ERR! need auth auth required for publishing
npm ERR! need auth You need to authorize this machine using `npm adduser`

npm ERR! Please include the following file with any support request:
npm ERR!     /home/ubuntu/workspace/dev/npm-debug.log
```

In order to view your package content, I just ran this command:

  npm view rafase282

Run that command yourself to see what it prints out.

The `npm view` command is a great way to view package details, to see what you just published, and to check if a name is already taken.

Now that you've published your first package here in make-believe npm workshop land, go out and write a real thing to share with real humans!

You don't have to just share code for other people, though.  There are also benefits to breaking up your code into small manageable pieces, even if you are only using them all yourself.

You can imagine that your future self and your past self are the two other developers on your team.  (Scheduling meetings is pretty tricky.)

### Version
Every package in npm has a version number associated with it.  As you release updates to your package, these updates get an updated version number.

Version numbers in npm follow a standard called "SemVer".  This stands for "Semantic Version".  The specification for this standard can be found at [http://semver.org](http://semver.org).

The tl;dr version is that for a version like this:

```
  1.2.3
  ^ ^ ^
  | | `-- Patch version. Update for every change.
  | `---- Minor version. Update for API additions.
  `------ Major version. Update for breaking API changes.
```

npm has a special command called `npm version` which will update your package.json file for you, and also commit the change to git if your project is a git repository.  You can learn more at `npm help version`.

Or, if you don't trust the machines, you can open up your package.json file by hand, and put some new numbers in the "version" field.

The npm registry won't let you publish a new release of your package without updating the version number!  Ever!  So, get used to the idea of bumping the version whenever you want to publish, even if the change is really minor.

Don't worry, there's a lot of integers, we probably won't run out.
