# Request validation

When handling any request, API must check whether

* User requesting an operation has an account
* the targeted resource exists
* the user is authorized to make the operation in question
* all required parameters provided in request
* request content is valid according to the data model

In case validation fails, operation is stopped and an appropriate error response is sent. In case validation is passed, the request process continues.

Partial updates are not allowed. Consistency between database objects must be maintained:

* in successful case all requested resources are updated
* in failure case none of the requested resources is updated.

