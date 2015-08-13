# Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128) submitted by Rafase282

[Github](https://github.com/Rafase282) |
[FreeCodeCamp](http://www.freecodecamp.com/rafase282) | 
[CodePen](http://codepen.io/Rafase282/) |
[LinkedIn](https://www.linkedin.com/in/rafase282) |
[Blog/Site](https://rafase282.wordpress.com/) |
[My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Functional Programming in Javascript

* [Original Source](http://jhusain.github.io/learnrx/)

>Functional programming provides developers with the tools to abstract common collection operations into reusable, composable building blocks. You'll be surprised to learn that most of the operations you perform on collections can be accomplished with five simple functions:

* [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* concatAll
* [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
* zip

The functions hold the key to simplying asynchronous programming, and more durable code overall. You will learn hwo to avoid race conditions, propagate and handle asynchonous erros and more.

# Working with Arrays

>The Array is Javascript's only collection type. Arrays are everywhere. We're going to add the five functions to the Array type, and in the process make it much more powerful and useful. As a matter of fact, Array already has the map, filter, and reduce functions! However we're going to to reimplement these functions as a learning exercise.

This section will follow a pattern. First we'll solve problems the way you probably learned in school, or on your own by reading other peoples code. In other words, we'll transform collections into new collections using loops and statements. Then we'll implement one of the five functions, and then use it to solve the same problem again without the loop. Once we've learned the five functions, you'll learn how to combine them to solve complex problems with very little code.

## Traversing an Array

* **Exercise 1: Print all the names in an array**
```
function(console) {
	var names = ["Ben", "Jafar", "Matt", "Priya", "Brian"],
		counter;

	for(counter = 0; counter < names.length; counter++) {
		console.log(names[counter]);
	}
}
```
>Ask yourself this question: **did we need to specify the order in which the names were printed?** If not, why do it?

* **Exercise 2: Use forEach to print all the names in an array**

```
function(console) {
	var names = ["Ben", "Jafar", "Matt", "Priya", "Brian"];

	names.forEach(function(name) {
		console.log(name);
	});
}
```
With the usae of **forEach** we can tell the program what we want to happen to each element, but it does not show how it traverses the array unlike the previous code.

## Projecting Arrays

Applying a function to a value and creating a new value is called a projection. To project one array into another, we apply a projection function to each item in the array and collect the results in a new array.

* **Exercise 3: Project an array of videos into an array of {id,title} pairs using forEach()**

For each video, add a projected {id, title} pair to the videoAndTitlePairs array.

```
function() {
	var newReleases = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id:432534, time:65876586 }]
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id:432534, time:65876586 }]
			}
		],
		videoAndTitlePairs = [];
  
	// ------------ INSERT CODE HERE! -----------------------------------
	// Use forEach function to accumulate {id, title} pairs from each video.
	// Put the results into the videoAndTitlePairs array using the Array's
	// push() method. Example: videoAndTitlePairs.push(newItem);
	// ------------ INSERT CODE HERE! -----------------------------------

	newReleases.forEach(function(video) {
		videoAndTitlePairs.push({id:video.id, title: video.title});
	});

	return videoAndTitlePairs;
}
```
All array projections share two operations in common:

* Traverse the source array
* Add each item's projected value to a new array

Why not abstract away how these operations are carried out?

* **Exercise 4: Implement map()**

To make projections easier, let's add a **map()** function to the Array type. Map accepts the projection function to be applied to each item in the source array, and returns the projected array.

```
Array.prototype.map = function(projectionFunction) {
	var results = [];
	this.forEach(function(itemInArray) {

		// ------------ INSERT CODE HERE! ----------------------------
		// Apply the projectionFunction to each item in the array and add
		// each result to the results array.
		// Note: you can add items to an array with the push() method.
		// ------------ INSERT CODE HERE! ----------------------------
    
    results.push(projectionFunction(itemInArray));

	});

	return results;
};

// JSON.stringify([1,2,3].map(function(x) { return x + 1; })) === '[2,3,4]'
```
* **Exercise 5: Use map() to project an array of videos into an array of {id,title} pairs**

Let's repeat the exercise of collecting {id, title} pairs for each video in the newReleases array, but **this time we'll use our map function.**

```
function() {
	var newReleases = [
		{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": [4.0],
			"bookmark": []
		},
		{
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": [5.0],
			"bookmark": [{ id:432534, time:65876586 }]
		},
		{
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": [4.0],
			"bookmark": []
		},
		{
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": [5.0],
			"bookmark": [{ id:432534, time:65876586 }]
		}
	];

	// ------------ INSERT CODE HERE! -----------------------------------
	// Use map function to accumulate {id, title} pairs from each video.
	//return newReleases.map finish this expression!
	// ------------ INSERT CODE HERE! -----------------------------------

  return newReleases.map(function(video) {
    return {id: video.id, title: video.title};});
}
```

**Remember that Map always requires us to create a function.**

Notice that map allows us to specify what projection we want to apply to an array, but hides how the operation is carried out.

## Filtering Arrays

>Like projection, filtering an array is also a very common operation. To filter an array we apply a test to each item in the array and collect the items that pass into a new array.

* **Exercise 6: Use forEach() to collect only those videos with a rating of 5.0**

Use forEach() to loop through the videos in the newReleases array and, if a video has a rating of 5.0, add it to the videos array.

```
function() {
	var newReleases = [
		{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		},
		{
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{ id:432534, time:65876586 }]
		},
		{
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		},
		{
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{ id:432534, time:65876586 }]
		}
	],
	videos = [];

	// ------------ INSERT CODE HERE! -----------------------------------
	// Use forEach function to accumulate every video with a rating of 5.0
	// ------------ INSERT CODE HERE! -----------------------------------

  newReleases.forEach(function(video) {
    if (video.rating === 5.0) {
      videos.push(video);}
  });
    
	return videos;
}
```
Notice that, like **map()**, every **filter()** operation shares some operations in common:

* Traverse the array
* Add objects that pass the test to a new array

Why not abstract away how these operations are carried out?

* **Exercise 7: Implement filter()**

To make filtering easier, let's add a filter() function to the Array type. The filter() function accepts a predicate. A predicate is a function that accepts an item in the array, and returns a boolean indicating whether the item should be retained in the new array.


## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)