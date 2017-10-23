# What is AngularJS

* AngularJS is not a library, it's a framework that embraces extending HTML into a more expressive and readable format
* AngularJS is a structural framework for dynamic web apps
* A framework that lets you use HTML as your template language and extend HTML's syntax to express your application's components clearly and succinctly
* Angular is an opinionated framework on how a CRUD application should be built

# Use AngularJS to build CRUD application

* Angular was built for the CRUD application in mind. Games and GUI editors are examples of applications with intensive and tricky DOM manipulation. These kinds of apps are different from CRUD apps, and as a result are probably not a good fit for Angular

http://docs.angularjs.org/guide/overview

# Introduction to AngularjS

* Angular is pure client-side technology, written entirely in JavaScript.
* Angular is designed primarily for developing single-page apps.

# Things I Wish I Were Told About Angular.js

* [Angular.js does not force you to use its module system](http://ruoyusun.com/2013/05/25/things-i-wish-i-were-told-about-angular-js.html)
* Understand how Angular modules works before you start
* You need to understand how $scope works
* When You Manipulate DOM in Controller, Write Directives
* And the best part is, your controller does not need to know the existence of directives: communications are achieved through scope sharing and $scope events.
* put control logic in directive controller, and DOM logic in link function; scope sharing is the glue.
* The only unit test that requires some DOM manipulation is directive.