### 3. Adding Angular Universal

```sh
ng add @nguniversal/express-engine --clientProject <id>
# id is under projects in angular.json file
ng add @nguniversal/express-engine --clientProject basics
```
* Ensure ModuleMapLoader is imported and used in imports of app.server.module.ts
  * If not, npm i @nguniversal/module-map-ngfactory-loader
  * This is to allow Lazy loading
* Certain Browser Only APIs won't be available after this, namely localStorage
* Use @Inject(PLATFORM_ID) in AppComponent 
  * Inject globally provided value and assign to platformId
* Also use isPlatformBrowser from @angular/common to run autoLogin dispatch
* This will also run in the Browser and there localStorage is available, so autoLogin is dispatched
* package.json has build:ssr
  * npm run build:ssr
* Host must be capable of executing NodeJS to server Angular Universal App
* Static Host will no longer work
* serve:ssr on that host
* If you now inspect Page Source, you will see the actual contents of the Page

### 4. Adding Angular Universal with NestJS

```sh
ng add @nestjs/ng-universal
```
* NestJS allows you to write server side code along with Angular Universal
  * FullStack
  * server folder