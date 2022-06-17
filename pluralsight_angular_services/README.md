### Service

* https://github.com/bricewilson/angular-services
* Services are reusable piece of functionality shared across Components
* Analogy: Hospitality Service in a Hotel
  * Room Service
  * House keeping,etc
  * They are shared across all of the Guests in a Hotel
  * Hotel Concierge as a Dependency Injection system for the Hotel services
    * We request services we need from the Concierge
* What in Components?
  * Logic needed for View
* When Service?
  * The necessary functionality is not required by the View
  * Shared Logic
* Using the providedIn: 'root' within the service is Tree Shakable(Leave it out of the build if it is not used anywhere)

### Injecting a Dependency

* Creating a new instance of a Service within a Component makes it tightly couple to the Component
```ts
export class DashboardComponent {
  dataService: DataService;
  constructor() {
    this.dataService = new DataService();
  }
}
```
* DashboardComponent is now very tightly coupled to the type of data service that I'm creating here
  * This makes it very difficult for me to ever use the DashboardComponent with any other type of data service
```ts
export class DashboardComponent {
  constructor(private dataService:DataService) {
  }
}
```
* The above is passing an instance of the class(Service class here) to the Parameter of the Component's constructor
* The dependency will now be simply passed into the dataService parameter
* Type Annotation to make it clear that the type we are taking a dependency on is the DataService type
* This makes the code more flexible by now allowing **any appropriately typed value** to be passed to the component's constructor and used as the DataService instance the component depends on
* Type of the Constructor parameter is DataService class rather than an interface that defines the contract for the instance passed
  * This is possible because TypeScript uses a structural type system
  * Because of this the DataService class can behave much like an interface in a language like C# or Java
  * We are required to pass in a value that has the same shape(same properties and methods) as the declared type

### Provider Tokens and Recipes

* providers value in Decorator of Component and Module serves as a token
* Similarly the Constructor parameter type that will receive the Injected value acts as a token
```ts
providers: [
  DataService
]
// the above is equivalent to
providers: [
  { provide: DataService, useClass: DataService}
// provide is the token and useClass is the recipe
]
```
* The value given to provide is the token used to identify instances
* The value given to the useClass property is the class Angular will create an instance of to associate with the token
  * They will be created with the new keyword

### Multiple ways to Provide Services

* implements can be used with Classes as well just like Interfaces
* A class that implements another class must have the same methods and properties as the other class
```ts
providers: [
  { provide: LoggerService, useClass: PlainLoggerService}
]
// All the components requesting LoggerService will get a PlainLoggerService instance
// This will work because both classes have the same interface

// Another usecase where PlainLoggerService was built as a replacement to LoggerService
providers: [
  PlainLoggerService,
  { provide: LoggerService, useExisting: PlainLoggerService}
]

// useValue for providing whatever value in the provider  instead of a instance created by new keyword
providers: [
  PlainLoggerService,
  { provide: LoggerService, useValue: {
    log: (message: string) => console.log(`MESSAGE: ${message}`),
    error: (message: string) => console.error(`PROBLEM: ${message}`),

  }},
  { provide: DataService, useFactory: dataServiceFactory, deps: [LoggerService]} // use of factory method for creating the instance and deps for arguments taken by the Factory method
]
```

### The Role of Injectors

* Deliver provided services when they're requested via constructor injection
* Maintain a single instance of each service provided
* Delegate injection to parent injectors if no service is provided with the token requested

### Hierarchical Injectors

* The Dependency injection system would first try to locate an instance of the service in the injector associated with the Component receiving the Injection
* If it doesn't find it there, it will then move up a level and look for it in the parent component and its ancestors
* If it doesn't find it there it will finally move up to the root injector
* Don't be tempted to provide your services to the default AppComponent rather than the AppModule
  * If you're using lazy loaded modules, you won't be able to import services provided to the AppComponent