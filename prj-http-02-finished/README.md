### Module Introduction

* Functionality for Manage -> Save and Fetch Data

### 2. Backend (Firebase) Setup

* Firebase -> Project Name
* Database -> Realtime Database
* Test Mode, take url

### 3. Setting Up the DataStorage Service

* Buttons in header Component but we don't have any data here since the data is in the Recipe service
* We can add it in Recipe service or new service in shared called data-storage.service.ts
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