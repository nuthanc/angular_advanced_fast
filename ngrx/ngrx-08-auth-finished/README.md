### 32. Adding Auto-Logout

* Manager timer in AuthService and call in Effects
* Race condition in AuthGuard and effect
* Remove logout from authRedirect effect and in separate authLogout actino

### 33. Finishing the Auth Effects

* Moving setLogoutTimer and clearLogoutTimer to effects would require lot of Observable magic
* So we can leave it in the service