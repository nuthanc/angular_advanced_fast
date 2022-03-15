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

### 23. Defining the First Effect

* Add auth.effects.ts in store
* Inject Actions from effects
  * Convention $ at the end
* Actions is one big observable that will give access to all dispatched actions
* Effects are added as a normal property in the Class
  * No need to call subscribe because ngrx effects will call it for us
  * With ofType we can filter for types
* Add LOGIN_START in auth.actions
  * We can rename LOGIN to LOGIN_SUCCESS but we can leave it as it is
* ofType triggers only when action of that type is triggered

### 24. Effects & Error Handling

* Create LoginStart class in auth.actions.ts
* switchMap for creating new Observable by taking data from another Observable
* Copy http post snippet from login method from AuthService and paste in switchMap
* An effect by default should return a new Action at the end because effect by itself doesn't change the state
* So we need to add @Effect decorator to the property
* Effects need to be an ongoing Observable screen(must never die as long as our app is running)
* Errors have to be handled on a different level
* Need to add pipe on the inner observable
* Use 'of' to create new Observable without Error
* If we create an Error the Observable dies
  * An Observable completes whenever an Error is thrown

### 25. Login via NgRx Effects

* IN of(), we need to create a new Action
  * No need to dispatch, cause ngrx effects will automatically do that
* To wire effects, we need to add @Injectable decorator to the AuthEffects Class
  * providedIn root not req because it is never injected itself
  * It needs Injectable so that things can be injected to this class like http and actions
* Registering is done in AppModule after StoreModule
  * EffectsModule.forRoot
* In AuthComponent, inject store and dispatch LoginStart