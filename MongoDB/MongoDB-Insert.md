### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Insert

Connect to MongoDB on port 27017\. You should connect to the database named learnyoumongo and insert a document into the docs collection.

The document should be a json document with the following properties:

- `firstName`
- `lastName`

`firstName` will be passed as the first argument to the lesson.

`lastName` will be passed as the second argument to the lesson.

Use console.log to print out the object used to create the document.

Make sure you use JSON.stringify convert it to JSON.

## HINTS

Remember, one can access the arguments passed by using process.argv.

In order to use the mongo package, one must first require it like:

```javascript
var MongoClient = require('mongodb').MongoClient
```

To connect, use the connect() function of MongoClient.

Ex.

```javascript
MongoClient.connect(url, function(err, db) {
  if (err) throw err

})
```

If you get a Connection Refused error, make sure that mongod is still running.

After you have successfully connected, you will need to specify a collection. That can be done by calling the `collection()` function on the db returned in the callback to connect.

Say you wanted to specify a collection named users:

```javascript
var collection = db.collection('users')
```

To insert a document, one would need to call `insert()` on the collection, like this:

```javascript
// inserting document
// { a : 2 }
collection.insert({
  a: 2
}, function(err, data) {
  // handle error

  // other operations
})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resource

- <http://docs.mongodb.org/manual/reference/method/db.collection.insert/>

## My Solution

```javascript
var url = 'mongodb://localhost:27017/learnyoumongo'
var MongoClient = require('mongodb').MongoClient
var doc = {
  firstName: process.argv[2],
  lastName: process.argv[3]
}
MongoClient.connect(url, function(err, db) {
  if (err) throw err
  var collection = db.collection('docs')
  // You need the information to be inserted and a function that also handles errors
  collection.insert(doc, function(err, data) {
    // handle error
    if (err) throw err

    // You print the inserted document and not "data"
    console.log(JSON.stringify(doc))
    db.close()
  })
})
```

## Official Solution:

```javascript
var mongo = require('mongodb').MongoClient

var firstName = process.argv[2]
var lastName = process.argv[3]
var doc = {
  firstName: firstName,
  lastName: lastName
}

var url = 'mongodb://localhost:27017/learnyoumongo'
mongo.connect(url, function(err, db) {
  if (err) throw err
  var collection = db.collection('docs')
  collection.insert(doc, function(err, data) {
    if (err) throw err
    console.log(JSON.stringify(doc))
    db.close()
  })
})
```
