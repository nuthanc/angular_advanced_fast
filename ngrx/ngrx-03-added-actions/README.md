### 9. Dispatching Actions

* You can also subscribe to the store's select method
* Unsubscribe would be done automatically by Angular and ngrx, but to be super safe manually store and unsubscribe
* Check ShoppingEditComponent for dispatching actions
* First inject the store and use dispatch method in onSubmit
  * Note: Actions are defined in shopping-list.actions.ts
* Add payload to constructor as a public property
  * public because we need to access it in Reducers
* Now add Ingredient is the only thing that works in ShoppingEditComponent
* The flow will be like this
  * When a new Ingredient is added, the action is dispatched to all the reducers with the store's dispatch and action object as argument
  * The reducer with the correct type processes it and updates the store

### 10. Multiple Actions

* In shopping-list.actions.ts, add another action class AddIngredients and ADD_INGREDIENTS constant
* In shoppingListReducer, we get an error when we try to add ShoppingListActions.ADD_INGREDIENTS case
* This is because we are mentioning action as ShoppingListActions.AddIngredient
* But there is another action class in shopping-list.actions.ts
* So we can export ShoppingListActions as a type of union of all the Action classes
* Inject store in RecipeService and dispatch action in addIngredientsToShoppingList