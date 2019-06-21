# Breaking changes

**Changing an invocation signature.**

If you add optional parameters to an invocation target, that can be safe. But, if you add required parameters; or, if you add optional parameters that change the default behavior of the invocation; that is a breaking change. Doing so will require the consumer to update their invocation arguments in order to adapt to the change.

**Changing a response structure.**

When we talk about data structures, we often talk in terms of "additive" changes vs. "breaking" changes. The idea being that if you only add new properties to an existing structure, the consumer can safely ignore them at first; then, incrementally update the code to consume the new properties as needed.

But, is this always true? What if the consumer needs to serialize the data and store it in a database column that has a constrained character size? In such a case, even an "additive" change could cause an unexpected database truncation error.

Or, imagine that the response was being logged to a file. An increase in the response payload size could change the velocity with which log files take up disk-space. This, in turn, could cause issues if the log files aren't being rotated quickly enough.

**Changing a response code.**

Changing a response code is like changing a response data structure. If the consumer's logic examines the response code, the consumer may have to change their logic in order to cope with the change in response code.

But, what if you do something less obvious like implement ETag support. In such a case, an API that always responded with a 200 OK could suddenly start responding with a 304 Not Modified response. Such a change could cause runtime errors for a consumer that never had to deal with a functioning ETag workflow before.

**Changing error types, messages, and other details.**

When it comes to error handling, consumers implement all kinds of crazy-ass logic in order to understand the errors that are coming back from a system or module. This could mean looking at error Types and Messages. It could also mean performing string-parsing on the extended data provided in an error. As such, any change to the content of an error object could, theoretically, break the error handling logic in the consuming context.

**Changing event types.**

An event type is akin to a method signature or a RESTful resource location. As such, if you change an event type, consumers will have to change their code in order to listen for the new events.

**Changing event payloads.**

An event payload is akin to a response structure. As such, changing an event payload incurs the same problems as changing a response structure. In so much as an "additive" change will likely be OK in the vast majority of cases. But, that even an "additive" change can cause unexpected errors depending on how the consumer is processing the event.

**Changing testable class hierarchies.**

Changing the inheritance chain or prototype chain of an object is the same as changing its Type. As such, any consumer that inspects the type of an object, either declaratively as a Type annotation or imperatively with something like instanceof, will need to change their code in order to consume the new class definition.

**Changing rate limiting rules.**

Changing the rate limiting strategies for a service - or implementing rate limiting for the first time - may require a consumer to refactor their invocation patterns so as not to hit a rate-limit ceiling. Or, they may have to come up with totally new strategies if a rate-limit ceiling is too low. Or, they may have to upgrade to a more substantial API subscription with higher rate limits.

**Changing caching strategies.**

If a change in caching strategies is completely transparent, then it's not a breaking change. But, the moment there's a possibility that stale data can be presented to a client, that's a breaking change \(assuming that the consumer is not expecting the possibility of and / or the magnitude of such staleness\). So, for example, updating an API response to read from a database replica instead of the database master is a definitely a breaking change.

**Changing the connaissance of time.**

A consumer doesn't just consume end-points or methods, it consumes a "system". As such, if a system as a whole changes the way workflows are orchestrated internally, this could be considered a breaking change. Imagine a scenario in which a DELETE request triggers a "deleted" event that gets pushed to a publish-and-subscribe mechanism. If "deleted" events went from being published instantly to being published at night in a "batch job", the only thing that changed would be the "connaissance of time". But, if a consumer expected those events to be published in a more immediate fashion, the consuming code may have to change in order to cope with the new timing.

Ok, that's maybe a bad example. But, just think of the way in which we depend on the relative timing of related actions in a system. Imagine that your database replica lag suddenly went from sub-second times to several hours. It is very likely that you would have to change your application code to deal with such a change in timing.

**Changing content-distribution \(CDN\) strategies.**

There are many benefits to moving an API behind a Content-Delivery Network \(CDN\). Automatic compression; image optimization; DDOS protection; to name a few. But, a CDN adds "API" semantics in the sense that it injects its own HTTP headers into both the request and the response data. A consumer may come to depend on those injected HTTP headers. For example, the Cloudflare CDN injects a "country" header that can be used to help implement geofencing internally to an application. If the application context were to be moved to another CDN that no longer injected the same HTTP headers, both internal and external consumers may have to change in order to make up for the missing data.



