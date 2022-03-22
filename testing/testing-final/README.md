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