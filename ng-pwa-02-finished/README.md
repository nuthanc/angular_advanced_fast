# AngularPwa

### Introduction 

* Inspect -> Application -> Service Workers -> Offline 
* There is no Internet connection

### 2. Adding Service Workers

![SW](../img/sw.png)
* Proxy between Frontend App and Backend
* Cache response from Backend and serve it for successive requests without making API call
* ng add @angular/pwa
  * Add something to manifests.json and index.html and app.module.ts an ngsw-config.json and angular.json
* ng build --prod
  * ngsw-worker.js
* npm install -g http-server
  * Simple node based server
  * Host the content of the folder
  * cd dist/angular-pwa
  * http-server -p 8081
* Inspect -> Application -> ngsw-worker.js
* Offline and Reload and it works
* Add static content in app.component.html
* ng build --prod
* cd dist/angular-pwa && http-server -p 8081
* Reload twice because of fetching from cache