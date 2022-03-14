
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