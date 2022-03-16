### 36. Getting Started with NgRx for Recipes

* Add store folder in recipes
* Create actions, reducers and effects
* Dispatch action from data-storage.service.ts and select in RecipeList Component

### 37. Fetching Recipe Detail Data

* Inject store in recipe-detail
* We can call map and subscribe within route params pipe
* But we can also create a big Observable by calling pipe on the params
* Same approach on recipe-edit

### 38. Fetching Recipes & Using the Resolver

* Add fetch recipes action
* Add and use RecipeEffects
* resolve expects an Observable and when we dispatch an action we don't get back an Observable
  * So resolve would instantly resolve and we would instantly load a route where the data is not actually there yet
  * Workaround is wait for the effect that is triggered by the action to complete 
  * The actions observable provided by ngrx/effects can be used in any class without the @Effect decorator
  * Listen for ofType SET_RECIPES, because if that action is triggered that means there are recipes
  * take 1 value and unsubscribe