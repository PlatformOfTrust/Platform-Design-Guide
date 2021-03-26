---
description: >-
  Sample email template announcing individual blackout test schedules. Check and
  modify necessary dates, URL and other info before sending the email.
---

# API Blackout Test Email Template

### Sub: Important! V1 API Blackout Test on yyyy-mm-dd

Dear valued customer,

Platform of Trust will be performing scheduled blackout tests on the **V1 APIs** on **&lt;yyyy-mm-dd&gt;** at &lt;**hh:mm&gt;** **&lt;timezone&gt;** for upto **&lt;number of hours&gt;**.

During the blackout test period, you might not be able to access the V1 APIs.

It won't be possible to create `identity networks`, `data products`, and `generating harmonized data` during this period.

During the tests, APIs will respond with **HTTP** status code: `410 Gone`

However, you will be able to use all **V2 APIs** in Platform of Trust.  
Please check the [documentation here](https://docs.oftrust.net/api-name/v2).

It should be possible to send requests to all V1 APIs once the blackout test is complete.

The blackout test will start on **&lt;yyyy-mm-dd&gt;** at **hh:mm** **&lt;timezone&gt;** and could last upto **&lt;number of hours&gt;**.

#### Start time

&lt;yyyy-mm-dd&gt;, &lt;hh:mm&gt; &lt;timezone&gt;

#### Estimated duration

&lt;number of hours&gt;

#### APIs, environments and services affected 

The following APIs will not be accessible in `Sandbox`, `Staging`, and `Production` Environments:

Access Control List \(ACL\) API V1  
Application API V1  
Broker API V1  
Context API V1  
Identity API V1  
Login API V1  
Product API V1

`Sandbox` environment: [https://world-sandbox.oftrust.net/](https://world-sandbox.oftrust.net/)   
`Staging` environment: [https://world-staging.oftrust.net/](https://world-staging.oftrust.net/)   
`Production` environment: [https://sandbox.oftrust.net/](https://sandbox.oftrust.net/) 

Ontology Viewer: [standards.oftrust.net/v2](http://standards.oftrust.net/v2)   
[MyWorld Standard](https://valaa.com/potpot/?partition=valaa-aws%3A%2F%2Fl3zyy1pxp9.execute-api.eu-west-1.amazonaws.com%2Fpartitions%3Fid%3D8877f709-b450-4bc0-900e-e121c62c81c9)

Mark the date for the blackout test in your calendar by using the calendar invite in the attachment.

We apologize for any inconvenience caused to you due to this scheduled blackout test.

[View full scheduled blackout test details](https://uptime.com/s/platformoftrust)

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

The email template is saved in [Mailgun](https://app.mailgun.com/app/sending/domains/sandbox38ab76a4d79f4c0d99796a4ffd799698.mailgun.org/templates/details/api_blackout-test) under **Sandbox** domain. This domain is used for testing purpose. When it is sent to actual customers, the domain **notifications.oftrust.net** should be selected from available domain and the template should be added there.

Make sure to add additional possible consequences that might result from the blackout tests.

The calendar invite should be sent along with the email either as attachment or a direct download link.
{% endhint %}

