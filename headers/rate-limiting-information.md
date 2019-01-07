# Rate limiting information

An often-used technique  is the return of HTTP headers carrying information about the status of current call limits  to allow the user or application to assess where it stands in terms of call limits. These headers typically provide: 

* the maximum number of allowed requests in the current period, 
* the number of remaining requests in the current period and 
* a timestamp that marks when the call limit counter will be reset \(Epoch\). 

This kind of information enables dynamic adjustments of the API usage, which may be used to prevent the API user from being blocked.

## Example header response with rate limiting information

```text
X-RateLimit-Limit: 60
X-RateLimit-Remaining: 25
X-RateLimit-Reset: 1546841865
```

