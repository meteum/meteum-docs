{% include [links](../../../_includes/links.md) %}

## Climate data {#climate-data}

Using the Meteum API, you can view the average climate data for the last 10 years. The data can be detailed by days, weeks or months.

{% list tabs %}

- GraphQL

    To get climate data for the selected geographical point, it is necessary to specify the `climate` object in the request when calling the GraphQL method `weatherByPoint`:

    ```graphql
    {
      weatherByPoint(request: { lat: 53.718706, lon: 44.453126 }) {
        climate {
          ...
        }
      }
    }
    ```

    Inside the `climate` object, you must specify one of the objects to drill down the request with optional parameters `limit` and `offset`:

    * `days' – by days.
    * `weeks' – by week.
    * `months' – by month.

    The fields to be received in the response are specified inside these objects. By default, data is returned for the entire year from its beginning: the first day, week or month. Using the `limit` and `offset` parameters, you can set the desired period:

    * `limit` defines the number of records to be returned.
    * `offset` determines how many records to skip since the beginning of the year.

    Example of a request for obtaining average climatic data at a point for the period from January 1st to January 10th:

    {% include [button](../../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3KGzdGO">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: { lat: 53.718706, lon: 44.453126 }) {
        climate {
          days(limit: 10) {
            maxDayTemperature
            humidity
            pressure
            maxWindSpeed
            minWindSpeed
            prec
            precType
            precStrength
          }
        }
      }
    }
    ```

    {% cut "Response" %}

    ```json
    {
      "data": {
        "weatherByPoint": {
          "climate": {
            "days": [
              {
                "maxDayTemperature": -5,
                "humidity": 89,
                "pressure": 736,
                "maxWindSpeed": 6,
                "minWindSpeed": 3,
                "prec": 2.2,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -5,
                "humidity": 91,
                "pressure": 735,
                "maxWindSpeed": 6.5,
                "minWindSpeed": 3.7,
                "prec": 2.5,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -6,
                "humidity": 88,
                "pressure": 734,
                "maxWindSpeed": 6.3,
                "minWindSpeed": 3.5,
                "prec": 2,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -8,
                "humidity": 87,
                "pressure": 734,
                "maxWindSpeed": 5.8,
                "minWindSpeed": 3.5,
                "prec": 2.2,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -8,
                "humidity": 88,
                "pressure": 736,
                "maxWindSpeed": 5.5,
                "minWindSpeed": 3.4,
                "prec": 1.8,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -9,
                "humidity": 87,
                "pressure": 739,
                "maxWindSpeed": 5.4,
                "minWindSpeed": 3.5,
                "prec": 1.2,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -10,
                "humidity": 87,
                "pressure": 741,
                "maxWindSpeed": 5.5,
                "minWindSpeed": 3.7,
                "prec": 1.7,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -10,
                "humidity": 87,
                "pressure": 741,
                "maxWindSpeed": 6.5,
                "minWindSpeed": 4,
                "prec": 1.7,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -8,
                "humidity": 88,
                "pressure": 738,
                "maxWindSpeed": 5,
                "minWindSpeed": 3,
                "prec": 1.8,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -10,
                "humidity": 88,
                "pressure": 736,
                "maxWindSpeed": 5,
                "minWindSpeed": 2.9,
                "prec": 0.6,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              }
            ]
          }
        }
      }
    }
    ```

    {% endcut %}

    Example of a request for obtaining average climatic data at a point for the period from January 11th to January 20th:

    {% include [button](../../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3XUZWm7">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: { lat: 53.718706, lon: 44.453126 }) {
        climate {
          days(limit: 10, offset: 10) {
            maxDayTemperature
            humidity
            pressure
            maxWindSpeed
            minWindSpeed
            prec
            precType
            precStrength
          }
        }
      }
    }
    ```

    {% cut "Response" %}

    ```json
    {
      "data": {
        "weatherByPoint": {
          "climate": {
            "days": [
              {
                "maxDayTemperature": -10,
                "humidity": 86,
                "pressure": 736,
                "maxWindSpeed": 5.4,
                "minWindSpeed": 3.4,
                "prec": 1.7,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -7,
                "humidity": 88,
                "pressure": 736,
                "maxWindSpeed": 6.5,
                "minWindSpeed": 3.5,
                "prec": 1,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -5,
                "humidity": 92,
                "pressure": 732,
                "maxWindSpeed": 7.5,
                "minWindSpeed": 4.5,
                "prec": 2.7,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -4,
                "humidity": 93,
                "pressure": 734,
                "maxWindSpeed": 6.5,
                "minWindSpeed": 4.4,
                "prec": 1.6,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -5,
                "humidity": 92,
                "pressure": 737,
                "maxWindSpeed": 5.5,
                "minWindSpeed": 3.2,
                "prec": 1.6,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -6,
                "humidity": 92,
                "pressure": 739,
                "maxWindSpeed": 5,
                "minWindSpeed": 2.5,
                "prec": 2.7,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -7,
                "humidity": 89,
                "pressure": 741,
                "maxWindSpeed": 5.5,
                "minWindSpeed": 2.9,
                "prec": 1.7,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -8,
                "humidity": 91,
                "pressure": 742,
                "maxWindSpeed": 5.4,
                "minWindSpeed": 3,
                "prec": 1.8,
                "precType": "SNOW",
                "precStrength": "AVERAGE"
              },
              {
                "maxDayTemperature": -9,
                "humidity": 89,
                "pressure": 740,
                "maxWindSpeed": 4.5,
                "minWindSpeed": 3,
                "prec": 1,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              },
              {
                "maxDayTemperature": -8,
                "humidity": 88,
                "pressure": 739,
                "maxWindSpeed": 5,
                "minWindSpeed": 3.2,
                "prec": 1.2,
                "precType": "NO_TYPE",
                "precStrength": "ZERO"
              }
            ]
          }
        }
      }
    }
    ```

    {% endcut %}

- REST

    To get climate data for a selected geographical point, you need to select an aggregation interval: days, weeks or months. By default, data is returned for the entire year from its beginning: the first day, week or month.

    Example of a request to get average climate data at a certain point for the whole year, aggregated by day:

    ```bash
    curl 'https://api.meteum.ai/v1/longterm?lat=52.37125&lon=4.89388' -H 'X-Meteum-API-Key: <Key>'
    ```

    {% cut "Response" %}

    ```json
    [
      {
        "time": 1,
        "cl": 79,
        "feels_like": -1,
        "h": 0.83,
        "is_cloudy": false,
        "is_overcast": true,
        "is_prec": true,
        "is_rain": true,
        "is_snow": false,
        "is_sunny": false,
        "max_day_t": 5,
        "min_night_t": 4,
        "p": 762,
        "p_pa": 1015,
        "prec": 4.4,
        "prec_chance": 0.6,
        "wind_dir": "sw",
        "wa": 214,
        "min_ws": 4.3,
        "max_ws": 9.1,
        "condition": "rain",
        "icon": "ovc_ra"
      },
      {
        "time": 2,
        "cl": 59,
        "feels_like": 0,
        "h": 0.77,
        "is_cloudy": false,
        "is_overcast": false,
        "is_prec": false,
        "is_rain": false,
        "is_snow": false,
        "is_sunny": true,
        "max_day_t": 6,
        "min_night_t": 5,
        "p": 763,
        "p_pa": 1017,
        "prec": 1.6,
        "prec_chance": 0.6,
        "wind_dir": "sw",
        "wa": 226,
        "min_ws": 4.8,
        "max_ws": 7.9,
        "condition": "clear",
        "icon": "skc_d"
      },
      {
        "time": 3,
        "cl": 82,
        "feels_like": -1,
        "h": 0.8,
        "is_cloudy": false,
        "is_overcast": true,
        "is_prec": true,
        "is_rain": true,
        "is_snow": false,
        "is_sunny": false,
        "max_day_t": 6,
        "min_night_t": 4,
        "p": 761,
        "p_pa": 1014,
        "prec": 3.4,
        "prec_chance": 0.6,
        "wind_dir": "sw",
        "wa": 211,
        "min_ws": 5.3,
        "max_ws": 9,
        "condition": "rain",
        "icon": "ovc_ra"
      },
      {
        "time": 4,
        "cl": 84,
        "feels_like": -1,
        "h": 0.8,
        "is_cloudy": false,
        "is_overcast": false,
        "is_prec": false,
        "is_rain": false,
        "is_snow": false,
        "is_sunny": true,
        "max_day_t": 6,
        "min_night_t": 5,
        "p": 760,
        "p_pa": 1013,
        "prec": 2.5,
        "prec_chance": 0.4,
        "wind_dir": "sw",
        "wa": 237,
        "min_ws": 5.9,
        "max_ws": 9,
        "condition": "clear",
        "icon": "skc_d"
      },
      {
        "time": 5,
        "cl": 74,
        "feels_like": -2,
        "h": 0.81,
        "is_cloudy": false,
        "is_overcast": true,
        "is_prec": true,
        "is_rain": true,
        "is_snow": false,
        "is_sunny": false,
        "max_day_t": 5,
        "min_night_t": 5,
        "p": 759,
        "p_pa": 1011,
        "prec": 1.7,
        "prec_chance": 0.6,
        "wind_dir": "sw",
        "wa": 219,
        "min_ws": 5.5,
        "max_ws": 8.8,
        "condition": "rain",
        "icon": "ovc_ra"
      }
      // ...
    ]
    ```

    {% endcut %}

    Example of a request to get average climate data at a certain point for the whole year, aggregated by month:

    ```bash
    curl 'https://api.meteum.ai/v1/climate/by-weak?lat=52.37125&lon=4.89388' -H 'X-Meteum-API-Key: <Key>'
    ```

    {% cut "Response" %}

    ```json
    [
      {
        "time": 1,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 5,
        "max_day_t": 6,
        "min_night_t": 3,
        "h": 0.81,
        "p": 761,
        "p_pa": 1014,
        "prec": 78.1,
        "overcast_days": 7,
        "rainy_days": 20,
        "sunny_days": 4,
        "wind_dir": "sw",
        "wa": 214,
        "ws": 6.5
      },
      {
        "time": 2,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 5,
        "max_day_t": 7,
        "min_night_t": 2,
        "h": 0.8,
        "p": 761,
        "p_pa": 1014,
        "prec": 58.2,
        "overcast_days": 8,
        "rainy_days": 15,
        "sunny_days": 5,
        "wind_dir": "sw",
        "wa": 213,
        "ws": 6.1
      },
      {
        "time": 3,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 8,
        "max_day_t": 11,
        "min_night_t": 4,
        "h": 0.75,
        "p": 762,
        "p_pa": 1015,
        "prec": 44.7,
        "overcast_days": 17,
        "rainy_days": 8,
        "sunny_days": 6,
        "wind_dir": "sw",
        "wa": 243,
        "ws": 5.3
      },
      {
        "time": 4,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 12,
        "max_day_t": 15,
        "min_night_t": 7,
        "h": 0.7,
        "p": 762,
        "p_pa": 1015,
        "prec": 30.2,
        "overcast_days": 16,
        "rainy_days": 5,
        "sunny_days": 9,
        "wind_dir": "w",
        "wa": 286,
        "ws": 4.4
      },
      {
        "time": 5,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 15,
        "max_day_t": 17,
        "min_night_t": 8,
        "h": 0.69,
        "p": 762,
        "p_pa": 1015,
        "prec": 48.9,
        "overcast_days": 14,
        "rainy_days": 9,
        "sunny_days": 8,
        "wind_dir": "nw",
        "wa": 312,
        "ws": 4.5
      },
      {
        "time": 6,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 18,
        "max_day_t": 20,
        "min_night_t": 13,
        "h": 0.69,
        "p": 762,
        "p_pa": 1015,
        "prec": 56.7,
        "overcast_days": 12,
        "rainy_days": 10,
        "sunny_days": 8,
        "wind_dir": "w",
        "wa": 284,
        "ws": 4.3
      },
      {
        "time": 7,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 20,
        "max_day_t": 22,
        "min_night_t": 15,
        "h": 0.69,
        "p": 761,
        "p_pa": 1014,
        "prec": 78.6,
        "overcast_days": 6,
        "rainy_days": 16,
        "sunny_days": 9,
        "wind_dir": "w",
        "wa": 254,
        "ws": 4.1
      },
      {
        "time": 8,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 20,
        "max_day_t": 22,
        "min_night_t": 16,
        "h": 0.7,
        "p": 761,
        "p_pa": 1014,
        "prec": 78,
        "overcast_days": 7,
        "rainy_days": 16,
        "sunny_days": 8,
        "wind_dir": "sw",
        "wa": 235,
        "ws": 4.3
      },
      {
        "time": 9,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 17,
        "max_day_t": 19,
        "min_night_t": 13,
        "h": 0.74,
        "p": 762,
        "p_pa": 1015,
        "prec": 70.9,
        "overcast_days": 5,
        "rainy_days": 17,
        "sunny_days": 8,
        "wind_dir": "sw",
        "wa": 225,
        "ws": 4.5
      },
      {
        "time": 10,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 13,
        "max_day_t": 16,
        "min_night_t": 10,
        "h": 0.77,
        "p": 762,
        "p_pa": 1015,
        "prec": 77,
        "overcast_days": 9,
        "rainy_days": 17,
        "sunny_days": 5,
        "wind_dir": "sw",
        "wa": 209,
        "ws": 5.4
      },
      {
        "time": 11,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 9,
        "max_day_t": 12,
        "min_night_t": 4,
        "h": 0.81,
        "p": 759,
        "p_pa": 1011,
        "prec": 80.3,
        "overcast_days": 4,
        "rainy_days": 24,
        "sunny_days": 2,
        "wind_dir": "sw",
        "wa": 212,
        "ws": 6
      },
      {
        "time": 12,
        "lat": 52.37125,
        "lon": 4.89388,
        "avg_day_t": 6,
        "max_day_t": 8,
        "min_night_t": 4,
        "h": 0.81,
        "p": 761,
        "p_pa": 1014,
        "prec": 72.5,
        "overcast_days": 10,
        "rainy_days": 18,
        "sunny_days": 3,
        "wind_dir": "sw",
        "wa": 225,
        "ws": 6.6
      }
    ]
    ```

    {% endcut %}

{% endlist %}
