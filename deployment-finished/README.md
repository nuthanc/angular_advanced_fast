
### 3. Using Environment Variables

* Check environments folder
* Add key value pairs to the constant in ts file
* Using API key in AuthService
  * Instead use firebaseAPIKey and import it
* environment.ts and environment.prod.ts are swapped automatically by Angular cli based on the env used

### 4. Deployment Example Firebase Hosting

* ng build --prod
* Compiles TS code to JS
* Compiles Templates to JS instructions
* After running ng build, we get the dist folder
* To deploy, google for Static website hosts
  * aws s3
  * firebase hosting
    * firebase cli
* Using firebase hosting cause that's easy to use
* sudo npm i -g firebase-tools
* firebase login
* firebase init in Angular project
  * Hosting
  * public dir: dist/<project-name>
  * Y to SPA
  * n to not override existing index.html
* firebase deploy
  * url for App

### Server Routing vs Browser Routing

```txt
When deploying your Angular app, it's really important to make sure that your server (like S3) is configured to always serve the index.html file.

Here's why: https://academind.com/learn/angular/angular-q-a/#how-to-fix-broken-routes-after-deployment
```