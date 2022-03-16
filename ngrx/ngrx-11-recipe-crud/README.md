### 39. Fixing the Auth Redirect

* Add redirect property in Auth Action AuthenticateSuccess
* When autoLogin effect, set redirect to false
* Add redirect to true in handleAuthentication for manual login and signup