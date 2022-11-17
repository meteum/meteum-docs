{% include [links](../../_includes/links.md) %}

## Quick start {#fast-start}

To make your first request to Meteum API, you need to get an access key.
You can get a [trial key](plans.md#trial) on [the developer portal](https://meteum.ai/b2b/console).

To _authorize_ access, pass the key in the `X-Meteum-API-Key` header of the HTTP request.

{% list tabs %}

- GraphQL

    Next, create a request following the schema [specification](https://docs.meteum.ai/en/pages/spectaql).

    You can start by using this simple example:

    {% include [button](../../_includes/button.md) %}
    <div class="button-container">
        <a target="_blank" href="http://bit.ly/3ZirVgy">Run in playground</a>
    </div>

    ```graphql


    {
      weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
        now {
          temperature
        }
      }
    }
    ```
    This query literally means, "Give me the current weather data for these coordinates, but only the temperature".

    You need to pass this text in the body of a POST request. The HTTP request is executed at `https://api.meteum.ai/graphql/query`. Any HTTP(S) client can be used.

- REST

    To get current weather data, use this endpoint:

    ```
    https://api.meteum.ai/v1/fact?lat=52.37125&lon=4.89388
    ```

    You can use any http client or programming language.

{% endlist %}

### Example in Python {#python}

Here's a minimal working example in Python. To run it, just paste your API access key into the value of the `access_key` variable and execute this code using an interpreter.

{% list tabs %}

- GraphQL

    ```python
    import requests

    # insert your real key here!
    access_key = "your_key"

    headers = {
        "X-Meteum-API-Key": access_key
    }

    query = """{
    weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
        now {
        temperature
        }
    }
    }"""

    response = requests.post('https://api.meteum.ai/graphql/query', headers=headers, json={'query': query})

    print(response.content)
    ```

- REST

    ```python
    import requests

    # insert your real key here!
    access_key = "your_key"

    headers = {
        "X-Meteum-API-Key": access_key
    }

    response = requests.get('https://api.meteum.ai/v1/forecast?lat=52.37125&lon=4.89388', headers=headers)

    print(response.content)
    ```

{% endlist %}

## How to create a request to GraphQL Meteum API {#create-request}

The [GraphQL](https://graphql.org/) query language is used to create requests to Meteum API. **GraphQL** is used to capture a schema describing the data in the API in a way that is understandable to users. This schema unambiguously defines how a query to the API should be generated and what the response format will be. The main advantage of the GraphQL schema (compared to REST API, for example) is the ability to get any subset of data in a single request. Thanks to this, you can write much shorter and clearer code since you don't have to build the logic for merging response data when requesting different data types. Moreover, most weather API providers charge for a particular number of API requests per unit of time. This means that getting all the data you need in one request (instead of multiple requests) is more cost-effective.

A request is simple text that's similar to a JSON object. Each request is enclosed in curly braces
```json
{
  # request parameters
}
```
[Earlier](#fast-start), we saw an example of a request for "current temperature at a location". The main point of this request is to call the `weatherByPoint` method with the `request` parameter, for which a specific value is set
```javascript
{
  lat: 52.37125,
  lon: 4.89388
}
```
By doing so, you're basically telling the system "give me weather info at this location" and specifying which point we want to get data for. Next, you need to specify exactly what data you need. To do this, add the necessary structures to the request:

{% include [button](../../_includes/button.md) %}
<div class="button-container">
    <a target="_blank" href="http://bit.ly/3ZirVgy">Run in playground</a>
</div>

```graphql


{
  weatherByPoint(request: { lat: 52.37125, lon: 4.89388 }) {
    now {          # weather for now
      temperature  # temperature value
    }
  }
}
```

By executing this request, here's what we'll get in the response:
```json
{
  "data": {
    "weatherByPoint": {
      "now": {
        "temperature": 20
      }
    }
  }
}
```

### How to use the playground and learn more about the GraphQL schema {#use-playground}

Meteum API is equipped with an [interactive playground](https://meteum.ai/b2b/api#graphql) interface where you can try to create and execute requests. The playground lets you create requests using autocomplete features and interactive documentation, which describes the GraphQL API schema in detail. Once the request is created, you can immediately execute it and make sure it's correct. You can also generate working code for Python and Node.JS in the playground and execute it via the command line using the `curl` utility.
