### Module Introduction

* Functionality for Manage -> Save and Fetch Data

### 2. Backend (Firebase) Setup

* Firebase -> Project Name
* Database -> Realtime Database
* Test Mode, take url

### 3. Setting Up the DataStorage Service

* Buttons in header Component but we don't have any data here since the data is in the Recipe service
* We can add it in Recipe service or new service in shared called data-storage.service.ts
* This service is for **interacting with the Backend**
* Inject HttpClient in DataStorageService
* Add HttpClientModule in AppModule's imports 
  * Adding before AppRoutingModule because 1st Angular's then our Custom modules

### 4. Storing Recipes

* storeRecipes in DataStorageService
* Inject RecipeService in DataStorageService to get the recipes
* post for 1 recipe
* Using put request to override the data stored previously
* The above depends on the API
* The Header Component is interested in the Response, so we can subscribe in the Service itself

### 5. Fetching Recipes

* fetchRecipes in DataStorageService
* The Header Component is interested in the Response, so we can subscribe in the Service itself
* setRecipes in the RecipeService for overriding with the get response data
  * Don't forget to call the recipesChanged next

### 6. Transforming Response Data

* Bug when Ingredients are not added while adding a new Recipe
* For that we can pipe in fetchRecipes and transform the data using map

### 7. Resolving Data Before Loading

* Add recipes-resolver.service.ts to ensure that there is data
  * Note: Check about resolvers [here](https://github.com/nuthanc/angular_course/blob/main/routing-start/README.md#resolving-dynamic-data-with-the-resolve-guard)
* We are using tap for fetchRecipes and subscribing should be done in the Header Component(since resolve can return Observable<any> | Promise<any>)
* Inside resolve, we don't need to subscribe because it is done automatically once data is there
* Add resolve to routes requiring the data to be present

### 8. Fixing a Bug with the Resolver

* Changes are not saved after Editing
* This is because of the Resolver which fetches new Recipes from the Server and it overrides
* So only fetch when there are no Recipes
  * This is done by injecting the RecipeService in the Resolver