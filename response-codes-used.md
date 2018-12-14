# Response codes used



## Response codes

When the client sends a request to the server through an API, the client must know from the feedback the outcome of the request, whether it succeeded or failed. The reason of failure must also be specified.

The server must always return the corrent status code.

Platform of Trust APIs use the following HTTP codes in responses.

### 2xx \(Success category\)

The requested action was received and successfully processed by the server.

* **200 OK**
  * successful response for GET, PUT and POST.
* **201 Created**
  * a new resource instance was successfully created with POST method.
* **204 No Content**
  * the request was successfully processed, but no content was returned.
    * DELETE can be a good example of this. The API `DELETE /organizations/:id` will delete the organization `:id` . In response we do not need any data in the returned, as we explicitly asked the system to delete the resource instance.
    * In case there were any error, like if manager `:id`does not exist in the database, then the response code would be not be of 2xx Success Category but around 4xx Client Error category.

### 3xx \(Redirection Category\)

Used rarely.

* **304 Not Modified**
  * indicates that the client has the response already in its cache. And hence there is no need to transfer the same data again.

### 4xx \(Client Error Category\)

These status codes represent that the client has raised a faulty request.

* **400 Bad Request**
  * The request was not processed, as the server could not understand what the client is asking for, e.g. because of missing parameter.
* **401 Unauthorized**
  * The client was not allowed to access resources, and should re-request with the required credentials.
* **403 Forbidden**
  * The request was valid and the client is authenticated, but the client is not allowed access the resource for some reason. 
* **404 Not Found**
  * The requested resource was not available at the time of request.

### 5xx \(Server Error Category\)

Possibly needed in some special case. Should never happen. 

* **500 Internal Server Error**
  * The request was valid, but the server was unable to serve because of some unexpected condition.
* **503 Service Unavailable**
  * The server is down or unavailable to receive and process the request. 

