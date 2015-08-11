# Details

* Difficulty: 2/5

Flatten a nested array. You must account for varying levels of nesting.

# Useful Links

* [Array.isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)

# My code:

```
function steamroller(arr) {
	var flattenedArray = [];
	// Create function that adds an element if it is not an array.
	// If it is an array, then loops through it and uses recursion on that array.
	var flatten = function (arg) {
		if (!Array.isArray(arg)){
			flattenedArray.push(arg);
		} else {
			for (var a in arg) {
				flatten(arg[a]);
			}
		}
	};
	// Call the function for each element in the array
	arr.forEach(flatten);
	return flattenedArray;
}
```

# Problem Script:

```
function steamroller(arr) {
  // I'm a steamroller, baby
  return arr;
}

steamroller([1, [2], [3, [[4]]]]);
```

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)