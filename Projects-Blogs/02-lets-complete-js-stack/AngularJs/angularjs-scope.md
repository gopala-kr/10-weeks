* Scope is context where the model is stored so that controllers, directives, and expressions can access it. The values that are stored in variables on the scope are referred to as the model.
* AngularJS will create a new instance of the `Scope` class whenever it encounters a scope-creating directive in the DOM tree. The `ng-controller` directive is an example of scope-creating directive.
* Each `$scope` is an instance of the [Scope class](http://docs.angularjs.org/api/ng.$rootScope.Scope).
* The scope class has methods that control the scope's lifecycle, provide event-propagation facility, and support the template rendering process.
* A new `$scope` was created by the `ng-controller` directive using the `Scope.$new()` method call.
* `$rootScope` instance gets created when a new application