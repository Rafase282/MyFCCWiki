### Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Medium](https://medium.com/@Rafase282) [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# MongoDB Aggregate

Next up is aggregation. Aggregation allows one to do things like calculate the sum of a field of multiple documents or the average of a field of documents meeting particular criteria.

Say you have a collection named prices. Each price document is modeled like so:

```javascript
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

```javascript
var match = { $match: { status: 'A' } }
```

The above example will match all of the documents that have a status property equal to A.

### $group

$group is what allows us to run operations on certain properties.

So, say we wanted to get the sum of the values of the property value where status is equal to A and have it placed in the total property.

Ex.

```javascript
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
