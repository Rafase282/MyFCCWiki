# Details

* Difficulty: 3/5

Fill in the object constructor with the methods specified in the tests.

Those methods are:
* getFirstName()
* getLastName()
* getFullName()
* setFirstName(first)
* setLastName(last)
* setFullName(firstAndLast)

All functions that take an argument have an arity of 1, and the argument will be a string.

These methods must be the only available means for interacting with the object.

# Useful Links

* [Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* [Details of the Object Model](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model)

# My code

```
var Person = function(firstAndLast) {
    
    var fullName = firstAndLast;
    var arr = fullName.split(' ');
    
    this.getFirstName = function() {
        return arr[0];
    };
    this.getLastName = function() {
        return arr[1];
    };
    this.getFullName = function() {
        return fullName;
    };
    this.setFirstName = function(first) {
        arr[0] = first;
    };
    this.setLastName = function(last) {
        arr[1] = last;
    };
    this.setFullName = function(firstAndLast) {
        fullName = firstAndLast;
    };
};
```
# Problem Script:

```
var Person = function(firstAndLast) {
    return firstAndLast;
};

var bob = new Person('Bob Ross');
bob.getFullName();
```
## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)