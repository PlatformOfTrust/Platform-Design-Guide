# Sunsetting API

As we described before in [previous section](deprecating-api.md), our retirement process can be divided into to stages: deprecating and sunsetting the API. Here we will cover second stage: Sunsetting API.

Sunsetting means API will become unresponsive. At this point of time it does not matter that the API is not recommended version anymore, only thing that matters is that API will become unresponsive. Sunset does not happen immediately but it has a time period. Sunset period is the last call for customers to migrate for a new version of the API

Our sunset period will take approximately 6 months meaning after that period of time API will stop working.

Informing customers about sunsetting our APIs will take same approach as with deprecating.  
Customers will receive sunset announcement email in the beginning of the sunset period. Social media will also include posts about sunsetting our APIs.  
Among with Deprecation header, when the sunset period starts, we will include _**Sunset**_ header into API response:

```text
Deprecation: Sat, 1 Aug 2020 23:59:59 GMT 
Link: <https://api-sandbox.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html", 
<https://docs.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html"
Sunset: Sat, 1 Oct 2020 23:59:59 GMT
```

The date of the _**Sunset**_ header is the end date for the API when it will cease to exist. After that date API will respond with HTTP status code **410:Gone**.

During sunset period we will be executing blackout tests, you can read more about them [here](blackout-testing.md).

