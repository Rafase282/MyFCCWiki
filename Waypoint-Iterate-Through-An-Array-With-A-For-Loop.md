# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Waypoint: Iterate Through an Array with a For Loop
A common task in Javascript is to iterate through the contents of an array. One way to do that is with a `for` loop. This code will output each element of the array `arr` to the console:

```js
    var arr = [10,9,8,7,6];
    for (var i=0; i < arr.length; i++) {
       console.log(arr[i]);
    }
```

Remember that Arrays have zero-based numbering, which means the last index of the array is `length - 1
`. Our `condition` for this loop is `i < arr.length`, which stops when `i` is at `length - 1`.
