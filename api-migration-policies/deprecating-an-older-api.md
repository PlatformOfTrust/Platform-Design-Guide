---
description: >-
  Best practices for using deprecation headers for endpoints, parameters etc. in
  older API version
---

# Deprecating an older API

## Actions to undertake before stopping older API functionalities

### Migration Announcement Email

Send **Migration Announcement email** to developer customers, emphasizing the _**final date**_ when the older APIs will stop working. We recommend sending the email atmost _**6 months prior**_ to the day older APIs will function for the last time. The following information should be highlighted in the email:

* **Last date** and time of Older API versions functioning: **YYYY-MM-DD hh:mm \(timezone\)**
* List of **APIs versions affected** - URLs
* Reasons for their deprecation
* List of **environments** and **services** affected - URLs
* **Latest API versions**, already up and running, that would replace the older ones and their **documentation** - URLs
* **Benefits** of newest versions
* List of possible **blackout tests**, along with their **dates and times**.

We recommend sending subsequent reminder emails in every two months with the 6-month migration period. Sample Email template can be found here

### Official announcements in Social Media

Make an **official announcement** about the migration process on the _**company website**_ or _**developer portal**_. This could be **company news**, with the contents from the migration email curated to accommodate this. Announcements should also be made from the company page or handler in related **social media sites** like _**Twitter**_, _**LinkedIn**_, _**StackOverflow**_, etc. Specifically, StackOverflow engagement can work better to answers developer queries and assure them about their worries.

**Retweeting** or **reposting** can also be done to remind customers about the deprecation deadline.

### Changes in Documentation

Notify developers of the upcoming Older API deprecation by including a **small announcement text** in the relevant API documentation. The announcement should include the _**last date of API\(s\) functioning**_ and _**links**_ to _**endpoints**_ of the _**latest**_ ****_**versions**_, _**documentation,**_ and \(if possible\) new _**SDKs**_.

A **tagline,** named `deprecated` or `sunset`, depending on the approach you undertake for stopping an older version API to function, can be appended in the API documentation. More about this is discussed in upcoming sections.

At the time close to the deadline, we recommend **removing documentation for the older APIs** so that they are no longer accessible to new customers as well as the existing ones.

### Using analytics to monitor API endpoint usages

If **older API version endpoints** are already being **monitored** by some **usage analytics**, inspect the changes in usage traffic _**after the migration announcements**_ and _**executing blackout test**_s. See if the usage traffic is still high in these endpoints or no. 

If the traffic continues to be high or to increase, we recommend _**approaching the users still working with the older versions**_ and asking them about the reasons they are still using them. They should be made aware of the possible consequences when the older APIs will no longer work. In addition, they should be assisted to migrate to the newest versions with the required assistance.

### Executing API Blackout Tests







## Sunset header or Deprecation header?

Before earlier versions of APIs stop working for good, any response sent back from these APIs should contain either a Sunset Header or a 

