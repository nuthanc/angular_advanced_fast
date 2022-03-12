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