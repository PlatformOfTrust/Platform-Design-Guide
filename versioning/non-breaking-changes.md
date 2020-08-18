# Non-breaking changes example

## Non-breaking changes regarding APIs

• Making a required field in the request to be optional, without affecting any of the logic when the field is used   
• Adding an optional request field that does not affect the response logic when the field is not present   
• Correcting an issue with the backend logic that does not result if any of the updates listed in “Breaking changes”   
• Adding a new feature that does not results in any of the updates listed in “Breaking changes”   
• Creating a new endpoint that does not results in any of the updates listed in “Breaking changes”   
• Adding a new resource to an existing endpoint that does not results in any of the updates listed in “Breaking changes”

## Non-breaking changes regarding ontology

### Adding/changing annotation information <a id="user-content-adding%2Fchanging-annotation-information"></a>

Adding annotation properties like labels, descriptions, links between classes e.t.c. This will not affect Context URLs structure and class names and those should not affect or break any logic.

### Adding classes <a id="user-content-adding-classes"></a>

Adding new classes to ontology and defining their properties should not break existing logic because there should be no references to new things in existing code.

### Adding properties <a id="user-content-adding-properties"></a>

Adding new properties to ontology itself is not a breaking change. However linking them to classes might be breaking change if this property is required, since existing data needs to be updated.

