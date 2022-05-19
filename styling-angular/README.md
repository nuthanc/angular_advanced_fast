# PluralSight Angular Styling course

* https://github1s.com/pluralsight-styling-angular-apps/demos
* https://app.pluralsight.com/course-player?clipId=34673589-69cf-4c19-b2a6-0e022c9e0aa7
* Some notes in Pluralsight

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
  * All css in global area: **styles under src**
    * Styles for styling all of the Components
  * In **styles.scss**, import all the partials
  * This styles.scss is loaded in angular.json
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

### Global Styles: A More Modular Approach(Style Encapsulation)

* Not all Styles need to be Encapsulated
  * Both Global and Local Styles
* Global Styles: 2 Approaches
  * Class Based System
  * Mixins and variables only
* **scss directory in shared folder** under App for Global styles
  * various directories and partials within them
    * Prefix them with directory single letter like l-(or anything else) to avoid conflicts
  * Rest of the Local styles in the Component
* How to include these Global styles in the Component. There are 2 ways:
  * Root styles.scss
  * Turn Off View Encapsulation in App component
    * Styles not visible until App has fully loaded, so we'll have to link to them in the root style sheet instead
* With many Global styles in the Component, it will look messy
* This can be prevented by converting the global items into mixins and variables and importing them
* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-06
* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-07
* General rules: 
  * Include Mixin first and include our styles later
  * Never override any styles(Rarely make an exception)
* Normalize.css for Browser Reset
  * Reset all Default Browser styles to make it a Plain levelling field
* Down side of this approach: Code duplication after processing to css

### Simplifying Global Imports

* Add stylePreprocessorOptions object in angular.json
  * Include all the global style files in includePaths array
* Now in the imports, we can simply include the file name
* Recompile the App for the changes to take Effect

### Naming Conventions

* B.E.M convention for Block Element Modifier
  * block__element--modifier
```html
<ul class="nav">
  <li class="nav__item"> 
    Home
  </li>
  <li class="nav__item nav__item--active">
    About
  </li>
</ul>
```
* We can create more simplistic class names since names are local within the Component
* Check Traditional B.E.M vs Angular notes
  * The names are simple in Angular as they are local to the Component
  * Like items and item instead of app-navbar-header and app-navbar-header__item
  * For Modifier, item--selected instead of app-navbar-header__item--selected

### Predictable Sizing with Relative Units

* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-12
  * Check accordion component styles
  * All styles with px
  * Switch to Relative units(like em) to make life easier
* Unpredictable results since Angular components are Modular and relative units are based off Parent
* We can use the rem unit to fix this
  * In every Component(:host), set its base font size to 1 rem 
* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-14

### Good CSS Practices & Style Overrides

* Keep Specificity Low
  * Only use classes
  * Pseudo classes
  * Adjacent sibling combinator(.class + .sibling)
  * Only veer from this when there is absolutely no other way
* Avoid IDs altogether
* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-15
  * navbar-primary Comp
  * bem convention
  * Sass '&' Feature for parent name(https://css-tricks.com/the-sass-ampersand/)
    * For ex, if parent is .item and we want .item__icon, we can simply use &__icon
* Have styles similar to order of markup as seen below
* https://github1s.com/pluralsight-styling-angular-apps/demos/tree/module-03-16
  * navbar-primary Comp
* Avoid for the most part Overriding styles
  * https://github1s.com/pluralsight-styling-angular-apps/demos/blob/module-03-17/app/shared/components/content/tabs/tabs.component.scss
  * Add separate classes for inactive and active, instead of overriding in active
* Responsive design
  * https://github1s.com/pluralsight-styling-angular-apps/demos/blob/module-03-18/app/shared/components/navigation/navbar-primary/navbar-primary.component.scss
  * Completely separate out min-width and max-width instead of overriding styles

### Component CSS Structure & Organization

* Break main Component scss file into a series of partial files
* https://github1s.com/pluralsight-styling-angular-apps/demos/blob/module-03-19/app/app.component.scss
* Check scss directory in app folder
* globals file for host pseudo class that is generic and other files according to the styles they are applying
* Finally use @import and import them in app.component.scss instead of styleUrls in ts file
  * Using styleUrls will create style blocks for each scss file in the array
* https://github1s.com/pluralsight-styling-angular-apps/demos/blob/module-03-20/app/app.component.scss