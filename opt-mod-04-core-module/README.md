### 10. Understanding the Core Module

* CoreModule is used for making AppModule leaner
* Mainly used for Services
* Alternative is to use providedIn in the Services itself(recommended) so it doesn't have to be added to providers
[Core Module](../img/core.png)
* Check CoreModule
* Services doesn't need to be exported
* Import CoreModule in AppModule

### 11. Adding an Auth Feature Module

* Add AuthModule