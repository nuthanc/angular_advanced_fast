### 12. Understanding Lazy Loading

* We load everthing whenever we visit any Page
* Only load when needed
* With lazy loading, we only load the Root Module and its Components code
* Only when we visit the other module, we load those Module and components

### 13. Implementing Lazy Loading

* Go to Network tab and reload in Auth page unauthenticated
* 4 js files, polyfills.js, styles.js, vendor.js and main.js
* There are big in size
* With lazy loading, we can decrease that
* For Lazy loading to work, the feature module needs to bring in its own routes(with forChild)
* Path in feature needs to be empty path
* Add in AppRouting module the routes, the path which was emptied and then loadChildren
* After adding this lazy loading, we don't need to import in imports os AppModule

### 14. More Lazy Loading

* Add Lazy loading for ShoppingList as well