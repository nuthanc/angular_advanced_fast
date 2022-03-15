### 21. And Important Note on Actions

* When ngrx starts up, it sends an initial action to all reducers and the action has a type which we don't handle in the switch case, we need to add a default case which takes the initial state
* In all reducers, handle default case because when actions are dispatched, it goes to all the Reducers
* If the case doesn't match, we need to return the state in default case for that reducer slice, else we will lose that reducer's state
* For bigger apps to avoid clashed in the Action constants, use name of the feature in square brackets
* export const ADD_INGREDIENT = "[Shopping List] ADD_INGREDIENT" OR "[Shopping List] Add Ingredient"