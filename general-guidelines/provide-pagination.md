# Provide pagination

Pagination is really important because you don’t want a simple request to be incredibly expensive if there are thousands \(or millions\) of rows of results. It seems obvious, but many neglect this functionality.

API accepts a `from` query string parameter and then returns a limited number of results from that offset \(`200` results\). The amount of returned objects can be adjusted with  a `limit` parameter which has a hard-maximum of `1000` .

