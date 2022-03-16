### 39. Fixing the Auth Redirect

* Add redirect property in Auth Action AuthenticateSuccess
* When autoLogin effect, set redirect to false
* Add redirect to true in handleAuthentication for manual login and signup

### 40. Update, Delete and Add Recipes

* Add actions for ADD_RECIPE, UPDATE_RECIPE and DELETE_RECIPE
* Add reducers for those cases
* Dispatching and unsubscribing of store in the Components