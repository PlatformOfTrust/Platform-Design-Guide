# Error handling

Because we are using HTTP methods, we should use HTTP status codes. Although a challenge here is to select a distinct slice of these codes, and then depend on response data to detail any response errors. Keeping a small set of codes helps you consume and handle errors consistently.

**for Data Errors**

* `400` for when the requested information is incomplete or malformed.
* `422` for when the requested information is okay, but invalid.
* `404` for when everything is okay, but the resource doesn’t exist.
* `409` for when a conflict of data exists, even with valid information.

**for Auth Errors**

* `401` for when an access token isn’t provided, or is invalid.
* `403` for when an access token is valid, but requires more privileges.

**for Standard Statuses**

* `200` for when everything is okay.
* `204` for when everything is okay, but there’s no content to return.
* `500` for when the server throws an error, completely unexpected.

Furthermore, returning responses after these errors is also very important. In the case of trying to create a new account, imagine we provide an `email` and `password` . Of course we would like to have our client app prevent any requests with an invalid email, or password that is too short, but outsiders have as much access to the API as we do from our client app when it’s live.

* If the `email` field is missing, return a `400` .
* If the `password` field is too short, return a `422` .
* If the `email` field isn’t a valid email, return a `422` .
* If the `email` is already taken, return a `409` .

Now from these cases, two errors returned `422s` regardless of their reasons being different. This is why we need an error code, and maybe even an error description. It’s important to make a distinction between code and description as I intend to have `error` \(code\) as a machine consumable constant, and `description` as a human consumable string that may change.

In the case of per-field errors, the presence of the field as a key in the error is enough of a “code” to indicate that it is a target of a validation error.

**Highly recommend you add a link in your description to more information.**

### Field Validation Errors

For returning those per field errors, it may be returned as:

```text
POST /v1/register

// request
{
  "email": "end@@user.comx"
  "password": "abc"
}

// response - 422
{
  "error": {
    "status": 422,
    "error": "FIELDS_VALIDATION_ERROR",
    "description": "One or more fields raised validation errors."
    "fields": {
      "email": "Invalid email address.",
      "password": "Password too short."
    }
  }
}
```

**Operational Validation Errors**

And for returning operational validation errors:

```text
POST /v1/register

// request
{
  "email": "end@user.com",
  "password": "password"
}

// response - 409
{
  "error": {
    "status": 409,
    "error": "EMAIL_ALREADY_EXISTS",
    "description": "An account already exists with this email."
  }
}
```

## Read more

* [https://nordicapis.com/best-practices-api-error-handling/](https://nordicapis.com/best-practices-api-error-handling/)

