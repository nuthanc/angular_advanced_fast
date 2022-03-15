### 11. Preparing Update & Delete Actions

* Add actions for UpdateIngredient and DeleteIngredient in shopping-list-actions.ts

### 12. Updating & Deleting Ingredients

* Add cases for actions in shoppingListReducer
* Note to update data immutably
```ts
const ingredient = state.ingredients[state.editedIngredientIndex];

// ingredient.amount = ... This is wrong
const updatedIngredient = {
...ingredient,
...action.payload
};

```
* In ShoppingEditComponent, dispatch action for edit ingredient in onSubmit

### 13. Expanding the State

* In ShoppingEditComponent ngOnInit, the values are coming from service and not the store
* To translate startedEditing Subject, we can dispatch an action
* Add editedIngredient in the initialState of shoppingListReducer
* Since we are adding new property in state, we have to change everywhere where state was injected
* So instead, use a State interface
* We can go a step further and add AppState interface

### 14. Managing More State via NgRx

* Add StartEdit and StopEdit actions in shopping-list-actions.ts
```ts
case ShoppingListActions.START_EDIT:
      return {
        ...state,
        editedIngredientIndex: action.payload,
        // Bad because we are passing the original reference(because ingredient is an object) and if it is changed in the Component, it is directly changed in the store
        // editedIngredient: state.ingredients[action.payload]
        editedIngredient: { ...state.ingredients[action.payload] }
      };
```
* IN ShoppingListComponent, dispatch an action instead of using the service in onEditItem
* The in ShoppingEditComponent, dispatch  StopEdit in onClear
  * In ngOnInit, select shoppingList and subscribe from it
  * Also unsubscribe the subscription

### 15. Removing Redundant Component State Management

* We don't need editIngredient index property in the Component as we already have it in the store's state
* So we can remove them from the action argument from Edit and Delete actions
* Also in the reducer, update editedIngredient: null and editedIngredientIndex: -1 in UPDATE_INGREDIENT and DELETE_INGREDIENT
### 16. First Summary & Clean Up

* Add StoreModule and forRoot which contains a map of Reducers in AppModule
* Reducer returning new state based on Action type
* Action classes containing type and payload(optional)
* Initial setup requires lot of work but later adding new state is easy

### 17. One Root State

* Add authReducer and import it in AppModule
* Global store folder and import all in appState and create an ActionReducerMap which is similar to what forRoot does in StoreModule