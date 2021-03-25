# Deprecating API

We are constantly evolving our APIs and their features. At some point of time when the new version of the API is ready to be published, we will initiate the retirement process for the current version of the API.

Our retirement process can be divided into two stages:

1. Deprecating API meaning its not recommended or preferred version anymore
2. Sunsetting API meaning it will cease to exist after the sunset period expires

This topic is related to the first stage.  
Deprecated APIs will no longer be supported or recommended to use, however API still remains operational and can be used. New version of the API should be adopted.  
We decided not to deprecate APIs partially by parameters or by individual resources, instead, we will be deprecating entire API.

### **Informing Customers** <a id="user-content-**informing-customers**"></a>

We are going to inform customers whenever we are launching a new version of the API and deprecating the current version.

#### Announcement Email <a id="user-content-announcement-email"></a>

Customers will receive deprecation related email announcing the intended deprecation, with the proposed deprecation time, next version release schedule and additional information such as support and contact information, etc.

#### Announcements in Social Media <a id="user-content-announcements-in-social-media"></a>

We will make official announcements related to deprecation and its process on the company's [website](https://platformoftrust.net/en/)  and on Twitter [@PlatformOfTrust](https://twitter.com/platformoftrust?lang=en) .

In addition, we encourage all developers to ask Platform of Trust related questions in [Stack Overflow](https://stackoverflow.com/questions/65178330/how-can-i-get-the-data-from-a-data-product-using-platform-of-trust) . Retirement process is no exception.  
To be able to track new questions easily our developer team managed to pull some strings and have _**platform-of-trust**_ tag created on Stack Overflow.

#### Documentation <a id="user-content-documentation"></a>

We keep our API documentation up to date. You will find additional information about deprecated APIs and their endpoints from here.

#### Technical Communication <a id="user-content-technical-communication"></a>

API responses will include Deprecation header with the date when API is or will be deprecated and the link to the additional information related to that process.

Example:

```text
Deprecation: Sat, 1 Aug 2020 23:59:59 GMT 
Link: <https://api-sandbox.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html", 
<https://docs.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html"
```

#### Sunsetting <a id="user-content-sunsetting"></a>

After the API has been deprecated, at some point of time we will move to stage two, sunsetting deprecated API, meaning it will become unresponsive. Please read more about sunsetting [here](sunsetting-api.md).

