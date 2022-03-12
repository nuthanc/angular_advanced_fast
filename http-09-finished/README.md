### 24. Manipulating Request Objects

* IN Interceptor, we can modify the request
* However Request object is Immutable
* We should use req.clone() to create another Request with whatever you need to modify
* The old keys will still be there if you don't override
* In next.handle pass the modifiedRequest