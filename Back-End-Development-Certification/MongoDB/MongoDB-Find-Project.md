### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Find Project

Here we will learn how to search for documents but only fetch the fields we need. Also known as projection in MongoDB

Use the parrots collection to find all documents where age is greater than the first argument passed to your script.

The difference from the last lesson will be that we only want the name and age properties

Using `console.log`, print the documents to `stdout`.

## HINTS

To find a document or documents, one needs to call find() on the collection.

Find is a little bit different than what we are used to seeing.

Here is an example:

```javascript
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

- <http://docs.mongodb.org/manual/reference/method/db.collection.find/#explicitly-exclude-the-id-field>

## My Solution

```javascript
var url = 'mongodb://localhost:27017/learnyoumongo'
var mongo = require('mongodb').MongoClient
mongo.connect(url, function(err, db) {
  if (err) throw err
    // db gives access to the database
  db.collection('parrots').find({
    age: {
      $gt: parseInt(process.argv[2])
    }
  }, {
    name: 1,
    age: 1,
    _id: 0

  }).toArray(function(err, documents) {
    // Here is where we decide what to do with the query results
    if (err) throw err
    console.log(documents)
    db.close()
  })
})
```

## Official Solution:

```javascript
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
  }, {
    name: 1,
    age: 1,
    _id: 0
  }).toArray(function(err, docs) {
    if (err) throw err
    console.log(docs)
    db.close()
  })
})
```
