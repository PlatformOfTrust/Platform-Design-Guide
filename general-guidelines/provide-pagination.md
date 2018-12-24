# Pagination, partial response and sorting

Pagination is really important because you don’t want a simple request to be incredibly expensive if there are thousands \(or millions\) of rows of results. It seems obvious, but many neglect this functionality.

API accepts a `from` query string parameter and then returns a limited number of results from that offset \(`200` results\). The amount of returned objects can be adjusted with  a `limit` parameter which has a hard-maximum of `1000` .

Example: 

```text
/market/apps?from=200&limit=400
```

The above API call returns metainformation about 400 apps in the market place starting from position 200 in the list. 

The response should be linked data and contain self, next, prev and last links. Note that not always you have all of them. A limited example \(**TODO: refine in the future**\): 

```text
{
  "apps": [
    {
      "id": "719aae5f70db4364850f6198ea874aa6",
      "foo": "bar",
      "baz": "quux",
      "size": 9
    },
    ...
    {
      "id": "08ec231f6d9a43dda97d4b950c3393df",
      "foo": "buzz",
      "baz": "honk",
      "size": 6
    }
  ],
  "links": [
      {
          "rel": "self",
          "href": "http://api.oftrust.net/v1/marketplace/apps?limit=30",
      },
      {
          "rel": "first",
          "href": "http://api.oftrust.net/v1/marketplace/apps?limit=30&from=0",
      },
      {
          "rel": "next",
          "href": "http://api.oftrust.net/v1/marketplace/apps?limit=30&from=30",
      }
  ]
}
```

 

Note that the above example does not necessarily be alphabetically sorted or the latest apps. For that purpose we need to have other query parameters. 



