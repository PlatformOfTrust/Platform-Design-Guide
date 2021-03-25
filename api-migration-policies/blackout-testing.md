# Blackout Testing

### What is a blackout test <a id="user-content-what-is-a-blackout-test"></a>

A blackout test is a planned, timeboxed event when we will turn off a certain API or some of the API capabilities.  
The test is meant to help developers understand the impact the retirement will have on the applications and users.

### Executing API Blackout Tests <a id="user-content-executing-api-blackout-tests"></a>

Blackout tests will be scheduled in advance and they should be performed approximately 1-2 months before sunset date of the API.  
Customers will get announcing and reminding emails prior to the date when tests will be executed.  
The email will include the date, time \(inc. timezone\), estimated duration of the blackout test, affected APIs and services, and alternate APIs to use during this period. A sample email template can be found here.

In addition, social media is used for notifications so please follow [@PlatformOfTrust](https://twitter.com/platformoftrust?lang=en)  on Twitter to receive notices about blackout tests.

We will execute at least **3 API blackout tests** where customers will be unable to request older API versions in any environments \(e.g. **Sandbox**, **Production**, etc.\).  
Tests will take place on a different days of the week and at different times of the day.

During the tests, APIs will respond with HTTP status code: **410 Gone**

