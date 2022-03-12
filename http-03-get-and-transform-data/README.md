### 7. GETting Data

* In get also we need to subscribe, else the request won't be sent
* Check fetchPosts method in AppComponent
* Making get request in ngOnInit so that whenever this Page loads, we make this request

### 8. Using RxJS Operators to Transform Response Data

* Transforming data can also be done in subscribe, but good practise is to use Observable Operators using pipe
* Convert JS object to Array of Posts