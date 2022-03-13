### 3. Analyzing the AppModule

* Check NgModule in AppModule and AppRoutingModule
* declarations contain all the Components, Directives and Pipes that we are going to be using in our App(templates or routes)
* imports allows to import other modules
  * like AppRoutingModule
  * other in-built modules like FormsModule
* providers for all the services
  * AppModule or providedIn: 'root'
* bootstrap for starting the App(Root Component)
  * Which Component in index.html
* entryComponents for Components created in Code(Programmatic Imperative)
* AppRoutingModule contains our Routing configuration
  * We could have added this to AppModule
  * But we outsourced it to keep our AppModule leaner
  * exports for it to become available in another Module
* Every Module works on its own and doesn't communicate with each other by default