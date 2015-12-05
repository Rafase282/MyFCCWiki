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

# Insert
Connect to MongoDB on port 27017. You should connect to the database named learnyoumongo and insert a document into the docs collection.

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

```js
var MongoClient = require('mongodb').MongoClient
```

To connect, use the connect() function of MongoClient.

Ex.

```js
MongoClient.connect(url, function(err, db) {
  if (err) throw err

})
```

If you get a Connection Refused error, make sure that mongod is still running.

After you have successfully connected, you will need to specify a collection. That can be done by calling the `collection()` function on the db returned in the callback to connect.

Say you wanted to specify a collection named users:

```js
var collection = db.collection('users')
```

To insert a document, one would need to call `insert()` on the collection, like this:

```js
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
- [http://docs.mongodb.org/manual/reference/method/db.collection.insert/](http://docs.mongodb.org/manual/reference/method/db.collection.insert/)

## My Solution

```js
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

Official Solution:

```js
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

# Update
Here we are going to update a document in the users collection.

The database name will be accessible via `process.argv[2]`.

Say we have a user defined like:

```js
{
  "name": "Tina",
  "age": 30,
  "username": "tinatime"
}
```

We want to change Tina's age from 30 to 40.

For the purpose of this lesson, assume that the username property is unique.

## HINTS
To update a document, one would need to call `update()` on the collection.

Ex.

```js
// document
// { a: 2, b: 3 }

collection.update({
  a: 2
}, {
  $set: {
    b: 1
  }
}, callback)

// document was updated
// { a: 2, b: 1 }
```

The first argument to update() is the query. This query is what filters the documents that we are wanting to update. The second argument is an object of the properties to update. Pay close attention to the $set property. If we were to omit $set, the document would be replaced with the object represented by the second argument.

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resources
- [http://docs.mongodb.org/manual/tutorial/modify-documents/](http://docs.mongodb.org/manual/tutorial/modify-documents/)
- [http://docs.mongodb.org/manual/reference/operator/update/set/#set](http://docs.mongodb.org/manual/reference/operator/update/set/#set)

## My Solution

```js
var url = 'mongodb://localhost:27017/' + process.argv[2];
var MongoClient = require('mongodb').MongoClient;

MongoClient.connect(url, function(err, db) {
  if (err) throw err;
  var collection = db.collection('users');
  collection.update({
    "username": "tinatime"
  }, {
    $set: {
      "age": 40
    }
  }, function() {
    // Callback, close connection
    db.close();
  })
})
```

Official Solution:

```js
var mongo = require('mongodb').MongoClient

var url = 'mongodb://localhost:27017/' + process.argv[2]
mongo.connect(url, function(err, db) {
  if (err) throw err
  var collection = db.collection('users')
  collection.update({
    username: 'tinatime'
  }, {
    $set: {
      age: 40
    }
  }, function(err) {
    if (err) throw err
    db.close()
  })
})
```

# Remove
This lesson involves removing a document with the given `_id`.

The database name will be accessible via `process.argv[2]`.

The collection name will be passed as the second argument to your script.

The `_id` will be passed as the third argument to your script.

## HINTS
To remove a document, one would need to call `remove()` on the collection.

Ex.

```js
collection.remove({
  name: 'foo'
}, callback)
```

The first argument to `remove()` is the query.

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resource
- [http://docs.mongodb.org/manual/reference/method/db.collection.remove/](http://docs.mongodb.org/manual/reference/method/db.collection.remove/)

## My Solution

```js
var mongo = require('mongodb').MongoClient;

var url = 'mongodb://localhost:27017/' + process.argv[2];
mongo.connect(url, function(err, db) {
  if (err) throw err;
  var collection = db.collection(process.argv[3]);
  collection.remove({
    _id: process.argv[4]
  }, function(err) {
    if (err) throw err;
    db.close();
  })
})
```

# Count
Here we will learn how to count the number of documents that meet certain criteria.

Use the parrots collection to count all documents where age is greater than the first argument passed to your script.

Using console.log, print the number to stdout.

## HINTS
To count the number of documents meeting certain criteria, we must use the collection.count() function.

Here is an example:

```js
collection.count({
  name: 'foo'
}, function(err, count) {

})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling db.close() after you have finished.

## Resource
- [http://docs.mongodb.org/manual/reference/command/count/](http://docs.mongodb.org/manual/reference/command/count/)

## My Solution

```js
var mongo = require('mongodb').MongoClient;
var url = 'mongodb://localhost:27017/learnyoumongo';

mongo.connect(url, function(err, db) {
  if (err) throw err;
  var collection = db.collection('parrots');
  collection.count({
    age: {
      // greater than integer
      $gt: parseInt(process.argv[2])
    }
  }, function(err, count) {
    if (err) throw err;
    console.log(count);
    db.close();
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
  parrots.count({
    age: {
      $gt: +age
    }
  }, function(err, count) {
    if (err) throw err
    console.log(count)
    db.close()
  })
})
```

# Aggregate
Next up is aggregation. Aggregation allows one to do things like calculate the sum of a field of multiple documents or the average of a field of documents meeting particular criteria.

Say you have a collection named prices. Each price document is modeled like so:

```js
{
  "name": "Tshirt",
  "size": "S",
  "price": 10,
  "quantity": 12
  "meta": {
    "vendor": "hanes",
    "location": "US"
  }
}
```

In this exercise, we need to calculate the average price for all documents in prices that have the **size** that will be passed as the first argument to your script.

Use `console.log()` to print the average price rounded to 2 decimal places to stdout after you have found it.

## HINTS
To use the `aggregate()` function, one first needs the collection. The `aggregate()` function takes an array of objects as the first argument.

This array will contain the different pipelines for the aggregation. To read more about pipelines, please visit [Aggregation](http://docs.mongodb.org/manual/core/aggregation-introduction/).

The two main pipeline stages we will use will be $match and $group.

### $match
$match is used similar to the way a query is done. It allows us to select the documents that meet certain criteria.

Ex.

```js
var match = { $match: { status: 'A' } }
```

The above example will match all of the documents that have a status property equal to A.

### $group
$group is what allows us to run operations on certain properties.

So, say we wanted to get the sum of the values of the property value where status is equal to A and have it placed in the total property.

Ex.

```js
// [
//  { status: 'A', value: 1 },
//  { status: 'B', value: 2 },
//  { status: 'A', value: 10 }
// ]

collection.aggregate([
  { $match: { status: 'A' }}
, { $group: {
    _id: 'total' // This can be an arbitrary string in this case
  , total: {
      // $sum is the operator used here
      $sum: '$value'
    }
  }}
]).toArray(function(err, results) {
  // handle error
  console.log(results)
  // => [
  // =>   { _id: 'total', total: 11 }
  // => ]
})
```

Other operators used in the $group stage include:
- `$avg`
- `$first`
- `$last`
- `$max`
- `$min`
- `$push`
- `$addToSet`

# Rounding
The Number prototype contains a function `toFixed()`, which accepts the number of decimal places you would like to round to, and returns a string representation.

```js
  var value = "1"
  Number(value).toFixed(5)
  // => '1.00000'
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling db.close() after you have finished.

## Resources
- [http://docs.mongodb.org/manual/aggregation/](http://docs.mongodb.org/manual/aggregation/)
- [http://docs.mongodb.org/manual/core/aggregation-introduction/](http://docs.mongodb.org/manual/core/aggregation-introduction/)

## My Solution

```js
var mongo = require('mongodb').MongoClient;
var url = 'mongodb://localhost:27017/learnyoumongo';

mongo.connect(url, function(err, db) {
  if (err) throw err;
  var collection = db.collection('prices');
  collection.aggregate([
    { $match: { size: process.argv[2] } }
  , { $group: {
      _id: 'total' // This can be an arbitrary string in this case
    , total: {
        // $sum is the operator used here
        $avg: '$price'
      }
    }}
  ]).toArray(function(err, results) {
    // handle error
    if (err) throw err
    console.log(Number(results[0].total).toFixed(2))
    db.close()
  })
})
```

Official Solution:

```js
var mongo = require('mongodb').MongoClient
var size = process.argv[2]

var url = 'mongodb://localhost:27017/learnyoumongo'

mongo.connect(url, function(err, db) {
  if (err) throw err
  var prices = db.collection('prices')
  prices.aggregate([{
    $match: {
      size: size
    }
  }, {
    $group: {
      _id: 'total',
      total: {
        $avg: '$price'
      }
    }
  }]).toArray(function(err, results) {
    if (err) throw err
    if (!results.length) {
      throw new Error('No results found')
    }
    var o = results[0]
    console.log(Number(o.total).toFixed(2))
    db.close()
  })
})
```
