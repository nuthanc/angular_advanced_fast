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

### 31. Adding Auto-Login with NgRx

* Add AutoLogin action and handle localStorage in handleAuthentication
* Add authLogout effect and autoLogin effect
* Dispatch AutoLogin action in app.component.ts
* In AuthEffects map, we need to return dummy action for conditions not caught in if

### 32. Adding Auto-Logout

* Manager timer in AuthService and call in Effects
* Race condition in AuthGuard and effect
* Remove logout from authRedirect effect and in separate authLogout actino