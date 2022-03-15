### 21. And Important Note on Actions

* When ngrx starts up, it sends an initial action to all reducers and the action has a type which we don't handle in the switch case, we need to add a default case which takes the initial state
* In all reducers, handle default case because when actions are dispatched, it goes to all the Reducers
* If the case doesn't match, we need to return the state in default case for that reducer slice, else we will lose that reducer's state
* For bigger apps to avoid clashed in the Action constants, use name of the feature in square brackets
* export const ADD_INGREDIENT = "[Shopping List] ADD_INGREDIENT" OR "[Shopping List] Add Ingredient"

### 22. Exploring NgRx Effects

* Side effects are parts in code where you run some logic but is not important for immediate update of the current state
* Eg: Http request and Local Storage
  * Result of http request matters but the actual sending doesn't matter
* Package is @ngrx/effects
* npm i @ngrx/effects