# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/AdventureBear/full/yNBJRj](http://codepen.io/AdventureBear/full/yNBJRj).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
1. As a user, I can see the weather in my current location.
2. As a user, I can see an icon depending on the temperature.
3. As a user, I see a different background image depending on the temperature (e.g. snowy mountain, hot desert).
4. As a user, I can push a button to toggle between Fahrenheit and Celsius.

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets
I have the standard head and end of body. The only thing different is that I have a `well` class and `p` tag with the weather `id` which is where the custom jQuery generated HTML will go. I also used `text-primary` and `bg-info` classes to give the headings more visibility regardless of the custom background.

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Local Weather</title>
  <link rel='stylesheet prefetch' href='http://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css'>
  <link rel='stylesheet prefetch' href='https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css'>
  <link rel="stylesheet" href="css/style.css">
</head>

<body>

  <section class="container-fluid">
    <h1 class='text-primary bg-info'>Free Code Camp Zipline</h1>
    <h2 class='text-primary bg-info'>Local Weather!</h2>
    <div class="well">
      <p id="weather"></p>
      <form action="/select-metric">
        <label>
          <input type="radio" checked name="farenheit-celcius" id="f"> Farenheit</label>
        <label>
          <input type="radio" name="farenheit-celcius" id="c"> Celsius</label>
      </form>
    </div>
  </section>
  <footer>
    <p>Copyright © Rafael J. Rodriguez 2015. All Rights Reserved</p>
  </footer>

  <script src='http://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js'></script>
  <script src='http://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js'></script>
  <script src="js/index.js"></script>

</body>

</html>
```

## My CSS Code Snippets
### Make things centered and styled
- Here I centered things either using `text-align` or `margins` and also gave font styling.

```css
p, form {
  text-align: center;
  font-family: "Georgia";
}
p {
  font-size: 20px;
}
.well {
  margin-left: 35%;
  margin-right: 35%;
}
h1, h2 {
  margin-left: 35%;
  margin-right: 35%;
  text-align: center;
  font-family: "Georgia";
}
```

### The rest of the styling
- I made the one section I have take a active screen space of 90% while the footer will take the remainder 10% to have the whole page visible.
- I gave my usual styling to the footer, centered on all directions.
- I made the body relative and custom styles for the background such as centered on top, no repeating and taking the whole section.
- I also gave the weather icons a custom size for better visibility.

```css
footer {
  min-height: 10vh;
  padding-top: 30px;
  padding-bottom: 1px;
  color: gray;
  background-color: black;
}
section {
  min-height: 90vh;
}
body {
  position: relative;
  background-repeat: no-repeat;
  background-position: center top;
  background-size: cover;
}

img {
  width: 100px;
  height: 100px;
}
```

## My JavaScript Code Snippets
### Location API callback Function
- The location API is [http://ip-api.com/json](http://ip-api.com/json) and it gets the location via `IP` address, this is the information we receive:

```js
{
  "as": "AS6128 Cablevision Systems Corp.",
  "city": "The Bronx",
  "country": "United States",
  "countryCode": "US",
  "isp": "Optimum Online",
  "lat": xx.yyyy,
  "lon": -xx.yyyy,
  "org": "Optimum Online",
  "query": "xx.xxx.xx.xx",
  "region": "NY",
  "regionName": "New York",
  "status": "success",
  "timezone": "America/New_York",
  "zip": "xxxxx"
}
```

- From there I get the `lat`, `lon`, `city`,`region` and use it to generate the custom url for the weather API. However, this url is incomplete as I need to know if I need the `imperial` or `metric`. Please note that the weather callback function is on the scope of this function so I can use it's information without generating more global variables like `url`.

```js
// Function to work with Location API to get Longitude, Latitude, City and State to bed used with the weather API
var getLocation = function (data) {
  var lat = data.lat
  var lon = data.lon
  var city = data.city
  var state = data.regionName
  // Custom url for the weather API, it is only missing imperial or metric format.
  url = 'http://api.openweathermap.org/data/2.5/weather?' + 'lat=' + lat + '&lon=' + lon + '&units='
```

### Weather API callback Function
- This function is global because we need to call it outside the scope of the Location API and outside the when ready status.
- We declare a variable for which system we want with a default of `imperial`
- I used ternary operators to check if the variable mentioned earlier is `metric` or `imperial` and then Assign the `C` or `F` accordingly. Furthermore, it uses the same methodology for the wind speed units.
- It gets the needed information and along with the information from the Location API it generates custom HTML to be displayed using: `$('#weather').html(html)`
- The information obtained from the Weather [API](http://api.openweathermap.org/data/2.5/weather?lat=10&lon=-95&units=imperial) is this (coordinates are random to avoid giving real personal data):

```js
{
  "coord": {
    "lon": -xx.yy,
    "lat": xx.yy
  },
  "weather": [{
    "id": 802,
    "main": "Clouds",
    "description": "scattered clouds",
    "icon": "03n"
  }],
  "base": "cmc stations",
  "main": {
    "temp": 62.04,
    "pressure": 1022,
    "humidity": 56,
    "temp_min": 51.8,
    "temp_max": 71.6
  },
  "wind": {
    "speed": 2.07,
    "deg": 293.003
  },
  "clouds": {
    "all": 40
  },
  "dt": 1440832823,
  "sys": {
    "type": 1,
    "id": 2120,
    "message": 0.0044,
    "country": "US",
    "sunrise": 1440843553,
    "sunset": 1440891147
  },
  "id": 5116119,
  "name": "County-name",
  "cod": 200
}
```

```js
var units = 'imperial'
// Function to get the Weather info and display it.
  getWeather = function (data) {
    var temp = data.main.temp
    var tempUnit = units === 'metric' ? 'C' : 'F'
    var windUnit = units === 'metric' ? ' meters/s' : ' miles/h'
    var description = data.weather[0].description
    var code = data.weather[0].icon
    var wspeed = data.wind.speed
    // Create custom HTML to display all the information gathered.
    var html = '<img src="http://openweathermap.org/img/w/' + code + '.png" alt="Weather Icon">' + '<p> ' + Math.round(temp) + ' ' + tempUnit + ', ' + description + '<br> Wind Speed: ' + wspeed + windUnit + '</p><p>' + city + ', ' + state + '</p>'
    // Displays the custom HTML
    $('#weather').html(html)
```

#### Handling Custom Background Images
- I use a switch to check whether I'll be working with Imperial or metric. The create arrays with their respective temperatures from the hottest threshold to the coldest.
- Then I create an array of images in the same order, from hottest to coldest.
- The I use a combination of `if else if else` to cover the different cases and use `$('body').css('background-image', imgs[0])` to give custom `CSS` properties with the background image.
- Then I call the Weather API. `$.getJSON(url + 'imperial', getWeather, 'jsonp')` I use imperial as default.

```js
// Checks what kind style of temperature was used for dynamic background image.
    switch (tempUnit) {
      case 'F':
        var temps = [90, 70, 32]
        break
      case 'C':
        temps = [32, 21, 0]
        break
    }
    // Array of backgroudn images.
    var imgs = ['url("http://i.imgur.com/eI5KLUW.jpg")', 'url("http://i.imgur.com/rG0P1ro.jpg")', 'url("http://i.imgur.com/voCuONs.jpg")', 'url("http://i.imgur.com/5tFHSKa.jpg")']
    // Select custom backgroudn image according to temperature range.
    if (temp >= temps[0]) {
      $('body').css('background-image', imgs[0])
    } else if (temp < temps[0] && temp >= temps[1]) {
      $('body').css('background-image', imgs[1])
    } else if (temp < temps[1] && temp >= temps[2]) {
      $('body').css('background-image', imgs[2])
    } else if (temp < temps[2]) {
      $('body').css('background-image', imgs[3])
    }
  }
  // Calls the Weather API
  $.getJSON(url + 'imperial', getWeather, 'jsonp')
}
```

### jQuery Handler
- When the page is finished loading I call the Location API which then also calls the weather API to display the default weather information with custom location.
- Then I have a radio button change handler to select between metric and imperial for the new weather.
- The app calls the APIs each time it loads and whenever you switch between metric and imperial so you don't have to refresh the page to get new updated weather.

```js
// When the documet finished loading call the Location API
$(document).ready(function () {
  $.getJSON('http://ip-api.com/json', getLocation, 'jsonp')
  // Handler for opetion between Metric and Imperial style temperature
  $('input[type=radio][name=farenheit-celcius]').change(function () {
    if ($('#f').is(':checked')) {
      units = 'imperial'
    } else {
      units = 'metric'
    }
    $.getJSON(url + units, getWeather, 'jsonp')
  })
})
```
