# Authentication and authorization

REST APIs should be stateless. Every request should be self-sufficient and must be fulfilled without knowledge of the prior request. This happens in the case of Authorizing a user action.

Previously, developers stored user information in server-side sessions, which is not a scalable approach. For that reason, every request should contain all the information of a user \(if it’s a secure API\), instead of relying on previous requests.

This doesn’t limit APIs to a user as an authorized person, as it allows service-to-service authorization as well. For user authorization, JWT \(JSON Web Token\) with OAuth2 provides a way to achieve this. Additionally, for service-to-service communication, try to have the encrypted API-key passed in the header. API -keys are discussed separately. 

