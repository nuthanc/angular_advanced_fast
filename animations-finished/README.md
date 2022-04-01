### 1. Making Animations Work with Angular 4+

```txt
With the release of Angular 4, the general syntax of Angular Animations didn't change. 

However, the animation functions were moved into their own package and you now also need to add a special module to your imports[]  array in the AppModule.

Specifically, the following adjustments are required:

You probably need to install the new animations package (running the command never hurts): npm install --save @angular/animations 
Add the BrowserAnimationsModule  to your imports[]  array in AppModule
This Module needs to be imported from @angular/platform-browser/animations'  => import { BrowserAnimationsModule } from '@angular/platform-browser/animations'  (in the AppModule!)
You then import trigger , state , style  etc from @angular/animations  instead of @angular/core 
That's all!
```

### 4. Animations Triggers and State

* Add animations in @Component Decorator
* Each animation needs to have a trigger
* Property bind name of the trigger and set the value to a state(Can be any name, but state is appropriate here)
* With Animations, you transition from state 1 to state 2
  * i.e we work with states
* So, in the trigger mention the 2 states and their styles
* Still we don't see any animation, but only see the normal state's css styles

### 5. Switching between States

* Add functionality for onAnimate method which is triggered on click of Animate button
* Switch the state in that method