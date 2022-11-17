{% include [links](../../../_includes/links.md) %}

## Actual weather and current weather data {#factual}

One of the most popular uses of weather data is getting information about the current weather at a specific location.

{% list tabs %}

- GraphQL

    To request information about the **current** weather at a certain point, you need to include the `now` object in the request and list the fields you want to get in the response.

    Meteum can provide data on:

    - temperature – `temperature`;
    - air humidity – `humidity`;
    - atmospheric pressure – `pressure`;
    - precipitation type and intensity – `precType`, `precStrength`;
    - wind speed and direction – `windSpeed`, `windDirection`;
    - cloudiness – `cloudiness`;
    - other weather parameters.

    You can use the special units of measurement:

    - [PressureUnit](https://docs.meteum.ai/en/pages/spectaql#definition-PressureUnit) – the pressure value;
    - [TemperatureUnit](https://docs.meteum.ai/en/pages/spectaql#definition-TemperatureUnit) – the temperature value;
    - [WindSpeedUnit](https://docs.meteum.ai/en/pages/spectaql#definition-WindSpeedUnit) – the wind speed value.

    You can check a detailed list of available fields and their arguments at [Full GraphQL specification](https://docs.meteum.ai/en/pages/spectaql#query-weatherByPoint).

    Example:

    {% include [button](../../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3G0jm2M">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: {lat: 52.37125, lon: 4.89388}) {
        now {
          cloudiness
          humidity
          precType
          precStrength
          pressure
          temperature
          fahrenheit: temperature(unit: FAHRENHEIT)
          windSpeed
          windDirection
        }
      }
    }
    ```

    {% cut "Response" %}

    ```json
    {
      "data": {
        "weatherByPoint": {
          "now": {
            "cloudiness": "OVERCAST",
            "humidity": 85,
            "precType": "NO_TYPE",
            "precStrength": "ZERO",
            "pressure": 759,
            "temperature": 13,
            "fahrenheit": 55,
            "windSpeed": 5,
            "windDirection": "NORTH"
          }
        }
      }
    }
    ```

    {% endcut %}

- REST

    To request information about the **current** weather at a certain point, you need to include the `now` object in the request and list the fields you want to get in the response.

    Meteum can provide data on:

    - temperature – `temp`;
    - air humidity – `humidity`;
    - atmospheric pressure – `pressure_mm` and `pressure_pa`;
    - precipitation type and intensity – `prec_type`, `prec_strength`;
    - wind speed and direction – `wind_speed`, `wind_dir`;
    - cloudiness – `cloudness`;
    - other weather parameters.

    Example:

    ```bash
    curl 'https://api.meteum.ai/v1/fact?lat=52.37125&lon=4.89388' -H 'X-Meteum-API-Key: <Key>'
    ```

    {% cut "Response" %}

    ```json
    {
      "obs_time": 1680465600,
      "uptime": 1680467748,
      "temp": 5,
      "feels_like": 0,
      "temp_water": 9,
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
      "soil_moisture": 0.69,
      "soil_temp": 9,
      "uv_index": 0,
      "wind_gust": 9.4
    }
    ```

    {% endcut %}

{% endlist %}
