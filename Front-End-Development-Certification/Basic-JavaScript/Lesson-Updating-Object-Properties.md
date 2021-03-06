# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [E-Mail](mailto:rafase282@gmail.com)

# Updating Object Properties
After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let's look at `ourDog`:
```js
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```
Since he's a particularly happy dog, let's change his name to "Happy Camper". Here's how we update his object's name property:

`ourDog.name = "Happy Camper";` or

`ourDog["name"] = "Happy Camper";`

Now when we evaluate `ourDog.name
`, instead of getting "Camper", we'll get his new name, "Happy Camper".
