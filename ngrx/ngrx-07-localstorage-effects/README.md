### 28. Preparing Other Auth Actions

* Add authSignup property in AuthEffects
* export constants in auth.action.ts
* We can reuse login_success and fail for signup, so rename as authenticate

### 29. Adding Signup

* Grab signup code from AuthService and use in authSignup

### 30. Further Auth Effects

* Handle SIGNUP_START in the same case as LOGIN_START by letting it fall through
* Unsubscribe store in Authcomponent
* Action for CLEAR_ERROR
* Multiple actions redirect in authRedirect Effect