### 4. Analyzing the Testing Setup (as created by the CLI)

* spec file in each folder(Check app.component.spec.ts)
* Block beginning with 'it' is a test
* Import TestBed and async
* createComponent in each test
* expect at the end for our Expectation
* detectChanges to trigger changeDetection so that the template gets rendered
* nativeElement gives access to the template

### 5. Running Tests (with the CLI)

* ng test to run our tests
* Make any changes to fail our tests

### 6. Adding a Component and some fitting Tests

* ng g c user
* Add the Component to test in TestBed.configureTestingModule declarations
  * Use compileComponents for non-webpack based setup
* Add a test in 'it' block
* ng test

### 7. Testing Dependencies Components and Services

* Add user.service.ts
* User injector to get the UserService in the test
* Remember to run detectChanges to update our Properties
* Check using toContain and not.toContain about the App's username

### 8. Simulating Async Tasks

* Add data.service.ts for async tasks
* spyOn which keeps on checking when the method gets executed
  * Give back our own data(Faking request to API)
* Wrap callback with async
  * This creates an asynchronous testing environment
  * Also need to use fixture.whenStable()
    * React when all Async tasks are finished

### 9. Using fakeAsync and tick

* Use fakeAsync to get rid of whenStable function but call tick in between
* In a fake Async env, tick allows to finish all async tasks now

### 10. Isolated vs Non-Isolated Tests

* A Pipe can be tested Independently(Isolated)
* Pure functions in a Service can also be tested Independently
* Add reverse.pipe.ts and reverse.pipe.spec.ts
* Just create a new Instance of ReversePipe and check it
* No need for TestBed and other utilities

### 11. More Resources

```txt
This Module only provides a brief and basic Introduction to Angular Unit Tests and the Angular Testing Suite. This Course isn't focused on Testing.

If you want to dive deeper, the official Docs actually are a great place to start. There you'll also find a Non-CLI Setup!

Official Docs: https://angular.io/docs/ts/latest/guide/testing.html

I can also recommend the following Article: https://semaphoreci.com/community/tutorials/testing-components-in-angular-2-with-jasmine

For more Information on how to run Tests with the CLI have a look at their official Docs:

=> Unit Tests: https://github.com/angular/angular-cli/wiki/test

=> E2E Tests: https://github.com/angular/angular-cli/wiki/e2e
```