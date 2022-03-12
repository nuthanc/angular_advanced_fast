### 12. Using a Service for Http Requests

* Move the http code to a service to make our AppComponent leaner and related to only template related work like handling of the listeners, initialization, inspecting etc
* Create posts service to handle http
* Move code from onCreatePost from App to PostsService's createAndStorePost
* Similarly move fetchPosts to the service
* Inject PostsService in App Component