### 17. Attaching the Token with an Interceptor

* Add AuthInterceptorService in auth folder
* Don't use providedIn: 'root' in Injectable cause we need to do it differently in AppModule's providers with the 3 arguments
* Now, no need to add params in data-storage.service.ts
* Add condition in interceptor for no user

### 18. Adding Logout

* logout method in AuthService -> set user to null
* Redirecting from Service and not Component because there are multiple places from which we can logout