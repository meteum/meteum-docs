{% include [links](../../../_includes/links.md) %}

## Forecast {#forecast}

The Meteum API can provide weather forecast data both with hourly details and aggregated by parts of the day. A detailed hourly forecast is well suited for drawing a graph of changes in a weather parameter, for detecting important changes, and for analyzing weather data. At the same time, an aggregated forecast for parts of the day is perfect for displaying in the interface or a quick assessment of the overall picture of the day.

{% list tabs %}

- GraphQL

    To get the weather forecast for the selected geographical point, the `forecast` object must be specified in the request:

    ```graphql
    {
      weatherByPoint(request: {lat: 52.37125, lon: 4.89388}) {
        forecast {
          ...
        }
      }
    }
    ```

- REST

    To get forecast, use this endpoint:

    ```
    https://api.meteum.ai/v1/forecast?lat=52.37125&lon=4.89388
    ```

{% endlist %}

### Hourly forecast {#forecast_hours}

{% list tabs %}

- GraphQL

    To get an hourly forecast in a request to the Meteum API inside the `forecast` object, operate with the `hours` object nested in `days` object. You can choose for how many days ahead you would like to have the data with `limit` argument for `days` objects.

    Example:

    {% include [button](../../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3XVlb7d">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: { lat: 52.37175, lon: 4.89358 }) {
        forecast {
          days(limit: 1) {
            hours {
              time
              temperature
              humidity
              pressure
              windSpeed
              windDirection
            }
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
          "forecast": {
            "days": [
              {
                "hours": [
                  {
                    "time": "2022-12-02T00:00:00+01:00",
                    "temperature": 4,
                    "humidity": 93,
                    "pressure": 771,
                    "windSpeed": 1.8,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T01:00:00+01:00",
                    "temperature": 4,
                    "humidity": 93,
                    "pressure": 771,
                    "windSpeed": 2,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T02:00:00+01:00",
                    "temperature": 4,
                    "humidity": 92,
                    "pressure": 770,
                    "windSpeed": 2.7,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T03:00:00+01:00",
                    "temperature": 3,
                    "humidity": 93,
                    "pressure": 770,
                    "windSpeed": 2.9,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T04:00:00+01:00",
                    "temperature": 3,
                    "humidity": 92,
                    "pressure": 770,
                    "windSpeed": 2.9,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T05:00:00+01:00",
                    "temperature": 3,
                    "humidity": 91,
                    "pressure": 770,
                    "windSpeed": 2.5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T06:00:00+01:00",
                    "temperature": 3,
                    "humidity": 92,
                    "pressure": 769,
                    "windSpeed": 2.9,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T07:00:00+01:00",
                    "temperature": 3,
                    "humidity": 90,
                    "pressure": 769,
                    "windSpeed": 3.5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T08:00:00+01:00",
                    "temperature": 2,
                    "humidity": 89,
                    "pressure": 769,
                    "windSpeed": 4.5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T09:00:00+01:00",
                    "temperature": 2,
                    "humidity": 87,
                    "pressure": 769,
                    "windSpeed": 4,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T10:00:00+01:00",
                    "temperature": 3,
                    "humidity": 84,
                    "pressure": 769,
                    "windSpeed": 4.1,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T11:00:00+01:00",
                    "temperature": 3,
                    "humidity": 85,
                    "pressure": 769,
                    "windSpeed": 5.6,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T12:00:00+01:00",
                    "temperature": 3,
                    "humidity": 84,
                    "pressure": 769,
                    "windSpeed": 5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T13:00:00+01:00",
                    "temperature": 3,
                    "humidity": 83,
                    "pressure": 768,
                    "windSpeed": 5.4,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T14:00:00+01:00",
                    "temperature": 2,
                    "humidity": 82,
                    "pressure": 768,
                    "windSpeed": 5.4,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T15:00:00+01:00",
                    "temperature": 2,
                    "humidity": 84,
                    "pressure": 768,
                    "windSpeed": 5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T16:00:00+01:00",
                    "temperature": 2,
                    "humidity": 83,
                    "pressure": 768,
                    "windSpeed": 5.5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T17:00:00+01:00",
                    "temperature": 3,
                    "humidity": 82,
                    "pressure": 769,
                    "windSpeed": 4.5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T18:00:00+01:00",
                    "temperature": 3,
                    "humidity": 84,
                    "pressure": 769,
                    "windSpeed": 5,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T19:00:00+01:00",
                    "temperature": 3,
                    "humidity": 82,
                    "pressure": 769,
                    "windSpeed": 6,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T20:00:00+01:00",
                    "temperature": 3,
                    "humidity": 84,
                    "pressure": 769,
                    "windSpeed": 6,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T21:00:00+01:00",
                    "temperature": 3,
                    "humidity": 84,
                    "pressure": 769,
                    "windSpeed": 6,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T22:00:00+01:00",
                    "temperature": 3,
                    "humidity": 82,
                    "pressure": 769,
                    "windSpeed": 5.6,
                    "windDirection": "NORTH_EAST"
                  },
                  {
                    "time": "2022-12-02T23:00:00+01:00",
                    "temperature": 3,
                    "humidity": 80,
                    "pressure": 769,
                    "windSpeed": 5.5,
                    "windDirection": "NORTH_EAST"
                  }
                ]
              }
            ]
          }
        }
      }
    }
    ```

    {% endcut %}

- REST

    You can use hours objects grouped by days inside forecast response. You can choose for how many days ahead you would like to have the data with `limit` query parameter.

    Example:

    ```bash
    curl 'https://api.meteum.ai/v1/forecast?lat=52.37125&lon=4.89388&limit=1' -H 'X-Meteum-API-Key: <Key>'
    ```

    {% cut "Response" %}

    ```json
    {
      "now": 1680469618,
      "now_dt": "2023-04-02T21:06:58.896650Z",
      "info": {
        "n": true,
        "geoid": 10466,
        "url": "https://meteum.ai/pogoda/10466?lat=52.37125&lon=4.89388",
        "lat": 52.37125,
        "lon": 4.89388,
        "tzinfo": {
          "name": "Europe/Amsterdam",
          "abbr": "CEST",
          "dst": true,
          "offset": 7200
        },
        "def_pressure_mm": 759,
        "def_pressure_pa": 1011,
        "slug": "10466",
        "zoom": 10,
        "nr": true,
        "ns": true,
        "nsr": true,
        "p": false,
        "f": true,
        "_h": false
      },
      "yesterday": {
        "temp": 7
      },
      "fact": {
        "obs_time": 1680465600,
        "uptime": 1680469618,
        "temp": 5,
        "feels_like": 0,
        "icon": "skc_n",
        "condition": "clear",
        "cloudness": 0,
        "prec_type": 0,
        "prec_prob": 0,
        "prec_strength": 0,
        "is_thunder": false,
        "wind_speed": 5,
        "wind_dir": "ne",
        "pressure_mm": 774,
        "pressure_pa": 1031,
        "humidity": 73,
        "daytime": "n",
        "polar": false,
        "season": "spring",
        "source": "station",
        "uv_index": 0,
        "wind_gust": 9.4
      },
      "forecasts": [
        {
          "date": "2023-04-02",
          "date_ts": 1680386400,
          "week": 13,
          "sunrise": "07:13",
          "sunset": "20:14",
          "rise_begin": "06:39",
          "set_end": "20:49",
          "moon_code": 14,
          "moon_text": "growing-moon",
          "parts": {
            "night": {
              "_source": "0,1,2,3,4,5",
              "temp_min": 4,
              "temp_avg": 6,
              "temp_max": 7,
              "wind_speed": 6.8,
              "wind_gust": 12.7,
              "wind_dir": "ne",
              "pressure_mm": 761,
              "pressure_pa": 1014,
              "humidity": 92,
              "prec_period": 360,
              "cloudness": 1,
              "prec_type": 1,
              "prec_strength": 0.25,
              "icon": "ovc_-ra",
              "condition": "overcast-and-light-rain",
              "feels_like": 0,
              "daytime": "n",
              "polar": false
            },
            "night_short": {
              "_source": "0,1,2,3,4,5",
              "temp": 4,
              "wind_speed": 6.8,
              "wind_gust": 12.7,
              "wind_dir": "ne",
              "pressure_mm": 761,
              "pressure_pa": 1014,
              "humidity": 92,
              "prec_period": 360,
              "cloudness": 1,
              "prec_type": 1,
              "prec_strength": 0.25,
              "icon": "ovc_-ra",
              "condition": "overcast-and-light-rain",
              "feels_like": 0,
              "daytime": "n",
              "polar": false
            },
            "evening": {
              "_source": "18,19,20,21",
              "temp_min": 7,
              "temp_avg": 8,
              "temp_max": 9,
              "wind_speed": 6.3,
              "wind_gust": 11.9,
              "wind_dir": "ne",
              "pressure_mm": 771,
              "pressure_pa": 1027,
              "humidity": 74,
              "prec_mm": 0,
              "prec_prob": 0,
              "prec_period": 240,
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "icon": "skc_d",
              "condition": "clear",
              "feels_like": 2,
              "daytime": "d",
              "polar": false,
              "fresh_snow_mm": 0
            },
            "morning": {
              "_source": "6,7,8,9,10,11",
              "temp_min": 3,
              "temp_avg": 4,
              "temp_max": 6,
              "wind_speed": 7.7,
              "wind_gust": 12.9,
              "wind_dir": "ne",
              "pressure_mm": 766,
              "pressure_pa": 1021,
              "humidity": 83,
              "prec_period": 360,
              "cloudness": 0.75,
              "prec_type": 0,
              "prec_strength": 0,
              "icon": "bkn_d",
              "condition": "cloudy",
              "feels_like": -3,
              "daytime": "d",
              "polar": false
            },
            "day": {
              "_source": "12,13,14,15,16,17",
              "temp_min": 6,
              "temp_avg": 8,
              "temp_max": 10,
              "wind_speed": 8.2,
              "wind_gust": 13,
              "wind_dir": "ne",
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 60,
              "prec_period": 360,
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "icon": "skc_d",
              "condition": "clear",
              "feels_like": 0,
              "daytime": "d",
              "polar": false
            },
            "day_short": {
              "_source": "6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21",
              "temp": 10,
              "temp_min": 3,
              "wind_speed": 8.2,
              "wind_gust": 13,
              "wind_dir": "ne",
              "pressure_mm": 769,
              "pressure_pa": 1025,
              "humidity": 72,
              "prec_mm": 0,
              "prec_prob": 0,
              "prec_period": 960,
              "cloudness": 0.25,
              "prec_type": 0,
              "prec_strength": 0,
              "icon": "bkn_d",
              "condition": "partly-cloudy",
              "feels_like": 0,
              "daytime": "d",
              "polar": false,
              "fresh_snow_mm": 0
            }
          },
          "hours": [
            {
              "hour": "0",
              "hour_ts": 1680386400,
              "temp": 6,
              "feels_like": 0,
              "icon": "ovc_-ra",
              "condition": "overcast-and-light-rain",
              "cloudness": 1,
              "prec_type": 1,
              "prec_strength": 0.25,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.8,
              "wind_gust": 12.6,
              "pressure_mm": 758,
              "pressure_pa": 1010,
              "humidity": 93,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "1",
              "hour_ts": 1680390000,
              "temp": 7,
              "feels_like": 0,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.6,
              "wind_gust": 12.6,
              "pressure_mm": 758,
              "pressure_pa": 1010,
              "humidity": 93,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "2",
              "hour_ts": 1680393600,
              "temp": 7,
              "feels_like": 0,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.5,
              "wind_gust": 12.7,
              "pressure_mm": 761,
              "pressure_pa": 1014,
              "humidity": 93,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "3",
              "hour_ts": 1680397200,
              "temp": 5,
              "feels_like": -1,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.7,
              "wind_gust": 12.7,
              "pressure_mm": 761,
              "pressure_pa": 1014,
              "humidity": 91,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "4",
              "hour_ts": 1680400800,
              "temp": 4,
              "feels_like": -2,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.7,
              "wind_gust": 12.7,
              "pressure_mm": 761,
              "pressure_pa": 1014,
              "humidity": 90,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "5",
              "hour_ts": 1680404400,
              "temp": 4,
              "feels_like": -2,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.4,
              "wind_gust": 11.6,
              "pressure_mm": 764,
              "pressure_pa": 1018,
              "humidity": 90,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "6",
              "hour_ts": 1680408000,
              "temp": 4,
              "feels_like": -3,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.6,
              "wind_gust": 11.6,
              "pressure_mm": 764,
              "pressure_pa": 1018,
              "humidity": 89,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "7",
              "hour_ts": 1680411600,
              "temp": 4,
              "feels_like": -3,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.4,
              "wind_gust": 11.6,
              "pressure_mm": 764,
              "pressure_pa": 1018,
              "humidity": 89,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "8",
              "hour_ts": 1680415200,
              "temp": 3,
              "feels_like": -3,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.5,
              "wind_gust": 10.7,
              "pressure_mm": 767,
              "pressure_pa": 1022,
              "humidity": 88,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "9",
              "hour_ts": 1680418800,
              "temp": 3,
              "feels_like": -3,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7,
              "wind_gust": 10.7,
              "pressure_mm": 767,
              "pressure_pa": 1022,
              "humidity": 85,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "10",
              "hour_ts": 1680422400,
              "temp": 5,
              "feels_like": -2,
              "icon": "ovc",
              "condition": "overcast",
              "cloudness": 1,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7.4,
              "wind_gust": 10.7,
              "pressure_mm": 767,
              "pressure_pa": 1022,
              "humidity": 75,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "11",
              "hour_ts": 1680426000,
              "temp": 6,
              "feels_like": -1,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7.7,
              "wind_gust": 12.9,
              "pressure_mm": 769,
              "pressure_pa": 1025,
              "humidity": 70,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "12",
              "hour_ts": 1680429600,
              "temp": 7,
              "feels_like": 0,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 8.1,
              "wind_gust": 12.9,
              "pressure_mm": 769,
              "pressure_pa": 1025,
              "humidity": 65,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "13",
              "hour_ts": 1680433200,
              "temp": 6,
              "feels_like": 1,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 8.2,
              "wind_gust": 12.9,
              "pressure_mm": 769,
              "pressure_pa": 1025,
              "humidity": 62,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "14",
              "hour_ts": 1680436800,
              "temp": 6,
              "feels_like": 2,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7,
              "wind_gust": 13,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 60,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "15",
              "hour_ts": 1680440400,
              "temp": 9,
              "feels_like": 3,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7.4,
              "wind_gust": 13,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 59,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "16",
              "hour_ts": 1680444000,
              "temp": 10,
              "feels_like": 3,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 7.4,
              "wind_gust": 13,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 57,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "17",
              "hour_ts": 1680447600,
              "temp": 10,
              "feels_like": 3,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.2,
              "wind_gust": 11.9,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 56,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "18",
              "hour_ts": 1680451200,
              "temp": 9,
              "feels_like": 3,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 6.3,
              "wind_gust": 11.9,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 62,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "19",
              "hour_ts": 1680454800,
              "temp": 8,
              "feels_like": 3,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 5.8,
              "wind_gust": 11.9,
              "pressure_mm": 770,
              "pressure_pa": 1026,
              "humidity": 70,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "20",
              "hour_ts": 1680458400,
              "temp": 7,
              "feels_like": 2,
              "icon": "skc_d",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 4.9,
              "wind_gust": 9.4,
              "pressure_mm": 772,
              "pressure_pa": 1029,
              "humidity": 81,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "21",
              "hour_ts": 1680462000,
              "temp": 7,
              "feels_like": 1,
              "icon": "skc_n",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 4.9,
              "wind_gust": 9.4,
              "pressure_mm": 772,
              "pressure_pa": 1029,
              "humidity": 82,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "22",
              "hour_ts": 1680465600,
              "temp": 5,
              "feels_like": 1,
              "icon": "skc_n",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 4.9,
              "wind_gust": 9.4,
              "pressure_mm": 772,
              "pressure_pa": 1029,
              "humidity": 83,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            },
            {
              "hour": "23",
              "hour_ts": 1680469200,
              "temp": 5,
              "feels_like": 0,
              "icon": "skc_n",
              "condition": "clear",
              "cloudness": 0,
              "prec_type": 0,
              "prec_strength": 0,
              "is_thunder": false,
              "wind_dir": "ne",
              "wind_speed": 4.5,
              "wind_gust": 7.9,
              "pressure_mm": 774,
              "pressure_pa": 1031,
              "humidity": 81,
              "prec_mm": 0,
              "prec_period": 60,
              "prec_prob": 0
            }
          ],
          "biomet": {
            "index": 1,
            "condition": "magnetic-field_1"
          }
        }
      ]
    }
    ```

    {% endcut %}

  {% endlist %}

### Forecast by parts of the day {#forecast_day_parts}

To get a forecast aggregated by days, specify the `days` object in the `forecast` object (in the optional `limit` parameter, you can specify how many days ahead the forecast is needed).
Inside the `days` object, you can request data related to the entire day. For example, the time of sunrise and sunset, as well as separate data for parts of the day:
- `morning` – aggregated forecast for the morning,
- `day` – aggregated forecast for the day,
- `evening` – aggregated forecast for the evening,
- `night` – aggregated forecast for the night.
Just as before, inside the objects defining the requested part of the day, you need to specify which weather parameters are needed.

Example:

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/41oEo48">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
    forecast {
      days(limit: 2) {
        time
        sunriseTime
        sunsetTime
        parts {
          morning {
            avgTemperature
          }
          day {
            avgTemperature
          }
          evening {
            avgTemperature
          }
          night {
            avgTemperature
          }
        }
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
      "forecast": {
        "days": [
          {
            "time": "2022-09-06T00:00:00+02:00",
            "sunrise": "06:59",
            "sunset": "20:18",
            "parts": {
              "morning": {
                "avgTemperature": 19
              },
              "day": {
                "avgTemperature": 25
              },
              "evening": {
                "avgTemperature": 22
              },
              "night": {
                "avgTemperature": 19
              }
            }
          },
          {
            "time": "2022-09-07T00:00:00+02:00",
            "sunrise": "07:00",
            "sunset": "20:16",
            "parts": {
              "morning": {
                "avgTemperature": 17
              },
              "day": {
                "avgTemperature": 23
              },
              "evening": {
                "avgTemperature": 20
              },
              "night": {
                "avgTemperature": 18
              }
            }
          }
        ]
      }
    }
  }
}
```

{% endcut %}

### Forecast by altitude {#forecast_day_altitude}

To get a forecast for a certain height (for example, at 100 meters), use the `onHeight` fields of the `ForecastHour` objects. The most approximate available height will be selected.

Currently available:
* temperature at 2, 100, 500 meters;
* wind at 10, 100, 200 meters.

Example:

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3Z2hfmD">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
    forecast {
      days(limit: 1) {
        hours {
          temperature
          time
          humidity
          pressure
          windSpeed
          windDirection
          windSpeedOnHeight(height: 100) {
            windSpeed
            height
          }
          temperatureOnHeight(height: 100) {
            temperature
            height
          }
          windDirectionOnHeight(height: 100) {
            windDirection
            height
          }
          windAngleOnHeight(height: 100) {
            windAngle
            height
          }
        }
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
      "forecast": {
        "days": [
          {
            "hours": [
              {
                "temperature": 6,
                "time": "2022-12-06T00:00:00+01:00",
                "humidity": 91,
                "pressure": 767,
                "windSpeed": 3.5,
                "windDirection": "NORTH_EAST",
                "windSpeedOnHeight": {
                  "windSpeed": 6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_EAST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 26,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T01:00:00+01:00",
                "humidity": 90,
                "pressure": 767,
                "windSpeed": 3,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5.8,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_EAST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 27,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T02:00:00+01:00",
                "humidity": 90,
                "pressure": 767,
                "windSpeed": 2.7,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5.3,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 19,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T03:00:00+01:00",
                "humidity": 92,
                "pressure": 767,
                "windSpeed": 2.2,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 9,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T04:00:00+01:00",
                "humidity": 92,
                "pressure": 766,
                "windSpeed": 2,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 4.6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 358,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T05:00:00+01:00",
                "humidity": 92,
                "pressure": 766,
                "windSpeed": 1.8,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 2,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T06:00:00+01:00",
                "humidity": 91,
                "pressure": 766,
                "windSpeed": 2,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5.4,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 5,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T07:00:00+01:00",
                "humidity": 91,
                "pressure": 767,
                "windSpeed": 2.5,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 5.8,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 8,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T08:00:00+01:00",
                "humidity": 87,
                "pressure": 766,
                "windSpeed": 2,
                "windDirection": "NORTH",
                "windSpeedOnHeight": {
                  "windSpeed": 4.8,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 5,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 1,
                  "height": 100
                }
              },
              {
                "temperature": 4,
                "time": "2022-12-06T09:00:00+01:00",
                "humidity": 85,
                "pressure": 766,
                "windSpeed": 2,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 3.9,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 350,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T10:00:00+01:00",
                "humidity": 79,
                "pressure": 766,
                "windSpeed": 1.3,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 3,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 334,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T11:00:00+01:00",
                "humidity": 84,
                "pressure": 766,
                "windSpeed": 2,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 3,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 315,
                  "height": 100
                }
              },
              {
                "temperature": 6,
                "time": "2022-12-06T12:00:00+01:00",
                "humidity": 84,
                "pressure": 765,
                "windSpeed": 1.8,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 3.2,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 297,
                  "height": 100
                }
              },
              {
                "temperature": 7,
                "time": "2022-12-06T13:00:00+01:00",
                "humidity": 77,
                "pressure": 766,
                "windSpeed": 2.2,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 3.5,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 282,
                  "height": 100
                }
              },
              {
                "temperature": 7,
                "time": "2022-12-06T14:00:00+01:00",
                "humidity": 78,
                "pressure": 766,
                "windSpeed": 2.2,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 4.3,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 291,
                  "height": 100
                }
              },
              {
                "temperature": 7,
                "time": "2022-12-06T15:00:00+01:00",
                "humidity": 81,
                "pressure": 765,
                "windSpeed": 3,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 5,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 298,
                  "height": 100
                }
              },
              {
                "temperature": 6,
                "time": "2022-12-06T16:00:00+01:00",
                "humidity": 83,
                "pressure": 765,
                "windSpeed": 3.4,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 303,
                  "height": 100
                }
              },
              {
                "temperature": 6,
                "time": "2022-12-06T17:00:00+01:00",
                "humidity": 84,
                "pressure": 765,
                "windSpeed": 2.9,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 303,
                  "height": 100
                }
              },
              {
                "temperature": 6,
                "time": "2022-12-06T18:00:00+01:00",
                "humidity": 86,
                "pressure": 764,
                "windSpeed": 2.9,
                "windDirection": "WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 304,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T19:00:00+01:00",
                "humidity": 83,
                "pressure": 764,
                "windSpeed": 2.9,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6.1,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 304,
                  "height": 100
                }
              },
              {
                "temperature": 6,
                "time": "2022-12-06T20:00:00+01:00",
                "humidity": 82,
                "pressure": 764,
                "windSpeed": 3.5,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 312,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T21:00:00+01:00",
                "humidity": 86,
                "pressure": 763,
                "windSpeed": 2.4,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6.1,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 320,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T22:00:00+01:00",
                "humidity": 86,
                "pressure": 763,
                "windSpeed": 3.2,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6.4,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 328,
                  "height": 100
                }
              },
              {
                "temperature": 5,
                "time": "2022-12-06T23:00:00+01:00",
                "humidity": 86,
                "pressure": 764,
                "windSpeed": 2.9,
                "windDirection": "NORTH_WEST",
                "windSpeedOnHeight": {
                  "windSpeed": 6.5,
                  "height": 100
                },
                "temperatureOnHeight": {
                  "temperature": 6,
                  "height": 100
                },
                "windDirectionOnHeight": {
                  "windDirection": "NORTH_WEST",
                  "height": 100
                },
                "windAngleOnHeight": {
                  "windAngle": 328,
                  "height": 100
                }
              }
            ]
          }
        ]
      }
    }
  }
}
```

{% endcut %}

### Forecast for multiple points {#forecast_multi_points}

In the Graphql API, it is possible to get a forecast for several points at once. To do this, you need to create a [fragment](https://graphql.org/learn/queries/#fragments) with the `forecast` object in which the necessary data is requested. The created fragment is specified in the `weatherByPoint` method call for each point.

For example, for `London`, `Warsaw` and `Berlin` points, you can get an aggregated daily (`day`) and night (`night`) forecast for 3 days ahead for the following parameters:

* `cloudiness` — cloud collection observed in a certain place,
* `humidity` — water content in the air,
* `avgTemperature` — average temperature,
* `prec` — amount of precipitation (in millimeters),
* `precType` — precipitation type,
* `precStrength` — precipitation intensity,
* `windSpeed` — wind speed,
* `windDirection` — wind direction.

Example:

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3IsjoAZ">Run in playground</a>
</div>

```graphql


{
  London: weatherByPoint(request: { lat: 51.50730, lon: -0.12769 }) {
    ...WeatherData
  }
  Warsaw: weatherByPoint(request: { lat: 52.23209, lon: 21.00714 }) {
    ...WeatherData
  }
  Berlin: weatherByPoint(request: { lat: 52.51865, lon: 13.37471 }) {
    ...WeatherData
  }
}

fragment WeatherData on Weather {
  forecast {
    days(limit: 3) {
      summary {
        day {
          cloudiness
          humidity
          avgTemperature
          prec
          precType
          precStrength
          windSpeed
          windDirection
        }
        night {
          cloudiness
          humidity
          avgTemperature
          prec
          precType
          precStrength
          windSpeed
          windDirection
        }
      }
    }
  }
}
```

{% cut "Response" %}

```json
{
  "data": {
    "London": {
      "forecast": {
        "days": [
          {
            "summary": {
              "day": {
                "cloudiness": "OVERCAST",
                "humidity": 87,
                "avgTemperature": 16,
                "prec": 40.4,
                "precType": "RAIN",
                "precStrength": "VERY_STRONG",
                "windSpeed": 3.4,
                "windDirection": "WEST"
              },
              "night": {
                "cloudiness": "OVERCAST",
                "humidity": 95,
                "avgTemperature": 14,
                "prec": 0.5,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 1.7,
                "windDirection": "SOUTH_WEST"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "SIGNIFICANT",
                "humidity": 80,
                "avgTemperature": 17,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 2.5,
                "windDirection": "NORTH_WEST"
              },
              "night": {
                "cloudiness": "SIGNIFICANT",
                "humidity": 96,
                "avgTemperature": 14,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 1.7,
                "windDirection": "WEST"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "OVERCAST",
                "humidity": 80,
                "avgTemperature": 18,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 2,
                "windDirection": "SOUTH"
              },
              "night": {
                "cloudiness": "CLEAR",
                "humidity": 93,
                "avgTemperature": 13,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 1.2,
                "windDirection": "NORTH_WEST"
              }
            }
          }
        ]
      }
    },
    "Warsaw": {
      "forecast": {
        "days": [
          {
            "summary": {
              "day": {
                "cloudiness": "OVERCAST",
                "humidity": 87,
                "avgTemperature": 14,
                "prec": 0.2,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 3.3,
                "windDirection": "EAST"
              },
              "night": {
                "cloudiness": "OVERCAST",
                "humidity": 81,
                "avgTemperature": 14,
                "prec": 0.4,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 4.5,
                "windDirection": "SOUTH_EAST"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "OVERCAST",
                "humidity": 81,
                "avgTemperature": 15,
                "prec": 0.8,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 2.4,
                "windDirection": "NORTH_EAST"
              },
              "night": {
                "cloudiness": "CLOUDY",
                "humidity": 95,
                "avgTemperature": 12,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 1.8,
                "windDirection": "EAST"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "OVERCAST",
                "humidity": 87,
                "avgTemperature": 13,
                "prec": 1.6,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 3,
                "windDirection": "NORTH_WEST"
              },
              "night": {
                "cloudiness": "OVERCAST",
                "humidity": 92,
                "avgTemperature": 13,
                "prec": 0.7,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 1.6,
                "windDirection": "NORTH_WEST"
              }
            }
          }
        ]
      }
    },
    "Berlin": {
      "forecast": {
        "days": [
          {
            "summary": {
              "day": {
                "cloudiness": "SIGNIFICANT",
                "humidity": 77,
                "avgTemperature": 18,
                "prec": 0.4,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 2.6,
                "windDirection": "EAST"
              },
              "night": {
                "cloudiness": "CLEAR",
                "humidity": 95,
                "avgTemperature": 14,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 2.1,
                "windDirection": "SOUTH"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "SIGNIFICANT",
                "humidity": 79,
                "avgTemperature": 17,
                "prec": 0.2,
                "precType": "RAIN",
                "precStrength": "WEAK",
                "windSpeed": 2,
                "windDirection": "SOUTH_WEST"
              },
              "night": {
                "cloudiness": "CLEAR",
                "humidity": 93,
                "avgTemperature": 14,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 1.7,
                "windDirection": "SOUTH_EAST"
              }
            }
          },
          {
            "summary": {
              "day": {
                "cloudiness": "CLOUDY",
                "humidity": 85,
                "avgTemperature": 17,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 3.3,
                "windDirection": "NORTH_WEST"
              },
              "night": {
                "cloudiness": "CLOUDY",
                "humidity": 93,
                "avgTemperature": 14,
                "prec": 0,
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "windSpeed": 1.3,
                "windDirection": "NORTH_WEST"
              }
            }
          }
        ]
      }
    }
  }
}
```

{% endcut %}
