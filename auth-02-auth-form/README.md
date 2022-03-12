### 4. Switching Between Auth Modes

* isLoginMode in AuthComponent to switch

### 5. Handling Form Input

* Using Template Driven approach
* Add ngModel, required and email | minlength to the inputs
* Disable based on authForm

### 6. Preparing the Backend

* In Firebase -> Authentication -> Setup Signup method -> Email/Password -> Enable
* Database -> Rules -> for read and write: "auth != null" and Publish

### 7. Make sure Recipes are there in your backend

```txt
In order to continue with this module and send successful authenticated requests, you need to ensure that you got recipes stored in your backend database.

So in case you deleted those (or never added any), make sure you do add some recipes before you turn on protection as shown in the last lecture!
```