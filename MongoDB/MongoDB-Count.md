### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Count

Here we will learn how to count the number of documents that meet certain criteria.

Use the parrots collection to count all documents where age is greater than the first argument passed to your script.

Using console.log, print the number to stdout.

## HINTS

To count the number of documents meeting certain criteria, we must use the collection.count() function.

Here is an example:

```javascript
collection.count({
  name: 'foo'
}, function(err, count) {

})
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resource

- <http://docs.mongodb.org/manual/reference/command/count/>

## My Solution

```javascript
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

## Official Solution:

```javascript
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
