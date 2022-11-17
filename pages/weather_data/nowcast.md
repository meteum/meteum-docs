{% include [links](../../../_includes/links.md) %}

## Rain Api {#nowcast}

[*time]: Step time (in this field an ISO file is used, which includes information about the timezone).
[*bounds]: A rectangular area where nowcast data is available (lat – latitude, lon – longitude).


The Meteum API provides nowcasting — a precipitation front forecast that uses machine learning, and is based on weather radar data, satellite images and user reports. Nowcasting is available at 10-minute intervals for the upcoming two hours and an hourly breakdown for the following 22 hours. For example, if 20:00 is the current time, data will be collected:

* from 20:00 to 22:00 – every 10 minutes;
* from 22:00 to 20:00 – hourly.

{% list tabs %}

- GraphQL

    To get nowcasting for a selected geographical point, the `nowcast` object must be specified in the request:

    {% include [button](../../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3m0dKyC">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
        nowcast {
          region

          steps {
            time

            bounds {
              lat { min max }
              lon { min max }
            }

            cloudiness
            condition
            daytime

            precType
            precStrength

            isLongterm
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
          "nowcast": {
            "region": "default",
            "steps": [
              {
                "[time](*time)": "2022-12-09T06:00:00+01:00",
                "[bounds](*bounds)": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T06:10:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T06:20:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T06:30:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T06:40:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T06:50:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:00:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:10:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:20:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:30:00+01:00",
                "bounds": {
                "lat": {"min": 22, "max": 69.36},
                "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:40:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T07:50:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:00:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:10:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:20:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:30:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:40:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T08:50:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
                {
                "time": "2022-12-09T09:00:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T09:10:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T09:20:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T09:30:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T09:40:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T09:50:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T10:00:00+01:00",
                "bounds": {
                  "lat": {"min": 22, "max": 69.36},
                  "lon": {"min": -9.44, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "SLEET",
                "daytime": "DAY",
                "precType": "SLEET",
                "precStrength": "WEAK",
                "isLongterm": false
              },
              {
                "time": "2022-12-09T10:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T11:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T12:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T13:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T14:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T15:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T16:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "DAY",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T17:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T18:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T19:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T20:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T21:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T22:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-09T23:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T00:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T01:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T02:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T03:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T04:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T05:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T06:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              },
              {
                "time": "2022-12-10T07:00:00+01:00",
                "bounds": {
                  "lat": {"min": 0, "max": 90},
                  "lon": {"min": -10, "max": 180}
                },
                "cloudiness": "OVERCAST",
                "condition": "OVERCAST",
                "daytime": "NIGHT",
                "precType": "NO_TYPE",
                "precStrength": "ZERO",
                "isLongterm": true
              }
            ]
          }
        }
      }
    }
    ```

    {% endcut %}

- REST

    To get nowcasting for a selected geographical point, use the following request:

    ```bash
    curl 'https://api.meteum.ai/v1/nowcast/timeline?lat=52.37125&lon=4.89388' -H 'X-Meteum-API-Key: <Key>'
    ```

    {% cut "Response" %}

    ```json
    {
      "now": 1680471153,
      "now_dt": "2023-04-02T23:32:33+02:00",
      "timeline": [
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "21:30",
          "ts": 1680463800
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "21:40",
          "ts": 1680464400
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "21:50",
          "ts": 1680465000
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:00",
          "ts": 1680465600
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:10",
          "ts": 1680466200
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:20",
          "ts": 1680466800
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:30",
          "ts": 1680467400
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:40",
          "ts": 1680468000
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "22:50",
          "ts": 1680468600
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:00",
          "ts": 1680469200
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:10",
          "ts": 1680469800
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:20",
          "ts": 1680470400
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:30",
          "ts": 1680471000
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:40",
          "ts": 1680471600
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "23:50",
          "ts": 1680472200
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:00",
          "ts": 1680472800
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:10",
          "ts": 1680473400
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:20",
          "ts": 1680474000
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:30",
          "ts": 1680474600
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:40",
          "ts": 1680475200
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "00:50",
          "ts": 1680475800
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "01:00",
          "ts": 1680476400
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "01:10",
          "ts": 1680477000
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "01:20",
          "ts": 1680477600
        },
        {
          "cloudness": 0,
          "condition": "clear",
          "icon": "skc_n",
          "is_thunder": false,
          "prec_strength": 0,
          "prec_type": 0,
          "time": "01:30",
          "ts": 1680478200
        }
      ]
    }
    ```

    {% endcut %}

{% endlist %}

Rain API availability depends on your product plan.

You may at times receive an “Empty” response. For example, if the given point lies outside the areas:

America:

* latitude – from -134.52 to -34.24;
* longitude – from 56.48 to 58.08.

Eurasia, Indonesia, Africa:

* latitude – from -12.0 to 69.3;
* longitude – from 58.52 to 180.0.

{% list tabs %}

- GraphQL

    {% cut "Empty response" %}

    ```json
    {
      "errors": [
        {
          "message": "TNowcastTimeline not found",
          "path": [
            "weatherByPoint",
            "nowcast_timeline"
          ]
        }
      ],
      "data": {
        "weatherByPoint": {
          "nowcast": {
            "region": "default",
            "steps": []
          }
        }
      }
    }
    ```

    {% endcut %}

- REST

    ```
    nowcast_timeline is empty
    ```

{% endlist %}

## Tiles

After the timeline is requested, you can get precipitation tiles:

```
https://api.meteum.ai/nowcast/tile?x=%x&y=%y&z=%z&for_date=1673773200&nowcast_gen_time=1673948778
```

Or cloudiness:
```
https://api.meteum.ai/nowcast/cloudiness_tile?x=%x&y=%y&z=%z&for_date=1673773200&nowcast_gen_time=1673948778
```

You need to work with such endpoint in the same way as [tile maps](https://ru.wikipedia.org/wiki/Tiled_web_map), except required parameters needs to be passed:

* `for_date` – step timestamp;
* `nowcast_gen_time` – generation timestamp.
