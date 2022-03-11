### Using Pipes

* Check pipes-start
* Pipes don't change the properties, just the display or output
* Pipes are added in html or templates
* {{ server.instanceType | uppercase }}
* uppercase and date pipes

### Parametrizing Pipes

* Add parameters with :(colon)
* Multiple parameters are separate by colon
* E.g date:'fullDate'

### Where to learn more about Pipes

* https://angular.io/api?query=pipe
* E.g: https://angular.io/api/common/DatePipe

### Chaining Multiple Pipes

* Can apply multiple pipes
* Parsed from left to right

### Creating a Custom Pipe

* filename.pipe.ts (shorten.pipe.ts)
* It's not strictly necessary but you can implement the PipeTransform interface which dictates you to implement transform method
* transform takes **value and list of arguments**
* transform always returns something
* Add ShortenPipe to **declarations in AppModule** just like Components and Directives
* **Pipe decorator** also needs to added to the class to *indicates the name*

### Parametrizing a Custom Pipe

* Pass parameter with colon(shorten:15)
* For multiple parameters, you can specify another colon and the value and in the transform method accept another argument

### Example Creating a Filter Pipe

```sh
ng g p filter --skipTests true
```
* Add input to get the filter from the user
* Use two way binding to filteredStatus property
* Use filter pipe in ngFor loop to filter elements based on the status

### Pure and Impure Pipes (or How to fix the Filter Pipe)

* Pipe by default is run(triggered) only when the Pipe argument(input) changes 
* This a good behaviour, otherwise Angular would have to rerun the Pipe when any data on the Page changes, which causes significant Performance issues
* But if you want it to run even for Array and Object updates, we need to set pure: false in Pipe decorator

### Understanding the async Pipe

* appStatus which resolves asynchronously in AppComponent
* App Status: [object Object] in the beginning because it resolves later
  * Angular doesn't observe this object
* **async** bulitin pipe recognizes that something changed and prints that data
* It works with Promises and Observables