# The only weather widget you will ever need

> **Warning:** This repo contains harmful script. Do not run in SharePoint.

![Safety or death](https://media.giphy.com/media/Np822BSj0v2dG/giphy.gif)

## Minimal path to awesome

Put this in SharePoint:

```html
<script src="https://rawgit.com/waldekmastykarz/weather-widget/master/jquery-2.1.1.min.js"></script>
<script src="https://rawgit.com/waldekmastykarz/weather-widget/master/jquery.simpleWeather.min.js"></script>
<link href="https://rawgit.com/waldekmastykarz/weather-widget/master/styles.css" rel="stylesheet" type="text/css" />
<div class="weather"></div>
<script>
  $(function () {
    // location for which you want to show the weather
    var location = 'Seattle, WA';
    // show temperature in Fahrenheit or Celsius
    var unit = 'f';

    // don't change below this line
    $.simpleWeather({
      location: location,
      woeid: '',
      unit: unit,
      success: function(weather) {
        var html =
          '<h2><i class="icon' + weather.code + '"></i> ' + weather.temp + '&deg;' + weather.units.temp + '</h2>\
           <ul><li>' + weather.city + ' ' + weather.region + '</li></ul>';
        $('.weather').html(html);
      },
      error: function(error) {
        $('.weather').html('<p>' + error.message + '</p>');
      }
    });
  });
</script>
```