# Versioning

When APIs are upgraded with a breaking change, it may lead to breaking existing products or services using upgraded APIs.

Examples of breaking changes:

* renaming fields or resource paths or endpoints
* changing field type \(e.g. from string to a list of strings\)
* changing structure of payload \(removing/renaming/retyping fields\)
* altering HTTP verbs
* changing response HTTP codes

In case of breaking changes making a new version of the updated API is mandatory.

There are mixed opinions around about the way the versioning is indicated: whether API version should be included in the URL or in a header.

**The Platform of Trust convention is to have the version in the URL of APIs**. The reason is to ensure browser explorability of the resources across versions.

Example:

`https://api.oftrust.net/v1/marketplace`

If there is any major breaking update, the new set of APIs is named as `v2` .

