### 12. Using a Service for Http Requests

* Move the http code to a service to make our AppComponent leaner and related to only template related work like handling of the listeners, initialization, inspecting etc
* Create posts service to handle http
* Move code from onCreatePost from App to PostsService's createAndStorePost
* Similarly move fetchPosts to the service
* Inject PostsService in App Component

### 13. Services & Components Working Together

* 1st Approach of Communication between Service and Component is Subjects
* Use Subjects and communicate using next to our AppComponent(subscribe in AppComponent) regarding the GET response
* 2nd Approach is to just return the Observable and subscribe in the Component
* Result Handling in the Component but the heavy lifting(sending of Request and transforming the data) in the Service
* If the Component doesn't care about the Response, subscribing can be done in the Service itself

### 14. Sending a DELETE Request

* deletePosts in posts.service.ts
* Subscribing in the Component to reassing the property

### 15. Handling Errors

* Change Rules in firebase for read: false
* Now we get an Error
* 2nd argument to subscribe for error callback
* Set error property based on error.message
* Console log the error to check all the keys and values

### 16. Using Subjects for Error Handling

* If multiple places in the App are interested in the Error, then we can use a Subject for this
* check this in createAndStorePost method in PostsService
* Don't forget to unsubscribe in the Component

### 17. Using the catchError Operator

* catchError gets the same errorMessage as what we get in the 2nd argument of the subscribe method
* catchError Operator in pipe to perform generic error handling stuff like sending it to Analytics
* Note we need to return and throwError the errorResponse for it to reach subscribe