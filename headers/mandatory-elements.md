# Mandatory elements & behaviour

_Content-Type_ defines the request format.  
_Accept_ defines a list of acceptable response formats.

* An API that accepts JSON encoded POST, PUT & PATCH requests should also require the **Content-Type header** be set to **application/json** or throw a 415 Unsupported Media Type HTTP status code.



