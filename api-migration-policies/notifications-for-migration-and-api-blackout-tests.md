---
description: >-
  Sample emails for announcing API Sunset period and upcoming blackout tests.
  Check and modify necessary dates, URL and other info before sending the email.
---

# Migration Email Template

### Sub: Migration to API V2 - Platform of Trust

Dear valued customer,

Thanks as you continue to use Platform of Trust for generating harmonized data flow.

You are probably aware, that we have released the **2.0 version** of **Platform of Trust Architecture** and as part of it, **version 2 \(V2\)** of our **API family**.

Soon, our **V1 APIs** will be entering into `sunset` stage.

`sunset` period for V1 APIs will start on &lt;**yyyy-mm-dd hh:mm timezone**&gt;.  
Domains for the V1 APIs will cease to exist on &lt;**yyyy-mm-dd hh:mm timezone**&gt;.

After this date, V1 APIs will stop functioning and will become unresponsive.

The `sunset` period will take approximately **6 months**.  
During this period, V1 APIS will contain a `sunset` header as part of their response body:

```text
Deprecation: Sat, 1 Aug 2020 23:59:59 GMT 
Link: <https://api-sandbox.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html", 
<https://docs.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html"
Sunset: Sat, 1 Oct 2020 23:59:59 GMT
```

The date of the Sunset header is the _**end date for the API when it will cease to exist**_. After that date API will respond with HTTP status code `410:Gone`.

The `sunset` period is the last call for you to migrate for a new version of the API.  
To familiarize yourself with the new Architecture and APIs, some actions are required on your part.

New **URLs** for the **V2 APIs** are:

**sandbox**: [https://api-sandbox.oftrust.net/](https://api-sandbox.oftrust.net/)api-name/v2  
**staging**: [https://api-staging.oftrust.net/](https://api-staging.oftrust.net/)api-name/v2  
**production**: [https://api.oftrust.net/](https://api.oftrust.net/) api-name/v2  
**API Documentation**: [https://docs.oftrust.net/api-name/v2](https://docs.oftrust.net/api-name/v2)  
**API Descriptions**: [https://developer.oftrust.net/apis/api-name](https://developer.oftrust.net/apis/api-name)

**Important!** all the new URLs listed above are already up and running, so you can start the migration immediately. As mentioned, ‘[oftrust.net/](http://oftrust.net/)api-name/v1’ will cease functioning on &lt;**yyyy-mm-dd hh:mm timezone**&gt;. So please be sure to finish the migration before that deadline.

#### Planned Blackout Tests

As part of the migration process, Platform of Trust will be performing scheduled **blackout tests** on the **V1 APIs**.

For minimized impact, the following dates are chosen for the blackout tests. V1 APIs will not be accessible from &lt;hh:mm timezone&gt;, &lt;Day&gt; to &lt;hh:mm timezone&gt;, &lt;Day&gt; for &lt;number of&gt; hours.

* &lt;yyyy-mm-dd&gt;
* &lt;yyyy-mm-dd&gt;
* &lt;yyyy-mm-dd&gt;

Please do not hesitate to contact us if you have questions, concerns, or special requirements from us. We encourage all developers to ask Platform of Trust related questions in [StackOverflow](https://stackoverflow.com/questions/ask?guided=false&tags=platform-of-trust), attaching the `platform-of-trust` tag in it.

Best Regards,

![](../.gitbook/assets/platformoftrust-tall-rgb-xs.png)

**Jaro Lexmond**

API Product Owner, API coordination & tech support

jaro.lexmond@oftrust.net

+358 40 900 3598

PLATFORM OF TRUST \| SIGNSPACE

_part of Vastuu Group_

\_\_

{% hint style="info" %}
### **Notes for the development team**

The email template is saved in [Mailgun](https://app.mailgun.com/app/sending/domains/sandbox38ab76a4d79f4c0d99796a4ffd799698.mailgun.org/templates/details/api-sunset-email) under **Sandbox** domain. This domain is used for testing purpose. When it is sent to actual customers, the domain **notifications.oftrust.net** should be seleted from available domain and the template should be added there.
{% endhint %}



