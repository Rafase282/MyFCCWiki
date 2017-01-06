### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Connect

Start **mongod** on port **27017** with _data_ as the **dbpath**

## HINTS

You may have to create the data directory.

```bash
mkdir data
```

To start mongo on port 27017, `run mongod --port 27017 --dbpath=./data`.

Then, in another terminal, run `npm install mongodb`.

Then, run `learnyoumongo verify`.

If this lesson is passed, be sure to leave mongod running as it will be used for the remainder of the exercise.

## My Solution

```bash
rafase282:~/workspace $ mkdir data
rafase282:~/workspace $ mongod --port 27017 --dbpath=./data --nojournal
```

Then open another terminal window and install mongodb using npm.
