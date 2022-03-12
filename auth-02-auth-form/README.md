### 4. Switching Between Auth Modes

* isLoginMode in AuthComponent to switch

### 5. Handling Form Input

* Using Template Driven approach
* Add ngModel, required and email | minlength to the inputs
* Disable based on authForm

### 6. Preparing the Backend

* In Firebase -> Authentication -> Setup Signup method -> Email/Password -> Enable
* Database -> Rules -> for read and write: "auth != null" and Publish