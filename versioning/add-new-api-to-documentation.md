---
description: Follow these steps when ever you expose new API to the developers.
---

# Add new API to documentation

Steps to follow: 

1. Ensure that RAML is valid. Use validator tools. 
2. Add RAML file \(+ includes\) to [https://github.com/PlatformOfTrust/docs/tree/master/raml2markdown/src](https://github.com/PlatformOfTrust/docs/tree/master/raml2markdown/src) 
   * Create folder for new API and follow filename format: apiname-api
     * For example Broker API is broker-api, Identity API is identity-api. 
3. Add code example files for each endpoint and method to: [https://github.com/PlatformOfTrust/docs/tree/master/raml2markdown/examples](https://github.com/PlatformOfTrust/docs/tree/master/raml2markdown/examples)
   * Filename format: api-name\_METHOD\_endpointpath.md
   * For example Broker API POST method: **broker-api\_POST\_broker\_version\_fetch-data-product.md**
4. Modify array variable `APIs` in [build.py](https://github.com/PlatformOfTrust/docs/blob/master/raml2markdown/build.py) to include the name of the folder you created in step 1. so that it is included in build process.  
5. 


