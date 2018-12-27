# Performance

## Minimum response time

You should design REST APIs in a way which does not enable inefficient use of it. In other words enabling full datasource replication with single API call with tens of millions of objects is not allowed. To transfer big datamasses you should seek other options or use pagination. 

As a rule of thumb, 

* Platform of Trust REST APIs should in 99% of calls respond in under 200 ms preferably even faster. 
* GraphQL API should respond in under x00 ms. 

Reasoning for the above limits is that the customer experience of the applications built on top of our platform depend partially on our APIs responsiveness. Our service including APIs must be efficient and reliable. 

## Metrics

Platform metrics and how it is measured

