# Purpose and scope

## Scope

This API Design Guide is intended for Platform of Trust: 

* Public and internal REST APIs regarding Marketplace
* Public REST APIs regarding public data access by 3rd party developers
* Public REST APIs regarding Digital Twins \(data models\)

## Aim and reasoning

Since REST is not a standard but architecture style, it leaves a lot of freedoms in implementation. Thus result can be sometimes confusing and hard to learn APIs. API Design Guide is a tool to unify REST APIs in given context. Benefits of API Design Guide can be defined to be: 

* **Unified API family**. Professional look and feel among all APIs. 
* **Lower learning curve**. If all API implementations follow the same guidelines, the resulting API family is cohorent and learning curve for 3rd party API consumer is lower. For API consumer APIs behave similarly and thus feeling of intuition can occur. 
* **No need to reinvent the wheel.** Not all APIs are implemented by one team or even inside same organisation. API Guide line removes the need to reinvent practicalities regarding for example error handling and naming conventions to mention a few. 
* **Faster API Design.** Given that APIs behaviour is the same regardless of API, some specifications in Design can be reused as is. 
* **Testing APIs is faster.** Tests can be more easily modified to fit multiple APIs and thus testing is easier. As a result API development is faster. 



## General guidelines

Our goal is consistency, maintainability, and best practices across applications. APIs aim to balance a truly RESTful API interface with a positive developer experience \(DX\).

In a nutshell:

* **Keep APIs' functionalities as simple as possible.** The endpoints do only one thing, but they do it well. APIs build for "Answer to Life, the Universe and Everything" are just cumbersome, hard to use, too complex to maintain and error prone. 
* **Avoid overlapping functionalities** between different APIs.
* **In error case include in the API response verbose description**.
  * include also a description about erroneous parameter value, if it is feasible.
* **API must have support for the OPTIONS endpoint** to enable cross-origin API calls \(CORS\). 
* **Use standards** - don't reinvent the wheel \(that only causes more work in implementation and in consumer side too\). 
* **Keep verbs out of your base URLs.**
* **Use HTTP verbs** to operate on the collections and elements.

