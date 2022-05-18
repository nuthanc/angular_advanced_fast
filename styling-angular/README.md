# PluralSight Angular Styling course

* https://github.com/pluralsight-styling-angular-apps/demos

## How Styles Work in Angular

### Web Components

* Example of Web Component: HTML5 Video player
* Web Components consists of 3 parts
  * Custom Elements: Allow us to create and use our own elements
  * HTML templates: Fragments of Markup referenced elsewhere
  * Shadow DOM: Encapsulated DOM for styling and scripting. IN shadow of Light DOM
    * Can see the markup but can't access it from parent styles of JS and vice versa

### View Encapsulation

* Angular inserts the content of the Template directly within the selector we provided in the Component
* Style blocks in the head is where Angular inserts the style for our Component
* Emulated: Provides scoping by unique host(_nghost*) and content(_ngcontent*) attributes(Attributes are Unique to a Component)
  * If no style is added in the Component, then Angular doesn't add the Scoping attributes
* ShadowDOM: Handled by Browser. Native Shadow DOM for Browsers that support it
  * Shadow root which will isolate the styles and markup outside the scope of the Parent document
  * #shadow-root element which we can expand
* None: No scoping and styles applied are global
  * Good for Global styles at the root of our App

### Emulated CSS selectors

* style block within the template
* Inline styles
* Link and external stylesheet
* Angular styleUrls
* :host, :host-context and :ng-deep
  * :host -> For targeting the Host or the Component
    * :host('class-name'): Apply style to the Host only when it has that class name
  * :host-context -> For targeting the Host or its Ancestors
    * :host-context('class-name'): Apply style to the Host or its Ancestors only when it has that class name
  * ::ng-deep -> Deep combinator, this emulates by removing the scoping attributes
    * Example like content projected from Parent to Child but child can't style the projected content
    * Use it with :host and more specific element like :host ul ::ng-deep

### Global Styles: A Traditional Approach(No Style Encapsulation)

* Flat, Low specifity approach
* BEM convention separating by prefix
* Breaking Up large files into Partials
* First approach: External Link Method
  * All css in global area: styles under src
    * Styles for styling all of the Components
  * In styles.scss, import all the partials
  * No style file in the Components
* Second approach: View Encapsulation Method
  * View Encapsulation mode to None
  * Add styleUrls pointing to styles.scss in App Component
  * Style sheet processed by Angular and will be embedded in the head of the Document
    * Styles will not be available until App is fully loaded and processed by Angular
    * Important when styling the App Loading screen
* What should be in Global space
  * Browser Resets
  * Colors
  * Common Typography
  * Layout systems
  * Media Queries
  * Utilities

### Global Styles: A More Modular Approach

* Both Global and Local Styles
* Use of Sass for Mixins, Partials