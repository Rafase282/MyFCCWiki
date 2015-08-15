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

# Links to the Excercises:

* [Exercise 1: Print all the names in an array](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-1-print-all-the-names-in-an-array)
* [Exercise 2: Use forEach to print all the names in an array](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-2-use-foreach-to-print-all-the-names-in-an-array)
* [Exercise 3: Project an array of videos into an array of {id,title} pairs using forEach()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-3-project-an-array-of-videos-into-an-array-of-idtitle-pairs-using-foreach)
* [Exercise 4: Implement map()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-4-implement-map)
* [Exercise 5: Use map() to project an array of videos into an array of {id,title} pairs](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-5-use-map-to-project-an-array-of-videos-into-an-array-of-idtitle-pairs)
* [Exercise 6: Use forEach() to collect only those videos with a rating of 5.0](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-6-use-foreach-to-collect-only-those-videos-with-a-rating-of-50)
* [Exercise 7: Implement filter()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-7-implement-filter)
* [Exercise 8: Chain filter and map to collect the ids of videos that have a rating of 5.0](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-8-chain-filter-and-map-to-collect-the-ids-of-videos-that-have-a-rating-of-50)
* [Exercise 9: Flatten the movieLists array into an array of video ids](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-9-flatten-the-movielists-array-into-an-array-of-video-ids)
* [Exercise 10: Implement concatAll()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-10-implement-concatall)
* [Exercise 11: Use map() and concatAll() to project and flatten the movieLists into an array of video ids](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-11-use-map-and-concatall-to-project-and-flatten-the-movielists-into-an-array-of-video-ids)
* [Exercise 12: Retrieve id, title, and a 150x200 box art url for every video](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-12-retrieve-id-title-and-a-150x200-box-art-url-for-every-video)
* [Exercise 13: Implement concatMap()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-13-implement-concatmap)
* [Exercise 14: Use concatMap() to retrieve id, title, and 150x200 box art url for every video](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-14-use-concatmap-to-retrieve-id-title-and-150x200-box-art-url-for-every-video)
* [Exercise 15: Use forEach to find the largest box art](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-15-use-foreach-to-find-the-largest-box-art)
* [Exercise 16: Implement reduce()](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-16-implement-reduce)
* [Exercise 17: Retrieve the largest rating](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-17-retrieve-the-largest-rating)
* [Exercise 18: Retrieve url of the largest boxart](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-18-retrieve-url-of-the-largest-boxart)
* [Exercise 19: Reducing with an initial value](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-19-reducing-with-an-initial-value)
* [Exercise 20: Retrieve the id, title, and smallest box art url for every video](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki/Waypoint-Practice-Functional-Programming#exercise-20-retrieve-the-id-title-and-smallest-box-art-url-for-every-video)


# Working with Arrays

>The Array is Javascript's only collection type. Arrays are everywhere. We're going to add the five functions to the Array type, and in the process make it much more powerful and useful. As a matter of fact, Array already has the map, filter, and reduce functions! However we're going to to reimplement these functions as a learning exercise.

This section will follow a pattern. First we'll solve problems the way you probably learned in school, or on your own by reading other peoples code. In other words, we'll transform collections into new collections using loops and statements. Then we'll implement one of the five functions, and then use it to solve the same problem again without the loop. Once we've learned the five functions, you'll learn how to combine them to solve complex problems with very little code.

## Traversing an Array

### Exercise 1: Print all the names in an array
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

### Exercise 2: Use forEach to print all the names in an array

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

### Exercise 3: Project an array of videos into an array of {id,title} pairs using forEach()

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

### Exercise 4: Implement map()

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
### Exercise 5: Use map() to project an array of videos into an array of {id,title} pairs

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

### Exercise 6: Use forEach() to collect only those videos with a rating of 5.0

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

### Exercise 7: Implement filter()

To make filtering easier, let's add a filter() function to the Array type. The filter() function accepts a predicate. A predicate is a function that accepts an item in the array, and returns a boolean indicating whether the item should be retained in the new array.

```
Array.prototype.filter = function(predicateFunction) {
	var results = [];
	this.forEach(function(itemInArray) {
		// ------------ INSERT CODE HERE! ----------------------------
		// Apply the predicateFunction to each item in the array.
		// If the result is truthy, add the item to the results array.
		// Note: remember you can add items to the array using the array's
		// push() method.
		// ------------ INSERT CODE HERE! ----------------------------
    
    if (predicateFunction(itemInArray)) {
      results.push(itemInArray);
    }
	});

	return results;
};

// JSON.stringify([1,2,3].filter(function(x) { return x > 2})) === "[3]"
```

Like map(), filter() lets us express what data we want without requiring us to specify how we want to collect the data.

## Query Data by Chaining Method Calls

### Exercise 8: Chain filter and map to collect the ids of videos that have a rating of 5.0

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
	];

	// ------------ INSERT CODE HERE! -----------------------------------
	// Chain the filter and map functions to select the id of all videos
	// with a rating of 5.0.

	//return newReleases  Complete this expression
	// ------------ INSERT CODE HERE! -----------------------------------
  return newReleases.filter(function(video) {
    if (video.rating === 5.0) {
      return video
    }
  }).map(function(video) {
    return video.id
  });
}
```
>Chaining together map() and filter() gives us a lot of expressive power. These high level functions let us express what data we want, but leave the underlying libraries a great deal of flexibility in terms of how our queries are executed.

## Querying Trees

>Sometimes, in addition to flat arrays, we need to query trees. Trees pose a challenge because we need to flatten them into arrays in order to apply filter() and map() operations on them.

Here is where I learn how to define an **concatAll()** function so that I can combine with **map()** and **filter()** to query trees.

### Exercise 9: Flatten the movieLists array into an array of video ids

Let's start by using two nested forEach loops collect the id of every video in the two-dimensional movieLists array.

```
function() {
	var movieLists = [
		{
			name: "New Releases",
			videos: [
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
				}
			]
		},
		{
			name: "Dramas",
			videos: [
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
			]
		}
	],
	allVideoIdsInMovieLists = [];

	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use two nested forEach loops to flatten the movieLists into a list of
	// video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------
  
  movieLists.forEach(function(movies) {
    movies.videos.forEach(function(video) {
      allVideoIdsInMovieLists.push(video.id);
    });
  });

	return allVideoIdsInMovieLists;

}
```
>Flattening trees with nested forEach expressions is easy because we can explicitly add items to the array. Unfortunately it's exactly this type of low-level operation that we've been trying to abstract away with functions like map() and filter(). Can we define a function that's abstract enough to express our intent to flatten a tree, without specifying too much information about how to carry out the operation?

I feel this is where **concatAll()** will be create...

### Exercise 10: Implement concatAll()
I was right!

>Let's add a concatAll() function to the Array type. The concatAll() function iterates over each sub-array in the array and collects the results in a new, flat array. Notice that the concatAll() function expects that each item in the array to be another array.

```
Array.prototype.concatAll = function() {
	var results = [];
	this.forEach(function(subArray) {
		// ------------ INSERT CODE HERE! ----------------------------
		// Add all the items in each subArray to the results array.
		// ------------ INSERT CODE HERE! ----------------------------
    
    subArray.forEach(function(arr) {
      results.push(arr)
    });
	});

	return results;
};

// JSON.stringify([ [1,2,3], [4,5,6], [7,8,9] ].concatAll()) === "[1,2,3,4,5,6,7,8,9]"
// [1,2,3].concatAll(); // throws an error because this is a one-dimensional array
```
>concatAll is a very simple function, so much so that it may not be obvious yet how it can be combined with map() to query a tree. Let's try an example...

### Exercise 11: Use map() and concatAll() to project and flatten the movieLists into an array of video ids

Hint: use two nested calls to map() and one call to concatAll().

```
function() {
	var movieLists = [
			{
				name: "New Releases",
				videos: [
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
					}
				]
			},
			{
				name: "Dramas",
				videos: [
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
				]
			}
		];

	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use map and concatAll to flatten the movieLists in a list of video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------

  return movieLists.map(function(movies) {
    return movies.videos.map(function(video) {
      return video.id;
    });
  }).concatAll();

}
```

### Exercise 12: Retrieve id, title, and a 150x200 box art url for every video

>You've managed to flatten a tree that's two levels deep, let's try for three! Let's say that instead of a single boxart url on each video, we had a collection of boxart objects, each with a different size and url. Create a query that selects {id, title, boxart} for every video in the movieLists. This time though, the boxart property in the result will be the url of the boxart object with dimensions of 150x200px. Let's see if you can solve this problem with map(), concatAll(), and filter().

**There's just more one thing: you can't use indexers.** In other words, this is illegal:

```var itemInArray = movieLists[0];```

From this point onwards, indexers are nt allowed in any exercises unless we are implementing one of the five functions.

```
function() {
	var movieLists = [
			{
				name: "Instant Queue",
				videos : [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxarts": [
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" }

						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id:432534, time:65876586 }]
					}
				]
			},
			{
				name: "New Releases",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxarts": [
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
							{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id:432534, time:65876586 }]
					}
				]
			}
		];


	// Use one or more map, concatAll, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];
  


  return movieLists.map(function(movies) {
    return movies.videos.map(function(video) {
      return video.boxarts.filter(function(boxart) {
        return boxart.width === 150 && boxart.height === 200
      }).map(function(boxart) {
        return {id: video.id, title: video.title, boxart: boxart.url}
          });
      }).concatAll();
    }).concatAll();

}
```

This was a bit complilcated and while I had the general ide, I even have to check the answer for the final hint of an added **map()** and two **concatAll()**

* Return a map of the list of movies
* Return from the map of **list of movies** a map of videos from the **videos** array.
* Return a filter of **boxarts** that check for a particular size.
* For the ones that got filtered in, map them.
* From the filtered map, return a new object with id, title, and the url of the boxart filtered.
* Now concat the first two maps.
			
>Notice that map() and concatAll() are very commonly chained together. Let's create a small helper function to help us with this common pattern.

### Exercise 13: Implement concatMap()

>Nearly every time we flatten a tree we chain map() and concatAll(). Sometimes, if we're dealing with a tree several levels deep, we'll repeat this combination many times in our code. To save on typing, let's create a concatMap function that's just a map operation, followed by a concatAll.

```
Array.prototype.concatMap = function(projectionFunctionThatReturnsArray) {
	return this.
		map(function(item) {
			// ------------   INSERT CODE HERE!  ----------------------------
			// Apply the projection function to each item. The projection
			// function will return an new child array. This will create a
			// two-dimensional array.
			// ------------   INSERT CODE HERE!  ----------------------------
      return projectionFunctionThatReturnsArray(item);
		}).
		// apply the concatAll function to flatten the two-dimensional array
		concatAll();
};

/*
	var spanishFrenchEnglishWords = [ ["cero","rien","zero"], ["uno","un","one"], ["dos","deux","two"] ];
	// collect all the words for each number, in every language, in a single, flat list
	var allWords = [0,1,2].
		concatMap(function(index) {
			return spanishFrenchEnglishWords[index];
		});

	return JSON.stringify(allWords) === '["cero","rien","zero","uno","un","one","dos","deux","two"]';
*/
```
Now, instead of using map().concatAll() to flatten a tree, we can just use concatMap helper function.

### Exercise 14: Use concatMap() to retrieve id, title, and 150x200 box art url for every video

Let's repeat the exercise we just performed. However this time we'll simplify the code by replacing the map().concatAll() calls with concatMap().

```
function() {
	var movieLists = [
			{
				name: "Instant Queue",
				videos : [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxarts": [
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" }

						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id:432534, time:65876586 }]
					}
				]
			},
			{
				name: "New Releases",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxarts": [
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
							{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id:432534, time:65876586 }]
					}
				]
			}
		];


	// Use one or more concatMap, map, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

  return movieLists.concatMap(function(movies) {
    return movies.videos.concatMap(function(video) {
      return video.boxarts.filter(function(boxart) {
        return boxart.width === 150 && boxart.height === 200;
      }).map(function(boxart) {
        return {id: video.id, title: video.title, boxart: boxart.url};
      });
    });
  });

}
```
It's a very common pattern to see several nested concatMap operations, with the last operation being a map. You can think of this pattern as the functional version of a nested forEach.

## Reducing Arrays

Sometimes we need to perform an operation on more than one item in the array at the same time. For example, let's say we need to find the largest integer in an array. We can't use a filter() operation, because it only examines one item at a time. To find the largest integer we need to compare items in the array to each other.

One approach could be to select an item in the array as the assumed largest number (perhaps the first item), and then compare that value to every other item in the array. Each time we come across a number that was larger than our assumed largest number, we'd replace it with the larger value, and continue the process until the entire array was traversed.

If we replaced the specific size comparison with a closure, we could write a function that handled the array traversal process for us. At each step our function would apply the closure to the last value and the current value and use the result as the last value the next time. Finally we'd be left with only one value. This process is known as reducing because we reduce many values to a single value.

### Exercise 15: Use forEach to find the largest box art

In this example we use forEach to find the largest box art. Each time we examine a new boxart we update a variable with the currently known maximumSize. If the boxart is smaller than the maximum size, we discard it. If it's larger, we keep track of it. Finally we're left with a single boxart which must necessarily be the largest.

```
function() {
	var boxarts = [
			{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
			{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
			{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" },
			{ width: 425, height:150, url:"http://cdn-0.nflximg.com/images/2891/Fracture425.jpg" }
		],
		currentSize,
		maxSize = -1,
		largestBoxart;

	boxarts.forEach(function(boxart) {
		currentSize = boxart.width * boxart.height;
		if (currentSize > maxSize) {
			largestBoxart = boxart;
			maxSize = currentSize;
		}
	});

	return largestBoxart;
}
```
This process is a reduction because we're using the information we derived from the last computation to calculate the current value. However in the example above, we still have to specify the method of traversal. Wouldn't it be nice if we could just specify what operation we wanted to perform on the last and current value? Let's create a helper function to perform reductions on arrays.

### Exercise 16: Implement reduce()

Let's add a reduce() function to the Array type. Like map

```
// [1,2,3].reduce(function(accumulatedValue, currentValue) { return accumulatedValue + currentValue; }); === [6];
// [1,2,3].reduce(function(accumulatedValue, currentValue) { return accumulatedValue + currentValue; }, 10); === [16];

Array.prototype.reduce = function(combiner, initialValue) {
	var counter,
		accumulatedValue;

	// If the array is empty, do nothing
	if (this.length === 0) {
		return this;
	}
	else {
		// If the user didn't pass an initial value, use the first item.
		if (arguments.length === 1) {
			counter = 1;
			accumulatedValue = this[0];
		}
		else if (arguments.length >= 2) {
			counter = 0;
			accumulatedValue = initialValue;
		}
		else {
			throw "Invalid arguments.";
		}

		// Loop through the array, feeding the current value and the result of
		// the previous computation back into the combiner function until
		// we've exhausted the entire array and are left with only one value.
		while(counter < this.length) {
			accumulatedValue = combiner(accumulatedValue, this[counter])
			counter++;
		}
```

### Exercise 17: Retrieve the largest rating.

Let's use our new reduce function to isolate the largest value in an array of ratings

```
function() {
	var ratings = [2,3,1,4,5];

	// You should return an array containing only the largest rating. Remember that reduce always
	// returns an array with one item.
	return ratings.
    reduce(function(a,b) {
      if (a > b) 
        return a;
      else
        return b;
    });
}
```

### Exercise 18: Retrieve url of the largest boxart

Let's try combining reduce() with map() to reduce multiple boxart objects to a single value: the url of the largest box art.

```
function() {
	var boxarts = [
			{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
			{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
			{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" },
			{ width: 425, height:150, url:"http://cdn-0.nflximg.com/images/2891/Fracture425.jpg" }
		];

	// You should return an array containing only the largest box art. Remember that reduce always
	// returns an array with one item.
	return boxarts.
    reduce(function(a,b) {
      if (a.width * a.heigth > b.width * b.height)
        return a;
      else
        return b;
        }).map(function(obj) {
      return obj.url ;
    });
}
		
```

### Exercise 19: Reducing with an initial value

>Sometimes when we reduce an array, we want the reduced value to be a different type than the items stored in the array. Let's say we have an array of videos and we want to reduce them to a single map where the key is the video id and the value is the video's title.

```
function() {
	var videos = [
		{
			"id": 65432445,
			"title": "The Chamber"
		},
		{
			"id": 675465,
			"title": "Fracture"
		},
		{
			"id": 70111470,
			"title": "Die Hard"
		},
		{
			"id": 654356453,
			"title": "Bad Boys"
		}
	];

	// Expecting this output...
	// [
	//	 {
	//		 "65432445": "The Chamber",
	//		 "675465": "Fracture",
	//		 "70111470": "Die Hard",
	//		 "654356453": "Bad Boys"
	//	 }
	// ]
	return videos.
		reduce(function(accumulatedMap, video) {

			// Object.create() makes a fast copy of the accumulatedMap by
			// creating a new object and setting the accumulatedMap to be the
			// new object's prototype.
			// Initially the new object is empty and has no members of its own,
			// except a pointer to the object on which it was based. If an
			// attempt to find a member on the new object fails, the new object
			// silently attempts to find the member on its prototype. This
			// process continues recursively, with each object checking its
			// prototype until the member is found or we reach the first object
			// we created.
			// If we set a member value on the new object, it is stored
			// directly on that object, leaving the prototype unchanged.
			// Object.create() is perfect for functional programming because it
			// makes creating a new object with a different member value almost
			// as cheap as changing the member on the original object!

			var copyOfAccumulatedMap = Object.create(accumulatedMap);

			// ----- INSERT CODE TO ADD THE VIDEO TITLE TO THE ----
			// ----- NEW MAP USING THE VIDEO ID AS THE KEY	 ----
      copyOfAccumulatedMap[video.id] = video.title;

			return copyOfAccumulatedMap;
		},
		// Use an empty map as the initial value instead of the first item in
		// the list.
		{});
}
```
### Exercise 20: Retrieve the id, title, and smallest box art url for every video.

>This is a variation of the problem we solved earlier, where we retrieved the url of the boxart with a width of 150px. This time we'll use reduce() instead of filter() to retrieve the smallest box art in the boxarts array.

```
function() {
	var movieLists = [
		{
			name: "New Releases",
			videos: [
				{
					"id": 70111470,
					"title": "Die Hard",
					"boxarts": [
						{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 654356453,
					"title": "Bad Boys",
					"boxarts": [
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
						{ width: 140, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" }

					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id:432534, time:65876586 }]
				}
			]
		},
		{
			name: "Thrillers",
			videos: [
				{
					"id": 65432445,
					"title": "The Chamber",
					"boxarts": [
						{ width: 130, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 675465,
					"title": "Fracture",
					"boxarts": [
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
						{ width: 120, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
						{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id:432534, time:65876586 }]
				}
			]
		}
	];


	// Use one or more concatMap, map, and reduce calls to create an array with the following items (order doesn't matter)
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists.concatMap(function(movieList) {
      return movieList.videos.concatMap(function(video) {
        return video.boxarts.reduce(function(a,b) {
          if (a.width * a.heigth < b.width * b.heigth) {
            return a;
          }
          else {
            return b;
          }
        }).map(function(boxart) {
          return {id: video.id, title: video.title, boxart: boxart.url};
        });
      });
  });
}
```


## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)