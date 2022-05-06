### 21. Observing Different Types of Responses

* Instead of getting only the Response body, if you want the whole Response object, then we can configure the request in the config object passed as last argument with *observe* key
* The value should be 'response'
* You can also observe 'events'
* We can observe this using **tap** operator which we can chain in pipe which allows us to execute some code without altering the response sent to the subscribe
* You can check the event type with TS HttpEventType
  * Write it and add . at the end and hover over it to observe the codes

### 22. Changing the Response Body Type

* Default responseType is 'json'
* We can change it to 'text' or 'blob' if it is a file

### 23. Introducing Interceptors

* If we want to perform an operation to all outgoing requests, we use an Interceptor(for e.g Authenticate user and add certain param or header)
* Check auth-interceptor.service.ts which implements HttpInterceptor which forces to add intercept method
* next for request to continue on its journey
* IN the AppModule, we need to mention that in providers with an object with 3 keys
  * provide, useClass and multi
  * multi for more than 1 Interceptor otherwise it will replace