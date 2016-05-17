### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Remove

This lesson involves removing a document with the given `_id`.

The database name will be accessible via `process.argv[2]`.

The collection name will be passed as the second argument to your script.

The `_id` will be passed as the third argument to your script.

## HINTS

To remove a document, one would need to call `remove()` on the collection.

Ex.

```javascript
collection.remove({
  name: 'foo'
}, callback)
```

The first argument to `remove()` is the query.

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling `db.close()` after you have finished.

## Resource

- <http://docs.mongodb.org/manual/reference/method/db.collection.remove/>

## My Solution

```javascript
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
