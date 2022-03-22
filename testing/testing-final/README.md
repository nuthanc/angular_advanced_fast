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