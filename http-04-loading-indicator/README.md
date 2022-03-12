### 9. Using Types with the HttpClient

* Types of posts is any when you hover over it
* This is because TS doesn't know the responseData
* One way is to assign type to the argument
  * (responseData: {[key: string]: Post })
  * where Post is an interface having title, content and optional id
  * const postsArray: Post[] = []
* However instead of the above, there is much more elegant way to do so
* Check AppComponent's fetchPosts http get method
* this.http.get<{ [key: string]: Post }>
  * Generic type of the response body
* This is available on all requests of HttpClient

### 10. Outputting Posts

* Assign loadedPosts in subscribe and output it in the Template based on its length