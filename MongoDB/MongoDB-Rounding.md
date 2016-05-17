### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Rounding

The Number prototype contains a function `toFixed()`, which accepts the number of decimal places you would like to round to, and returns a string representation.

```javascript
  var value = "1"
  Number(value).toFixed(5)
  // => '1.00000'
```

If your program does not finish executing, you may have forgotten to close the db. That can be done by calling db.close() after you have finished.

## Resources

- <http://docs.mongodb.org/manual/aggregation/>
- <http://docs.mongodb.org/manual/core/aggregation-introduction/>

## My Solution

```javascript
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

## Official Solution:

```javascript
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
