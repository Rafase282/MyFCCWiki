### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Find

Here we will learn how to search for documents.

For all of the exercises, the database is learnyoumongo. So, the url would be something like: `mongodb://localhost:27017/learnyoumongo`

Use the parrots collection to find all documents where age is greater than the first argument passed to your script.

Using console.log, print the documents to stdout.

## HINTS

To connect to the database, one can use something like this:

```javascript
var mongo = require('mongodb').MongoClient
mongo.connect(url, function(err, db) {
  // db gives access to the database
})
```

To get a collection, one can use

```javascript
db.collection('<collection name>')
```

To find a document or documents, one needs to call find() on the collection.

Find is a little bit different than what we are used to seeing.

Keep in mind, process.argv is an array of strings. To convert to an integer, you could use parseInt()

Here is an example:

```javascript
collection.find({
  name: 'foo'
}).toArray(function(err, documents) {

})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resources:

- <http://docs.mongodb.org/manual/reference/method/db.collection.find/>
- <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt>

## My Solution

```javascript
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
  }).toArray(function(err, docs) {
    if (err) throw err
    console.log(docs)
    db.close()
  })
})
```
