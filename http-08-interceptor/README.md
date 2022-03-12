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