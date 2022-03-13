### 2. Adding an Alert Modal Component

* Authenticate -> Login -> Incorrect credentials -> Error Message
* Check Alert Component created in shared
* Css of backdrop is a positive z-index background
* Use app-alert in the Auth Component's template

### 3. Understanding the Different Approaches

* These Components are not always there but created only when something specific happens
* Loaded Programmatically
  * Using ngIf
    * Component embedded via selector (declaratively)
    * ngIf controls whether Component is added to the DOM
  * Dynamic Component Loader
    * Helper utility that we shouldn't use anymore
    * Component created and added to DOM via code (imperatively)
    * Component is managed & added by developer

### 4. Using ngIf

* onClose method in Alert and there emitting close event
* Listen to close in Auth Component and call onHandleError where error is set to null
* This approach is the recommended one as it is much easier

### 5. Preparing Programmatic Creation

* Add showErrorAlert for this approach
* Can't create new Component using new cause Angular doesn't understand this to wire a Component, changeDetection etc
* We need to inject ComponentFactoryResolver
* To tell where to add, we might think Local Reference and View Child would work, but no
* We need ViewContainerRef
* ViewContainerRef is an object managed by Angular which gives a pointer/reference to a place in the DOM
* Create placeholder directive for this in shared directory

### 6. Creating a Component Programmatically

* Use ng-template instead of div to add the appPlaceholder
* In AuthComponent's ViewChild, type is passed which will look for its existence in the template
* Clear anything created before on hostViewContainerRef
* Use hostViewContainerRef's createComponent and pass the alertCmpFactory
* There is some error after this