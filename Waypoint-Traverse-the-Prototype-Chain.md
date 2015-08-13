# Author

![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128) submitted by Rafase282 | https://github.com/Rafase282

* FreeCodeCamp Profile: http://www.freecodecamp.com/rafase282
* CodePed Profile: http://codepen.io/Rafase282/
* LinkedIn: https://www.linkedin.com/in/rafase282


## Create an object:

```
var gold = {a:1}
log(gold.a) // 1
log(gold.z) // undefined
```

There are two ways to create a copy of the object, a one time hardcorpy and a onetime with looup tot he original object.

The first method is the following:

```
var blue = extend({}, gold);
blue.b = 2;
log(blue.a); // 1
log(blue.b); // 2
log(blue.z); /// undefined
```

The second method which allows you to find keys that are on the original object is this:

```
var rose = Object.create(gold);
rose.b = 2;
log(rose.a); // 1
log(rose.b); // 2
log(rose.z) // undefined

gold.z = 3;
log(blue.z); // undefined
log(rose.z); // 3
```
## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)