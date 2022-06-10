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