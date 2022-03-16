### 34. Using the Store Devtools

* Google search "Redux devtools extension"
* Install from Chrome or Firefox store
* npm i @ngrx/store-devtools
* Add StoreDevtoolsModule.instrument() in imports of AppModule
  * The argument takes logOnly
* Find Redux in Browser Developer Tools

### 35. The Router Store

* npm i @ngrx/router-store
* This is for reacting to Routing actions
* Add StoreRouterConnectingModule.forRoot() in imports of AppModule
* Find Redux in Browser Developer Tools
  * Now you see more actions being dispatched