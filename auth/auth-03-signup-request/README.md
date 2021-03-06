### 8. Preparing the Signup Request

* Google for Firebase auth rest api
* https://firebase.google.com/docs/reference/rest/auth#section-create-email-password
```txt
https://identitytoolkit.googleapis.com/v1/accounts:signUp?key=[API_KEY]
```
* auth.service.ts for Requests for signing up and in and managing the token
* Firebase settings -> API key
* Return without subscribing in the service because the Component is interested in the response
* Add interface for the kind of response you will be getting and provide it to the HttpClient methods

### 9. Sending the Signup Request

* In Auth component's onSubmit, we are checking for validity again so that if a User used developer tools to enable the Submit button, we can have this extra validation step here
* Inject AuthService and signup and subscribe 

### 10. Adding a Loading Spinner & Error Handling Logic

* Google for CSS loading spinners
  * loading.io
* Now folder in shared and add loading-spinner and place in the css and ts files
* isLoading and error properties in AuthComponent

### 11. Improving Error Handling

* Error Handling in AuthComponent
* Check Error codes in Firebase and based on that have a switch case
* Instead of having this logic in the AuthComponent, we can handle in the AuthService in the pipe's catchError