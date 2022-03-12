### 15. Reflecting the Auth State in the UI

* Redirecting can be done in the Component(inside subscribe) or the Service(handleAuthentication)
* Inject router to AuthComponent
* Add Logout button in Header Component
* Inject AuthService in Header and add isAuthenticated property
* user Subject source of truth