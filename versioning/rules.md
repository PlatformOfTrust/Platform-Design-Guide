# Versioning Rules

### When to do a new version?

We always upgrade our APIs’ version whenever we perform updates resulting in one or more breaking changes \(please see the “Breaking Changes” section\).

In addition, whenever an API is upgraded in any way, we need to keep in mind if the update is a breaking change for any of our other existing products or services, so that we can also update their version accordingly.

### Provide version information in URL of APIs <a id="user-content-provide-version-information-in-url-of-apis"></a>

The Platform of Trust convention is to have the version in the URL of APIs. The main reason for this is to ensure browser explorability of the resources across versions.

Also, we only use major versioning, so we do not use any minor versioning

The general format of the API URL including versioning is:

`[base_url]/[vN]/[resource]/*`

Example:  
 [https://api.oftrust.net/v1/products](https://api.oftrust.net/v1/products)

If there is any major breaking update, the affected APIs will be named as v2.

### How many versions should you maintain?

We need to maintain at least one version back until the retirement period for the old version is reached.

### How do we handle releases with non-breaking updates for the same API version? <a id="user-content-how-do-we-handle-releases-with-non-breaking-updates-for-the-same-api-version%3F"></a>

For managing the deployment of non-breaking transparent updates, we will use the API Revision support in Azure API Management. The key capability here is that only one Revision of an API version is considered current and all revisions actually share the same public URL \(including the version identifier\)

So, whenever a new API release is performed for the same version, we will increment the Revision of the current API version and set this revision as current.

### How do we handle the revert to a previous revision for the same API version? <a id="user-content-how-do-we-handle-the-revert-to-a-previous-revision-for-the-same-api-version%3F"></a>

Rolling back to a previous Revision is a straight-forward action by marking that revision as current again.

Also, we need to consider that it’s possible to use a non-current API Revisions \(both a previous revision or a future revision\), by using a special matrix parameter. For example, if an API is at version v2 and has multiple revisions and the rev=3 is set as the current one, then the next revision \(rev=4\) could be tested using an URL such as:

`[base_url]/Vx/[resource];rev=4/*`

For example:  
 [https://api.oftrust.net/v2/products;rev=4](https://api.oftrust.net/v2/products%3Brev%3D4)

### How many revisions should we maintain? <a id="user-content-how-many-revisions-should-we-maintain%3F"></a>

When we receive an issue from a customer related to the latest revision of an API, before reverting we need to consider that the customer can also use the API call with the revision matrix parameter \(set to the previous revision of the API\) for performing his requests.

In this direction, we need to maintain at least one revision back for ensuring the possibility of any customers having difficulties with the latest revision to use the previous one.

### How do we manage the versioning info? <a id="user-content-how-do-we-manage-the-versioning-info%3F"></a>

The versioning info of our components should be handled through configuration files, so in the case of the APIs managed through Azure API Management we should manage this through the ARM templates \(this would also not require additional tooling\).

For the components that are not managed through Azure APIM we need to use a configuration equivalent to the ARM templates and implement the required tooling to handle versioning in the CI / CD pipeline for these deployments.

### How do we handle versioning at the repository level? <a id="user-content-how-do-we-handle-versioning-at-the-repository-level%3F"></a>

The most straight-forward approach for handling the above versioning strategy at the repository level would be to maintain branches for each of the past major versions, while the latest major version would always be on the main release branch \(usually master\).

In addition to this, for each API Revision that is released we would need to maintain tags in the release branch that are equivalent to the API revisions.

Also, for releasing a specific revision, our tooling should support the option of deploying a specific tag from a branch.

