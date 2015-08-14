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

* **Exercise 8: Chain filter and map to collect the ids of videos that have a rating of 5.0**

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

* **Exercise 9: Flatten the movieLists array into an array of video ids**

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

* **Exercise 10: Implement concatAll()** I was right!

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

* **Exercise 11: Use map() and concatAll() to project and flatten the movieLists into an array of video ids**

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

* **Exercise 12: Retrieve id, title, and a 150x200 box art url for every video**

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

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)