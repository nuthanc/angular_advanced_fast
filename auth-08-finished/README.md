### 21. Adding an Auth Guard

* Adding Route Guard to prevent manual loading of a route
* Create AuthGuard for this
* Add this to Recipes path in AppRouting
* Earlier we had to use tap and inject router and redirect
  * Some cases, this leads to Race condition(Multiple redirects that interfere with each other)
* Now, we return urlTree if it's false
* urlTree created with router
* We don't want an ongoing Subscription, so we use take(1)