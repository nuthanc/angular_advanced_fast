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