Admission to Hospital API
=======

This application shows how to expose a service using API Gateway, and how to create different versions of an API

* API exposition patterns: Gateway 

  * Mule acts as a proxy to backend service (admission-main-service).

* API Versioning: 
  Changes that can affect API behaviour should go to a new version of the API. For example

  * Policies: adding, or changing policies
  * Existing resources and schemas: modifying schemas (for request or response), changing method behaviours, etc.

Since an api can be used by several consumers, you cannot change the API. You have to create a new version of that api.

This example exposes two apis: api/1.0.0 and api/2.1.0 to show a way to create different versions of an API.


Configuration properties
=========================

```
#host and port to publish APIs
http.port=8081
http.host=localhost
```

```
#location of the admission main service
admission.service.port=80
admission.service.host=<url of the main service>
admission.service.path=AdmissionService/v1.0.0/
```

```
#urls for the public APIs that are tracked by ASR
http.path.v.1.0.0=api/1.0.0/
http.path.v.2.1.0=api/2.1.0/
```

```
#urls for the same APIs that are NOT tracked by ASR
http.path.v.1.0.0-private=private/1.0.0/
http.path.v.2.1.0-private=private/2.1.0/
```

```
#to enable ASR
anypoint.agent.token=<token provided by Anypoint Service Registry>
```


ADDITIONAL RESOURCES
====================
See https://github.com/matiasjuan/admission-main-service for the backend service


