### 15. Reflecting the Auth State in the UI

* Redirecting can be done in the Component(inside subscribe) or the Service(handleAuthentication)
* Inject router to AuthComponent
* Add Logout button in Header Component
* Inject AuthService in Header and add isAuthenticated property
* user Subject source of truth

### 16. Adding the Token to Outgoing Requests

* data-storage.service.ts needs to have the tokens in the requests
* Inject AuthService
* Need access to user(contains token) cause we need it in the store and fetch recipes
* We could have a subscription to get the above
* But for in-demand access, we can have a separate variable property in AuthService
* Instead of having variable, we can have a BehaviorSubject
  * It behaves like normal Subject
  * In addition, it gives immediate access to the previously emitted values even if it is not subscribed
  * Needs to be initialized with starting value
* Then in DataStorageService, use pipe and take(1), which means unsubscribe after getting the value once
* exhaustMap is used for getting a new Observable for the computation done within it