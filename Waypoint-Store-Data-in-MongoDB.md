# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Store Data in MongoDB
Whenever you run a command that includes **mongod** on c9.io, be sure to also use the `--nojournal` flag, like this: `mongod --nojournal`.

# Mongod
Hey hey from learnyoumongo. First, let's get MongoDB installed. You can download MongoDB from [https://www.mongodb.org/downloads](https://www.mongodb.org/downloads).

We will also need to add it to your $PATH.

## HINTS
To verify that mongod is installed, you can try running `mongod --version`.

If you are on Windows, you will need to use mongod.exe instead.

It should print out something similar to:

```
db version v2.6.8
2015-05-06T09:44:39.362-0500 git version: nogitversion
```

# Connect
Start mongod on port 27017 with data as the dbpath

## HINTS
You may have to create the data directory.

```
mkdir data
```

To start mongo on port 27017, `run mongod --port 27017 --dbpath=./data`.

Then, in another terminal, run `npm install mongodb`.

Then, run `learnyoumongo verify`.

If this lesson is passed, be sure to leave mongod running as it will be used for the remainder of the exercise.

## My Solution

```
rafase282:~/workspace $ mkdir data
rafase282:~/workspace $ mongod --port 27017 --dbpath=./data --nojournal
```

Then open another terminal window and install mongodb using npm.

# Find
Here we will learn how to search for documents.

For all of the exercises, the database is learnyoumongo. So, the url would be something like: `mongodb://localhost:27017/learnyoumongo`

Use the parrots collection to find all documents where age is greater than the first argument passed to your script.

Using console.log, print the documents to stdout.

## HINTS
To connect to the database, one can use something like this:

```js
var mongo = require('mongodb').MongoClient
mongo.connect(url, function(err, db) {
  // db gives access to the database
})
```

To get a collection, one can use db.collection('<collection name>').

To find a document or documents, one needs to call find() on the collection.

Find is a little bit different than what we are used to seeing.

Keep in mind, process.argv is an array of strings. To convert to an integer, you could use parseInt()

Here is an example:

```js
collection.find({
  name: 'foo'
}).toArray(function(err, documents) {

})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resources:
- [http://docs.mongodb.org/manual/reference/method/db.collection.find/](http://docs.mongodb.org/manual/reference/method/db.collection.find/)
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

## My Solution

```js
var url = 'mongodb://localhost:27017/learnyoumongo'
var mongo = require('mongodb').MongoClient
mongo.connect(url, function(err, db) {
  if (err) throw err
    // db gives access to the database
  db.collection('parrots').find({
    age: {
      // greater than integer, see resources "Find"
      $gt: parseInt(process.argv[2])
    }
  }).toArray(function(err, documents) {
    // Here is where we decide what to do with the query results
    if (err) throw err
    console.log(documents)
    // Always close the connection after you get what you need
    db.close()
  })
})
```

Official Solution:

```js
var mongo = require('mongodb').MongoClient
var age = process.argv[2]

var url = 'mongodb://localhost:27017/learnyoumongo'

mongo.connect(url, function(err, db) {
  if (err) throw err
  var parrots = db.collection('parrots')
  parrots.find({
    age: {
      $gt: +age
    }
  }).toArray(function(err, docs) {
    if (err) throw err
    console.log(docs)
    db.close()
  })
})
```

# Find Project
Here we will learn how to search for documents but only fetch the fields we need. Also known as projection in MongoDB

Use the parrots collection to find all documents where age is greater than the first argument passed to your script.

The difference from the last lesson will be that we only want the name and age properties

Using console.log, print the documents to stdout.


## HINTS
To find a document or documents, one needs to call find() on the collection.

Find is a little bit different than what we are used to seeing.

Here is an example:

```js
collection.find({
  name: 'foo'
}, {
  name: 1
, age: 1
, _id: 0
}).toArray(function(err, documents) {

})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resource:
- [http://docs.mongodb.org/manual/reference/method/db.collection.find/#explicitly-exclude-the-id-field](http://docs.mongodb.org/manual/reference/method/db.collection.find/#explicitly-exclude-the-id-field)

## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```

# Insert
## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```

# Update
## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```

# Remove
## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```

# Count
## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```

# Aggregate
## My Solution

```js
//Solution
```

Official Solution:

```js
//Solution
```
