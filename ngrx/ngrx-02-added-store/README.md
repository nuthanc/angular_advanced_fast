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

### 8. Selecting State

* In ShoppingListComponent, inject store of type Store(feature added by ngrx)
* Store is a generic type and key should be same as what is given in AppModule's StoreModule.forRoot() and value is what the Reducer function yields
* Use select method to get an Observable
* Now ingredients: Observable<{ ingredients: Ingredient[] }>
* This will break the templates since we are looping through it
* But it's an easy fix with async pipe
  * (ingredients | async).ingredients
* Add default case in reducer