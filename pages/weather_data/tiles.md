{% include [links](../../../_includes/links.md) %}

# Tiled weather maps

You can get tiled weather maps in available parameters:

- `humidity` – relative humidity;
- `prec` – the amount of precipitation (in millimeters);
- `pressureMm`– atmospheric pressure for this hour;
- `snowDepth` – depth of snow cover;
- `soilMoisture` – soil moisture;
- `soilTemperature` – average soil temperature;
- `surfaceTemperature`– average surface temperature;
- `temperature` – average temperature;
- `waterTemperature` – average water temperature;
- `windSpeed`– wind speed.

## Timeline

Firstly get information about the available time points for which you can get tiles. In the `time` field an ISO file is used, which includes information about the timezone. The list of such steps is called a "Timeline".

Request example:

{% include [button](../../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3XRUjoF">Run in playground</a>
</div>

```graphql


{
  tiles(request: { lat:  52.37175, lon: 4.89358 }) {
    temperature {
      steps {
        genTime

        time
        timestamp

        bounds {
          lat { min max }
          lon { min max }
        }

        resolution { x y }

        value
      }
    }
  }
}
```

Response:

```json
{
  "data": {
    "tiles": {
      "temperature": {
        "steps": [
          {
            // Time of map generation (gen_time).
            // This value is needed to synchronize map tiles.
            // Is a required parameter in tile requests.
            "genTime": "1673948778",

            // Step time in ISO format.
            "time": "2023-01-15T10:00:00+01:00",

            // Step time (for_date).
            // Is a required parameter in tile requests.
            "timestamp": "1673773200",

            // Bounds for which tiles are available.
            "bounds": {
              "lat": {
                "min": -90,
                "max": 90
              },
              "lon": {
                "min": -180,
                "max": 180
              }
            },

            // Resolution of pixel in degrees.
            "resolution": {
              "x": 0.02,
              "y": 0.02
            },

            // Step value of the parameter at this point.
            "value": 5
          }
        ]
      }
    }
  }
}
```

## Tiles

After the timeline is requested, you can get the tiles:

```
https://api.meteum.ai/raster-maps/temperature/tile?x=%x&y=%y&z=%z&for_date=1673773200&gen_time=1673948778
```

You need to work with such endpoint in the same way as [tile maps](https://en.wikipedia.org/wiki/Tiled_web_map), except required parameters needs to be passed:

* `for_date` – step timestamp;
* `gen_time` – generation timestamp.
