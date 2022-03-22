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