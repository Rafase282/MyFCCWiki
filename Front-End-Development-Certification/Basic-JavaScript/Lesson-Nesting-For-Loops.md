# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Lesson: Nesting For Loops
If you have a multi-dimensional array, you can use the same logic as the prior lesson `Iterate Through an Array with a For Loop` to loop through both the array and any sub-arrays. Here is an example:

```js
    var arr = [
      [1,2], [3,4], [5,6]
    ];
    for (var i=0; i < arr.length; i++) {
      for (var j=0; j < arr[i].length; j++) {
        console.log(arr[i][j]);
      }
    }
```

This outputs each sub-element in `arr` one at a time. Note that for the inner loop, we are checking the `.length` of `arr[i]`, since `arr[i]` is itself an array.
