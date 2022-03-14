### 6. Understanding & Adding Actions

* Check shopping-list.actions.ts
* Move this and reducer to store folder
* Add constant for type
* Add a class which implements Action

### 7. Setting Up the NgRx Store

* import * as ShoppingListActions from './shopping-list.actions';
* Now state argument action: ShoppingListActions.AddIngredient
* To add Application Store, add StoreModule.forRoot() to imports of AppModule 
  * forRoot takes Action Reducer map object
  * key name is upto us