# Use HTTP Methods

This guideline might sound stupid, but too many times you stumble upon REST APIs which for example do delete operation with parameters `/?deleteID=xxx`

Use HTTPS methods such instead:

* `GET` for fetching data.
* `POST` for adding data.
* `PUT` for updating data \(as a whole object\).
* `PATCH` for updating data \(with partial information for the object\).
* `DELETE` for deleting data.

I would like to add that I think `PATCH` is great way to cut down the size of requests to change parts of bigger objects, but also that it fits well with commonly implemented auto-submit/auto-save fields.

