{% include [links](../../../_includes/links.md) %}

## GraphQL Examples {#examples-data}

Using Meteum API, you can get various weather data. For your convenience, we collected sample requests for some different cases.

### Current weather data by parameters {#current-weather}

This example shows how to get the current weather data for a given point by parameters:

* temperature in degrees Celsius and Fahrenheit;
* pressure in millimeters of mercury (mm Hg) and pascals (Pa);
* soil temperature;
* soil moisture;
* wind speed;
* wind direction in degrees.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="bit.ly/3IWeX1t">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: -22.814035, lon: -43.244477}) {
    now {
      temperatureInFahrenheit: temperature(unit: FAHRENHEIT)
      temperatureInCelsius: temperature(unit: CELSIUS)
      pressureInMMHG: pressure(unit: MM_HG)
      pressureInPa: pressure(unit: PASCAL)
      soilMoisture
      windSpeed
      windDirection
    }
  }
}
```

### Breakdown for the period {#breakdown}

This example shows how to get hourly breakdown of the weather forecast for a given point for the next 2 days by parameters:

* air quality index (AQI);
* index (dominant component and ozone content);
* probability of precipitation;
* temperature;
* feels-like temperature.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3kXqaHm">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 40.880850, lon: 44.714705}) {
    forecast {
      days(limit: 2) {
        hours {
          time
          pollution {
            aqi
            dominant
            o3
          }
          precProbability
          temperature
          feelsLike
        }
      }
    }
  }
}
```

This example shows how to get daily breakdown of the weather forecast for a given point for the next 5 days by parameters:

* average air temperature;
* maximum air temperature;
* UV Index.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3SZZKkD">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 40.880850, lon: 44.714705}) {
    forecast {
      days(limit: 5) {
        time
        parts {
          day {
            avgTemperature
            maxTemperature
            uvIndex
          }
          night {
            avgTemperature
            minTemperature
            precProbability
            minSoilTemperature
          }
        }
      }
    }
  }
}
```

This example shows how to get following aggregations and parameters for the next 5 days:

* At nights:
  * average air temperature;
  * minimum air temperature;
  * chance of rain;
  * minimum soil temperature.

* In the mornings:
  * minimum air temperature;
  * chance of rain;
  * average temperature.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3SZZKkD">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 40.880850, lon: 44.714705}) {
    forecast {
      days(limit: 5) {
        time
        parts {
          day {
            avgTemperature
            maxTemperature
            uvIndex
          }
          night {
            avgTemperature
            minTemperature
            precProbability
            minSoilTemperature
          }
        }
      }
    }
  }
}
```

This example shows how to get sunrise and sunset time for the next 4 days.


{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3YyCvzb">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 40.880850, lon: 44.714705}) {
    forecast {
      days(limit: 4) {
        time
        sunriseTime
        sunsetTime
        parts {
          morning {
            minTemperature
            precProbability
            avgTemperature
          }
        }
      }
    }
  }
}
```

This example shows how to get the precipitation forecast for a given point at 10-minute intervals for the next 2 hours.


{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3Yv0O1c">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 52.37125, lon: 4.89388}) {
    nowcast {
      region
      steps {
        time
        bounds {
          lat {
            min
            max
          }
          lon {
            min
            max
          }
        }
        precType
        precStrength
      }
    }
  }
}
```

This example shows how to get the weather forecast for a given poin in a monthly breakdown for the next 2 month by parameters:

* average daytime temperature;
* number of cloudy days;
* number of sunny days;
* total amount of precipitation;
* number of days with precipitation.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3mrEjN7">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 53.718706, lon: 44.453126}) {
    climate {
      months(offset: 3, limit: 2) {
        avgDayTemperature
        overcastDays
        sunnyDays
        prec
        precDays
      }
    }
  }
}
```

This example shows how to get the weather forecast for a given point in a weekly breakdown for the next 4 weeks by parameters:

* days of the week with the heaviest precipitation;
* the sunniest days of the week;
* minimum night temperature;
* maximum night temperature.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3YxqdHo">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 53.718706, lon: 44.453126}) {
    climate {
      weeks(offset: 8, limit: 4) {
        strongPrecDays
        sunnyDays
        minNightTemperature
        maxDayTemperature
      }
    }
  }
}
```

This example shows how to get the weather forecast for a given point in a daily breakdown for the next 21 days using by parameters:

* minimum night temperature;
* maximum night temperature;
* probability of precipitation;
* amount of precipitation;
* precipitation type;
* minimum and maximum wind speed;
* average wind direction.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3ZrqGfK">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: {lat: 53.718706, lon: 44.453126}) {
    climate {
      days(offset: 60, limit: 21) {
        minNightTemperature
        maxDayTemperature
        precProbability
        prec
        precType
        minWindSpeed
        maxWindSpeed
        windAngle
      }
    }
  }
}
```

### Weather stations {#stations}

This example shows how to determine the nearest to a given point weather stations coordinates.

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3yCEUi9">Run in playground</a>
</div>

```graphql


{
  stations(maxLat: 53.51865768, minLat: 51.51865768, minLon: 12.37471867, maxLon: 14.37471867, language: EN) {
    id
    name
    time
    distance
    lat
    lon
  }
}
```

### For the period {#period}

This example shows how to get data for the period from 01.01.2022 0:00 (UTC +3) to 01.05.2022 0:00 (UTC +3) from the weather station closest to the given point:

* temperature;
* probability of precipitation;
* precipitation type;
* precipitation strength;
* wind speed;
* wind direction;
* distance from the given point to the weather station;
* thunder location.


{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3SUtwHw">Run in playground</a>
</div>

```graphql


{
  stationsByTimeRange(
    request: {lat: 51.768611, lon: 13.168333}
    timeRange: {from: "1640984400", to: "1641330000"}
  ) {
    id
    time
    temperature
    precProbability
    precType
    precStrength
    windSpeed
    windDirection
    distance
    isThunder
  }
}
```
