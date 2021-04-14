# Weather

<p align="center">
   <a href="https://github.com/fork-my-spoons/weather.spoon/issues">
    <img alt="GitHub issues" src="https://img.shields.io/github/issues/fork-my-spoons/weather.spoon">
  </a>
  <a href="https://github.com/fork-my-spoons/weather.spoon/releases">
    <img alt="GitHub all releases" src="https://img.shields.io/github/downloads/fork-my-spoons/weather.spoon/total">
  </a>
  <a href="https://github.com/fork-my-spoons/weather.spoon/releases">
   <img alt="GitHub release (latest by date)" src="https://img.shields.io/github/v/release/fork-my-spoons/weather.spoon">
  </a>
</p>

A menubar app which shows current weather for a given location:

<p align="center">
  <img src="https://github.com/fork-my-spoons/weather.spoon/raw/main/screenshots/screenshot.png"/>
  <img src="https://github.com/fork-my-spoons/weather.spoon/raw/main/screenshots/screenshot2.png"/>
</p>

When clicked, a menu with more detailed information is shown, it also includes the sunrise and sunset times.

# Installation

This app is using [OpenWeather](https://openweathermap.org) as the data provider, so first you need to create an account and get an app id in order to use the API. Then

- install [Hammerspoon](http://www.hammerspoon.org/) - a powerful automation tool for OS X
   - Manually:

      Download the [latest release](https://github.com/Hammerspoon/hammerspoon/releases/latest), and drag Hammerspoon.app from your Downloads folder to Applications.
   - Homebrew:

      ```brew install hammerspoon --cask```
 - download [weather.spoon](https://github.com/fork-my-spoons/weather.spoon/releases/latest/download/weather.spoon.zip), unzip and double click on a .spoon file. It will be installed under ~/.hammerspoon/Spoons folder.
 - open ~/.hammerspoon/init.lua and add the following snippet:

```lua
-- weather
hs.loadSpoon('weather')
spoon.weather:setup{
  app_id = '<your app id>',
  -- units = 'f',
  lat = 45.501670,
  lon = -73.567221,
--   city = 'Montreal,QC,CA'
}
spoon.weather:start()
```

By defaul the temperature is in celsius, to change it to fahrenheit add parameter units with value 'f'. For the location you can either use latitude and longtitude, or [city name](https://openweathermap.org/current#name).

This app uses icons, to properly display them, install a [feather-font](https://github.com/AT-UI/feather-font) by [downloading](https://github.com/AT-UI/feather-font/raw/master/src/fonts/feather.ttf) this .ttf font and installing it.
