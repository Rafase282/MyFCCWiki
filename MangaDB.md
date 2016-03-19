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

## Implement Flash Messages with jade
Flash messages allows the app to share important and useful information just once and they reside in flash memory.

It is important to know that if you call it once to test, it will not work the second time. Once again, the message is displayed **once**.

To implement it, you first need to install [connect-flash](https://www.npmjs.com/package/connect-flash).

```bash
npm install --save connect-flash
```

This will save it to your `package.json` file where you will see something like this `"connect-flash": "^0.1.1"`.

You will need to add the following to your server:

```js
var flash = require('connect-flash');
app.use(flash());
```

Then you can create a flash message in the following way:

```js
req.flash('info', 'Flash is back!')
```

That is, identifier, and data. Just make sure that you put it before your `res` code. Then you display it with your render.

```js
res.render('index', { messages: req.flash('info') });
```

If you want multiple messages to be handled then you can use something like this in jade:

```jade
.container-fluid
  if msg.error && msg.error.length
    .alert.alert-danger
      div= msg.error
  if msg.info && msg.info.length
    .alert.alert-info
      div= msg.info
  if msg.success && msg.success.length
    .alert.alert-success
      div= msg.success
```

To take advantage of bootstrap custom alert panels and to handle the case where there is no indo at all.
