### 12. Sending Login Requests

* Add login method in AuthService
* https://firebase.google.com/docs/reference/rest/auth#section-sign-in-email-password
* Add optional registered to AuthResponseData and use in post
* Call login in AuthComponent
* Since same logic of subscribe is for login and signup, create authObs of type Observable and paste the subscribe in this variable

### 13. Login Error Handling

* Share Error Handling logic in private handleError method of AuthService

### 14. Creating & Storing the User Data

* user.model.ts for the User
* getter for token which accesses _token
* Add user Subject in AuthService
* tap operator to signup pipe method
* private handleAuthentication method in AuthService