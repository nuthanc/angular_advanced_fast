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