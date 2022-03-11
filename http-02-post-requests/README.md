### How Does Angular Interact With Backends

* Angular doesn't connect to DB directly as this will be Insecure(Anybody can inspect it from the Browser)
* Angular sends Http Request and gets Http Response from the Server(API)

### The Anatomy of a Http Request

* HTTP Verb
* URL(API Endpoint)
* Headers(Metadata)
* Body

### Backend (Firebase) Setup

* firebase.google.com(Google account)
* Add Project(Default Settings)
* Create Realtime db(Start in Test Mode)

### 6. Sending a POST Request

* App contains Template Driven form
* Add HttpClientModule to AppModule imports
* Inject HttpClient in AppComponent's constructor
* API endpoint .json is firebase related(As it creates folder based on endpoint)
* Normally we send json data to API
* But Angular HttpClient will automatically convert JS object to json for us
* post returns an Observable to which we have to subscribe
* If not subscribed, the request doesn't go through
* No need to Unsubscribe because it completes and also it is managed by Angular
* POST 2 requests in Browser Network tab: one of OPTIONS and the other POST
  * OPTIONS to check whether we are allowed to send and if it's a success we will send the actual POST request