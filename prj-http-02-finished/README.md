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