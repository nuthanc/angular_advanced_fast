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