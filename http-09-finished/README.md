### 24. Manipulating Request Objects

* IN Interceptor, we can modify the request
* However Request object is Immutable
* We should use req.clone() to create another Request with whatever you need to modify
* The old keys will still be there if you don't override
* In next.handle pass the modifiedRequest

### 25. Response Interceptors

* We can interact even with the Response in the interceptor
* Because handle gives back an Observable
* tap for just looking into the Response without modifying it
```ts
return next.handle(modifiedRequest).pipe(
    tap(event => {
        console.log(event);
        if(event.type === HttpEventType.Response) {
            console.log('Response arrived, body data: ');
            console.log(event.body);
        }
    })
);
```