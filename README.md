# angular_advanced_fast

## Using Pipes to Transform Output

### Introduction & Why Pipes are Useful

* Used for transforming Output without changing the property

### Attached pipes-start and pipes-final

* Check README in pipes-final

## Making Http Requests

### Attached http-01 to http-09

* Check each projects README starting with http-02

## Course Project - HTTP

* Add prj-http-01 and prj-http-02
* Check README in prj-http-02

## Authentication & Route Protection in Angular

### How Authentication Works

* Client -> Sends Auth Data -> Server(Restful API which is stateless) -> Token
* Client stores token in Storage
* Stored Token is sent to authorize subsequent request

### Attaching auth-01-auth to auth-08

* Check its README

## Dynamic Components

### Module Introduction

* Dynamic Components are Components created at Runtime
* E.g: Showing a Modal, Alert, Overlay which only should be loaded upon certain action like error 

### Attaching dyn-cmp-finished

* Check its README

## Angular Modules & Optimizing Angular Apps

### What are Modules

* Ways of *bundling Angular Building blocks*(Components, Directives, Services, Pipes) together
* Every Angular App requires *atleast 1 Module*(AppModule)
* Angular analyzes NgModules to *understand* your application and its features
* *Core Angular features* are included in Angular modules(e.g. FormsModule) to load them only when needed
* You *can't use a feature/building block* without including it in a Module

### Attaching opt-mod-01 to opt-mod-06

* Check their READMEs

## Deploying an Angular App

### 2. Deployment Preparation & Steps

* Use and Check environment variables
* Polish & Test Code
* ng build --prod
  * Use AOT compilation
* Deploy build artifacts(generated files) to static hosts
  * Because it's only html, js and css