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