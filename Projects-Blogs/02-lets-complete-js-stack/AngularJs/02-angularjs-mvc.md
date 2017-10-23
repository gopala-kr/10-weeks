# About MVC in AngularJS

* Along with services and dependency injection, MVC makes angular applications better structured, easier to maintain and more testable.

# Understanding the Model Component

* Depending on the context of the discussion in the Angular documentation, the term model can refer to either a single object representing one entity (for example, a model called "phones" with its value being an array of phones) or the entire data model for the application (all entities).

## Undestanding the Controllers Component

### Understanding Controllers

* In Angular, a Controller is a JavaScript **constructor function**

Use Controllers to:

* Set up the initial state of the $scope object.
* Add behavior to the $scope object.

### Scope Inheritance

* If the child controller are having the same properties with the parent controller, then it will override the parent properties.