### 41. Storing Recipes via Effects

* Add storeRecipes Effect and StoreRecipes action
* To get recipes in switchMap of storeRecipes, we use withLatestFrom which allows to merge a value from another observable to the next observable stream
* The recipes are pulled from the store in withLatestFrom and in switchMap, we now automatically get an array of arguments which holds the data provided by ofType which is our actionData and recipesState(data from withLatestFrom)
* Array Destructuring assignment done in the Argument
* Set dispatch to false
* Then in the header remove the data storage service and replace with dispatch action of STORE_RECIPES

### 42. Cleanup Work

* We can get rid of RecipeService and clean that up in CoreModule

### 43. Wrap Up

* ngrx.io
* github ngrx -> ngrx/platform -> projects -> example-app