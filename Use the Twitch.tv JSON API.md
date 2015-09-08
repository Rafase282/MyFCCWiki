# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Objective:
Build a CodePen.io app that successfully reverse-engineers this: [http://codepen.io/GeoffStorbeck/full/GJKRxZ](http://codepen.io/GeoffStorbeck/full/GJKRxZ).

## Rules:
1. Don't look at the example project's code on CodePen. Figure it out for yourself.
2. You may use whichever libraries or APIs you need.
3. Reverse engineer the example project's functionality, and also feel free to personalize it.

## User Stories:
In software development and product management, a user story is a description consisting of one or more sentences in the everyday or business language of the end user or user of a system that captures what a user does or needs to do as part of his or her job function.
- As a user, I can see whether Free Code Camp is currently streaming on Twitch.tv.
- As a user, I can click the status output and be sent directly to the Free Code Camp's Twitch.tv channel.
- As a user, if Free Code Camp is streaming, I can see additional details about what they are streaming.
- As a user, I can search through the streams listed.
- As a user, I will see a placeholder notification if a streamer has closed their Twitch account. You can verify this works by adding brunofin and comster404 to your array of Twitch streamers.

## Hints:
1. Here's an example call to Twitch.tv's JSON API: [https://api.twitch.tv/kraken/streams/freecodecamp](https://api.twitch.tv/kraken/streams/freecodecamp).
2. The relevant documentation about this API call is here: [https://github.com/justintv/Twitch-API/blob/master/v3_resources/streams.md#get-streamschannel](https://github.com/justintv/Twitch-API/blob/master/v3_resources/streams.md#get-streamschannel).
3. Here's an array of the Twitch.tv usernames of people who regularly stream coding: `["freecodecamp", "storbeck", "terakilobyte", "habathcx","RobotCaleb","thomasballinger","noobs2ninjas","beohoff"]`

## Notes:
**Do not use templates for this zipline.**

CodePen.io overrides the `Window.open()` function, so if you want to open windows using jQuery, you will need to target invisible anchor elements like this one: `<a target='_blank'>`.

## My HTML Code Snippets
## My CSS Code Snippets
## My JavaScript Code Snippets
## Extras:
- [Search Bar](http://bootsnipp.com/snippets/featured/expanding-search-button-in-css)