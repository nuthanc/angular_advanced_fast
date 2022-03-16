### 36. Getting Started with NgRx for Recipes

* Add store folder in recipes
* Create actions, reducers and effects
* Dispatch action from data-storage.service.ts and select in RecipeList Component

### 37. Fetching Recipe Detail Data

* Inject store in recipe-detail
* We can call map and subscribe within route params pipe
* But we can also create a big Observable by calling pipe on the params
* Same approach on recipe-edit