---
description: >-
  Sample email template notifying customers about API deprecation period. Check
  and modify necessary dates, URLs and other info before sending the email.
---

# API Deprecation Email

### Sub: Platform of Trust - V1 API Deprecation Notice

Dear valued customer,

Thanks as you continue to use Platform of Trust for generating harmonized data flow.

You are probably aware, that we have released the **2.0 version** of **Platform of Trust Architecture** and as part of it, **version 2 \(V2\)** of our **API family**.

As from the date **&lt;yyyy-mm-dd hh:mm timezone&gt;**, our V1 APIs will be entering into their `deprecated` lifecycle stage. It means, the APIs still remain operational and can be used, but **WE WILL NO LONGER SUPPORT or RECOMMEND THEM TO USE**.

All APIs entering into the `deprecated` stage will contain `deprecation-header` as part of their response body:

```text
Deprecation: Sat, 1 Aug 2020 23:59:59 GMT 
Link: <https://api-sandbox.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html", 
<https://docs.oftrust.net/api-name/v2>; rel="deprecation"; type="text/html"
```

We keep our **API documentation** up to date. You will find additional information about deprecated APIs and their endpoints from [here](https://dev.azure.com/Platform-of-Trust/Platform-of-Trust/_wiki/wikis/Platform-of-Trust.wiki/393/API-Deprecation-Email).

As V2 APIs are up and fully functional, we suggest that _**start adopting the newer version of the APIs**_ in order to get the desired experience from Platform of Trust capabilities.

#### New URLs for the V2 APIs are:

**sandbox**: [https://api-sandbox.oftrust.net/](https://api-sandbox.oftrust.net/)api-name/v2  
**staging**: [https://api-staging.oftrust.net/](https://api-staging.oftrust.net/)api-name/v2  
**production**: [https://api.oftrust.net/](https://api.oftrust.net/)api-name/v2  
**API Documentation**: https://docs.oftrust.net/api-name/v2  
**API Descriptions**: https://developer.oftrust.nets/apis/api-name

After the V1 APIs have been deprecated for a while, we will move forward **sunsetting the deprecated API**, meaning it will become _**completely unresponsive**_. We'll notify you about the `sunsetting` period and actions you need to take from your side in a separate email.

Please do not hesitate to contact us if you have questions, concerns, or special requirements from us. We encourage all developers to ask Platform of Trust related questions in [StackOverflow](https://stackoverflow.com/questions/ask?guided=false&tags=platform-of-trust), attaching the `platform-of-trust` tag in it.

Thank you for your efforts and hard works.

Best Regards,

![](../.gitbook/assets/platformoftrust-tall-rgb-xs.png)

**Jaro Lexmond**

API Product Owner, API coordination & tech support

jaro.lexmond@oftrust.net

+358 40 900 3598

PLATFORM OF TRUST \| SIGNSPACE

_part of Vastuu Group_

{% hint style="info" %}
### **Notes for the development team**

The email template is saved in [Mailgun](https://app.mailgun.com/app/sending/domains/sandbox38ab76a4d79f4c0d99796a4ffd799698.mailgun.org/templates/details/api-deprecation-notice) under **Sandbox** domain. This domain is used for testing purpose. When it is sent to actual customers, the domain **notifications.oftrust.net** should be selected from available domain and the template should be added there.
{% endhint %}

