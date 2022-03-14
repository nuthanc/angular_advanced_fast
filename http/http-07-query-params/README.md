
### 20. Adding Query Params

* params key in the last argument's object
* Value is new HttpParams() and set the param names using set method
* We can directly add to the url as well in the http methods
* Adding in params key, we don't have to concatenate a super long string in the url
* For multiple params, use append
* Use let of searchParams because it is Immutable and append returns a new HttpParams object