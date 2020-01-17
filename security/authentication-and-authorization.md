# Authentication and authorization

REST APIs should be stateless. Every request should be self-sufficient and must be fulfilled without knowledge of the prior request. This happens in the case of Authorizing a user action.

Previously, developers stored user information in server-side sessions, which is not a scalable approach. For that reason, every request should contain all the information of a user \(if it’s a secure API\), instead of relying on previous requests.

This doesn’t limit APIs to a user as an authorized person, as it allows service-to-service authorization as well. For user authorization, JWT \(JSON Web Token\) with OAuth2 provides a way to achieve this. Additionally, for service-to-service communication, try to have the encrypted API-key passed in the header.

### Basic rule for error handling

**A 401 Unauthorized** response should be used for missing or bad authentication, and a **403 Forbidden** response should be used afterwards, when the user is authenticated but isn’t authorized to perform the requested operation on the given resource.

#### Use Access and Refresh Tokens <a id="9549"></a>

Modern stateless, RESTful APIs implement authentication with tokens. This eliminates the need to handle sessions and cookies on a now stateless server, and makes it really easy to debug network requests by simply utilising the `Authorization` header \(or even an `access_token` query param\).

**Access Tokens**

The access token is used for authenticating all future API requests, has a short life span and can’t be revoked.

**Refresh Tokens**

The refresh token is returned in the initial login response, but it is hashed and stored in the database with an expiry timestamp and relationship to the user. This acts as a long-life, password-like secret token, which can be used to request a new short-life JWT access tokens. Refresh tokens also extend their life every time they are used for renewal, meaning that a user doesn’t need to log in again if they continually use the service.

**TODO:** Describe with code example how authentication and authorization is implemented in PoT context

## OAuth2 background and options

OAuth 2.0 specification defines 4 types of authorization flows:

* **Authorization Code**
* **Resource Owner Password Credentials**
* **Implicit**
* **Client Credentials**

**Implicit** and **Client Credentials** are flows typically reserved for special types of clients. More specifically,

* **Implicit:** Single-page Javascript Web Applications \(for example, Google Fonts\)
* **Client Credentials:** Non-interactive programs for machine-to-machine communications \(for example, background services and daemons\)

As for other clients, depending on their trustworthiness, they can use the following flows:

* **Authorization Code or Resource Owner Password Credentials:** Highly trusted apps \(first-party apps\)
* **Authorization Code:** Less trusted apps \(third-party apps requesting access to PoT platform\)

### Use authorization code flow

Loosely speaking, PoT is a platform where third-party applications and services can access its resources, thus we use authorization code flow. 

### OAuth2 authorization code flow example

#### Step 1: Authorization Code Link

{% api-method method="get" host="" path="" %}
{% api-method-summary %}
/auth/v2/
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Step 2: User Authorizes Application

{% api-method method="get" host="" path="" %}
{% api-method-summary %}
Authorize
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

