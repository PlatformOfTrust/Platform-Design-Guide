# Breaking changes

## Breaking changes regarding APIs

### Changing the request format <a id="user-content-changing-the-request-format"></a>

This includes the following type of changes:

 • Renaming the endpoint  
 • Removing an existing method \(POST, PUT etc.\)  
 • Renaming a field used in the request \(either mandatory or optional\)  
 • Updating the structure or signature of the request  
 • Making a parameter as required \(which was previously not required\)  
 • Modifying the data type of an existing field  
 • Changing the supported filtering on an existing endpoint  
 • Updating the URL structure of an existing endpoint  
 • The addition of a new feature that will change the purpose of an existing field  
 • The addition of a new validation or updating an existing validation to an existing resource  
 • Modifying the request logic related to pagination

Doing any of these updates will require the consumer to update their API requests in order to adapt to the change\(s\).

### Changing the response format <a id="user-content-changing-the-response-format"></a>

This includes the following type of changes:

 • Updating the structure of the response \(including the pagination info\)  
 • Renaming a field used in the response  
 • Modifying the data type of an existing field  
 • Changing the response code  
 • Changing error types or the structure of the error message

Doing any of these updates will require the consumer to update their API response handling logic in order to adapt to the change\(s\).

### Changing the event format <a id="user-content-changing-the-event-format"></a>

This includes the following type of changes:

 • Renaming the event  
 • Removing an event  
 • Changing the type of the event  
 • Changing the event payload \(this is actually bound to the same rules as changing the response\)

Doing any of the above changes, consumers will have to modify their code in order to cope with the event update\(s\).

### Changing the authentication type or authorization scopes <a id="user-content-changing-the-authentication-type-or-authorization-scopes"></a>

Changing how consumers can authenticate to use our services or updating any of the existing authorization scopes \(by limiting the scope; expanding the scope is not a breaking change\) will require the consumers to change the way they are consuming our services in their own applications.

### Changing rate limiting rules <a id="user-content-changing-rate-limiting-rules"></a>

Changing the rate limiting information in the header or implementing rate limiting for the first time will most likely require consumers react by:   
• Adapting their request patterns to cope with the updated limit   
• Changing their subscription cope with the rate limit update.

### Changing request or response caching strategies <a id="user-content-changing-request-or-response-caching-strategies"></a>

Changing any of the policies or backend logic related to the request or response caching will definitely affect part of the consumers \(especially the ones that expect their data to be current\).

### Changing components that are loose or tightly coupled <a id="user-content-changing-components-that-are-loose-or-tightly-coupled"></a>

In the scenario where we have one or more components that are not completely de-coupled, we may encounter a scenario where changing one of the components \(even if this were a non-breaking change\) would introduce a breaking change to one or more of the coupled components, which of course need to be updated to a new version.

So, in this scenario, all of the involved coupled components would need to be upgraded to a new major version.

### Changing testable class hierarchies <a id="user-content-changing-testable-class-hierarchies"></a>

Changing the inheritance chain or prototype chain of an object is the same as changing its Type. As such, any consumer that inspects the type of an object, either declaratively as a Type annotation or imperatively with something like “instance of”, will need to change their code in order to consume the new class definition.

## Breaking changes regarding ontology

