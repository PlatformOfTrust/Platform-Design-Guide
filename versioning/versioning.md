# Rules

### When to do new version?

When APIs are upgraded with a breaking change, it may lead to breaking existing products or services using upgraded APIs.

### Breaking changes with examples

Examples of breaking changes:

* renaming fields or resource paths or endpoints
* changing field type \(e.g. from string to a list of strings\)
* changing structure of payload \(removing/renaming/retyping fields\)
* altering HTTP verbs
* changing response HTTP codes

In case of breaking changes making a new version of the updated API is mandatory.

There are mixed opinions around about the way the versioning is indicated: whether API version should be included in the URL or in a header.

### Provide version information is URL of APIs

The Platform of Trust convention is to have the version in the URL of APIs. The reason is to ensure browser explorability of the resources across versions.

Example:

`https://api.oftrust.net/v1/marketplace`

If there is any major breaking update, the new set of APIs is named as `v2` . We do not use minor versioning. 



### How many versions should you maintain?

Maintain at least one version back. 

### Retirement process

* You should maintain old version at least for 6 months. 
* When new version is published
  * Notify all API consumers about the new version and begin of retirement period for previous version
  * Provide guides to migrate from old version to new version
  * Publish news in blog post and spread message to Social media
* Blackout testing 1 month before death
  * Notify all API consumers with email about the blackout testing



