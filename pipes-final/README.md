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