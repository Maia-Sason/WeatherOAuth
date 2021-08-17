# Weather Location

Purpose of this web application is to display weather information in a sleek way based on where you are in the world and store your location for next time so that the next time you check Weather Location, your previous locations' current weather will show up as well.

### Live Demo:
https://weatherlocation.herokuapp.com/login

## How it works

User authenticates with Facebook on client side -> client side talks to server which talks to Facebook through Passport's API -> Facebook sends callback to `/return` -> (If user is new user, they are saved to database and they get their own table for locations) -> which sends a response of the homepage after deserializing the user -> client side recieves information that user is indeed authenticated. It goes ahead and fetches user's information, then user's Geolocation using Geolocation api ->
sends location and saves it to localStorage for faster loading on subsequent visits -> fetches current weather -> goes to server -> server asks OpenWeatherMap to output current weather -> relays back to client side.

Client side also asks for all weather from server -> server sends information with all weather information for each location in user's table.

If user does not allow location services on load, WeatherLocation will display an error message and will attempt to request geolocation every 5 seconds 10 additional times before stopping and displaying a manual button for reconnecting. Because of memoized location information, if the user loads the website at least once without clearing their local storage the site will load faster and even if location services are not available, it will return the localStorage's location's current weather.

The main image of the page will change based on the current weather. If there's a thunderstorm in your location (and OpenWeatherMap knows too!) the main image will be a thunderstorm.

### Technologies used

**Backend:** NodeJS, Express, Axios, OAuth2, Passport, Passport-Facebook

**Frontend:** React, React-Redux, Thunk, Material-UI, React-Three-Fiber, Axios, React-Swipeable-Views, React-Wavify, Geolocation API

**API For Weather:** OpenWeatherMap

## Design

I wanted to have a very nice and clean looking design for this project, I found great inspiration from [Arthur K](https://dribbble.com/shots/7118235-Weather-DailyUI-037) on Dribbble.com.

For the hero page, I wanted something sleek and modern that succinctly explained the purpose of this app.
