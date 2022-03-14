### 18. Adding Logout

* logout method in AuthService -> set user to null
* Redirecting from Service and not Component because there are multiple places from which we can logout

### 19. Adding Auto-Login

* Since App Restarts, we'll lose everything since everything is stored in the memory
  * Token stored in User model
* We will use Local Storage for this
* Local Storage is an API exposed by the browser to store key-value pairs in the file system but controlled by the Browser
* In AuthService handleAuthentication localStorage.setItem to store the key value pair
* value is string which is done using JSON.stringify of the user object
* Now we can check in Inspect -> Application -> Local Storage
* Retrieve that when application restarts using autoLogin method
* Call autoLogin in App Component
  * This is the place which runs early in our App lifecycle

### 20. Adding Auto-Logout

* Clear data when Logging out
* autoLogout() and setTimeout
* autoLogout's setTimeout shouldn't be running when User manually hits Logout
* So in logout we need to clear that timer
* autoLogout should be called in handleAuthentication and autoLogin