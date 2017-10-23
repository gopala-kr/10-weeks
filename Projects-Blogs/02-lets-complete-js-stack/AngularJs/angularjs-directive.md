* Directive extend HTML with custom attributes and elements. We use Directive to apply special behaviour to attributes or elements in the HTML.

# Notes on creating directives

* Use the module.directive API to register a directive
* The `factory function` should return an object
* The `factory function` is invoked only once when the `$compiler` matches the directive for the first time.
* Perform any initialization work on `factory function`
* Prefer using the definition object over returning a function
* Prefix your own directives with 2 or 3 words, and avoid prefix your own directives with `ng-` or they might conflict with directives included in a future version of Angular.
* Use the `templateUrl` option if the size of the template relatively big.

# Notes on directive restrict option

* When you create a directive, it is restricted to attribute only by default.
* Use an element restrict option (E) when you are creating a component that is in control of the template. The common case for this is when you are creating a Domain-Specific Language for parts of your template.
* Use an attribute restrict option (A) when you are decorating an existing element with new functionality.
* Notes on directive scope option

# Notes on directive scope option

* Use the scope option to create isolate scopes when making components that you want to reuse throughout your app

# Notes on manupulating the DOM

* Directives that want to modify the DOM typically use the link option.
* When a DOM node that has been compiled with AngularJS's compiler is destroyed, it emits a `$destroy` event.

# Notes on creating directives that communicate

* use `controller` option when you want to expose an API to other directives. Otherwise use link.
* When other directives try to communicate wit other directives via exposed API, they will received controller as their fourth argument `link` function. For example `function (scope, element, attrs, myTabsCtrl) { ... }`