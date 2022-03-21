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

### 5. Deploying Universal Apps

```txt
As mentioned in the previous lectures, you can't deploy an Angular Universal app to a static host (i.e. Firebase Hosting, AWS S3 etc will NOT work).

The reason for this is, that you're using Node.js to pre-render pages on the server and those Hosts don't support Node.js.

Hence you need a host that does - for example AWS ElasticBeanstalk or Heroku.

To these hosts, you need to upload your dist/ folder along with the package.json file. On the web server, you then have to ensure that npm install is executed, followed by npm serve:ssr.

That's it - your app is now up and running on a web server!
```