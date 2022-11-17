{% include [links](../../../_includes/links.md) %}

## GraphQL API parameters {#parameters}

Using the Meteum API, you can view different parameters of weather data. The available list of parameters depends on your tariff plan.

### datum {#datum}

Datum is a base elevation used as a reference from which to reckon heights or depths of a tide. A tidal datum is a standard elevation defined by a certain phase of the tide. Tidal datums are used as references to measure local water levels and should not be extended into areas having differing oceanographic characteristics without substantiating measurements. In order that they may be recovered when needed, such datums are referenced to fixed points known as bench marks. Tidal datums are also the basis for establishing privately owned land, state owned land, territorial sea, exclusive economic zone, and high seas boundaries.

Tariff plan: all.

### daytime {#daytime}

Represents the time of day.

Tariff plan: all.

### cloudiness {#cloudiness}

Represents the state of cloudiness.

Tariff plan: all.

### condition {#condition}

Represents the general weather conditions.

Tariff plan: all.

### feelslike {#feelslike}

The same temperature can be perceived differently depending on humidity, wind strength and other factors. For example, with a strong wind of -5 °, cold is felt, and with high temperature and humidity, heat and heat are felt. Therefore, the forecast displays "feels-like" temperature. It indicates how comfortable the weather conditions are.

{% note info %}

"Feels-like" temperature is calculated as an average for most people. Each person's sense of warmth is individual, so it may differ from the response.

{% endnote %}

Tariff plan: Trial, Plus, Enterprise.

### humidity {#humidity}

Represents the relative humidity.

Tariff plan: all.

### icon {#icon}

Tariff plan: all.

### isThunder {#isThunder}

Represents the presence of a thunder for the current hour.

Tariff plan: Trial, Plus, Enterprise.

### kpIndex {#kpIndex}

Represents the geomagnetic activity and classifies geomagnetic storms.

Tariff plan: Trial, Plus, Enterprise.

### moon {#moon}

Represents the moon phase.

Tariff plan: Trial, Plus, Enterprise.

### oceanTideExtremums {#oceanTideExtremums}

Represents the ocean water level maximums and minimums in day.

Tariff plan: all.

### parts {#parts}

Represents the dayparts aggregations for this day.

Tariff plan: all.

### phenomCondition {#phenomCondition}

Represents the current phenomenon. Skipped when weather conditions are normal.

Tariff plan: all.

### phenomIcon {#phenomIcon}

Represents the icon of the phenomenon. Skipped when weather conditions are normal.

Tariff plan: Trial, Enterprise.

### polar {#polar}

Indicates the polar day or polar night. Skipped when the day is normal.

Tariff plan: all.

### Pollution {#pollution}

Represents the current composition of the atmosphere.

Tariff plan: Trial, Basic (AQI), Plus (AQI + components), Enterprise (AQI + DOM).

### precProbability {#precProbability}

Represents the current probability of precipitation. Possible values are in [0, 1].

Tariff plan: all.

### precStrength {#precStrength}

Represents the current value of precipitation strength.

Tariff plan: all.

### precType {#precType}

Represents the current type of precipitation.

Tariff plan: all.

### pressure {#pressure}

Represents the current atmospheric pressure.

Tariff plan: all.

### season {#season}

Represents the current time of the year.

Tariff plan: all.

### soilMoisture {#soilMoisture}

Represents the percentage of all soil moisture to dry soil.

Tariff plan: Trial, Plus, Enterprise.

### soilTemperature {#soilTemperature}

Represents the soil temperature at a depth of 7 cm.

Tariff plan: Trial, Plus, Enterprise.

### summary {#summary}

Summary aggregations for this day.

Tariff plan: Trial, Plus, Enterprise.

### sunriseBegin {#sunriseBegin}

Represents the start time of the sunrise in ISO format.

Tariff plan: Trial, Plus, Enterprise.

### sunriseBeginTime {#sunriseBeginTime}

Represents the start time of the sunrise in Unix Timestamp format.

Tariff plan: Trial, Plus, Enterprise.

### sunriseTime {#sunriseTime}

Represents the sunrise time in ISO format.

Tariff plan: Trial, Plus, Enterprise.

### sunriseTimestamp {#sunriseTimestamp}

Represents the sunrise time in Unix Timestamp format.

Tariff plan: Trial, Plus, Enterprise.

### sunsetEndTime {#sunsetEndTime}

Represents the end time of the sunset time in ISO format.

Tariff plan: Trial, Plus, Enterprise.

### sunsetEndTimestamp {#sunsetEndTimestamp}

Represents the end time of the sunset time in Unix Timestamp format.

Tariff plan: Trial, Plus, Enterprise.

### sunsetTime {#sunsetTime}

Represents the sunset time in ISO format.

Tariff plan: Trial, Plus, Enterprise.

### sunsetTimestamp {#sunsetTimestamp}

Represents the sunset time in Unix Timestamp format.

Tariff plan: Trial, Plus, Enterprise.

### temperatureOnHeight {#temperatureOnHeight}

Represents the temperature at the provided height.

Tariff plan: Trial, Enterprise.

### time {#time}

Represents the start time of the day in ISO format.

Tariff plan: all.

### timestamp {#timestamp}

Represents the start time of the day in Unix Timestamp format.

Tariff plan: all.

### uvIndex {#uvIndex}

Represents the level of solar radiation on the Earth's surface. Possible values are in [0, 13].

Tariff plan: Trial, Plus, Enterprise.

### waterTemperature {#waterTemperature}

Represents the water surface temperature. Exists only for cities that are located near large bodies of water.

Tariff plan: Trial, Plus, Enterprise.

### waveAngle {#waveAngle}

Represents the angle in which the primary wave is moving. Measured in degrees.

Tariff plan: Trial, Plus, Enterprise.

### waveDirection {#waveDirection}

Represents the direction in which the primary wave is moving.

Tariff plan: Trial, Plus, Enterprise.

### waveHeight {#waveHeight}

Represents the significant height of combined wind waves and swell surface. Measured in meters.

Tariff plan: Trial, Plus, Enterprise.

### wavePeriod {#wavePeriod}

Represents the primary wave mean period surface. Measured in seconds.

Tariff plan: Trial, Plus, Enterprise.

### WeatherByPoints {#WeatherByPoints}

Generic object containing all available types of weather data.

Field name | Description | Tariff plan
:--- | :---: | ---:
Climate | Average weather statistics for 10 years. | all
Days | Statistics grouped by day. | Basic, Plus
Weeks | Statistics grouped by week. | Basic
Months | Statistics grouped by month. | all
Zones | Climate zone description. | Basic, Plus
Forecast | The main weather forecast. | all
Hours | Forecast hours list for this day. Be careful, the size of this list may be less than 24 due to the decreasing frequency of forecasts for distant days. | Trial (48 hours), Basic (12 hours), Plus (24 hours), Enterprise (48 hours)
Days | Statistics grouped by day. | Trial (14 days), Basic (7 days), Plus (10 days), Enterprise (14 days)
Now | Weather now. It can be compiled from many sources based on different business logic. | Trial (every hour), Basic (3 times a day), Plus (6 times a day), Enterprise (every hour)
Pollution | The current composition of the atmosphere. | Trial (AQI + DOM), Basic (AQI), Plus (AQI + components), Enterprise (AQI + DOM)
Location | All information about requested location or point. | all
Observations (StationsByTimeRange) | Archive of stations for a certain period of time. | Trial, Enterprise

### windAngleOnHeight {#windAngleOnHeight}

Represents the wind angle at the provided height.

Tariff plan: Trial, Enterprise.

### windDirection {#windDirection}

Represents the current wind direction.

Tariff plan: all.

### windDirectionOnHeight {#windDirectionOnHeight}

Represents the direction of the wind in terms of the cardinal directions.

Tariff plan: Trial, Enterprise.

### windGust {#windGust}

Represents the speed of wind gusts.

Tariff plan: all.

### windSpeed {#windSpeed}

Represents the wind speed at a height of 10 meters from the ground surface.

Tariff plan: all.

### windSpeedOnHeight {#windSpeedOnHeight}

Represents the units of measurement of the wind speed value.

Tariff plan: Trial, Enterprise.

### kpIndex {#kpIndex}

Represents the wind speed at a height of 10 meters from the ground surface.

Tariff plan: Trial, Plus, Enterprise.
