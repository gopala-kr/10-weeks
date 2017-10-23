# Module

* A `module` acts as container for other AngularJS managed objects (controllers, services and son on).
* To define new module provide it's name as the very first argument to the module function call. The second argument makes it possible to express a dependency on other modules.
* A call to the `angular.module` function returns an instance of newly created module.
* Globally-defined controller's constructor functions are only good for quick-code examples and fast prototpying. Never user globally-defined controller functions in larger, real-life applications.

# Dependency Injection

AngularJS has the dependency injection (DI) engine built-in. To perform the following activities:
* Understand a need for a collaborator expressed by objects.
* Find a needed collaborator.
* Wire up objects together into a fully-functional application

# Modules Lifecycle

AngularJS splits module's lifecycle into two phases, which are as follows:
* The configuration phase
* The run phase

# The configuration phase

* It is the phase where all the recipes are collected and configured.
* The configuration phase allows us to do the last moment tweaks to the object's creation formula
* AngularJS can have multiple configure blocks

# The run phase

* Allows us to register any work that should be executed upon the application's bootstrap.
* AngularJS can have multiple run blocks

# AngularJS modules and files

There are basically three approaches we could take to relate individual files and AngularJS modules:
* Allow multiple AngularJS modules in one JavaScript file
* Have AngularJS modules spanning multiple JavaScript files
* Define exactly one AngularJS module per JavaScript file