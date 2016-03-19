# Notes on things I have learned along the way
## How to Run Code in Specific Page
There regular way to run JavaScript when a page loads is with:

```js
$(document).ready(callback);
```

However, whether you are using templates or plain HTML, you can specify the page you would like to run the code in by changing `document` to a class name that you would add to the top most level of your `div`.

```js
/* Load Manga info when page is loaded
 * When the profile page is read it will
 * call the function to get all mangas.
 */
$('.user-profile').ready(getMangas);
```
