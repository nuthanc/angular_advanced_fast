### 6. Adding Routes to Feature Modules

* Move Recipe related Route configuration away from AppRouting to RecipesModule
* We need to add forChild in imports
* To keep RecipesModule leaner, create RecipesRoutingModule
* export it and import it in RecipesModule