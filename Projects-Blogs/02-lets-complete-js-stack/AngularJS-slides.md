[HTML5 Dev Conf: AngularJS, a Framework for Web Applications](http://www.youtube.com/watch?v=Dlkx6AVOBcQ) ([slides](http://igorminar.github.com/ng-slides/angular-intro/index.html))

  * Is jQuery the wrong way to building apps? No. But jQuery doesn't increase the level of abstraction.
  * Building a web app is a lot more than DOM manipulation. It's a necessary condition, but it's not sufficient. What we want to do is take the DOM manipulation portion, and allow you to express it declaratively in HTML.
  * We allow you to turn HTML into a DSL.
  * (view the page source of the slide deck) It turns out this is an Angular app, and look what we get to do. [...] We get to say `<slide>`. When we went to create a presentation, we created primitives that are useful for this type of application. [...] The point I'm trying to say is that, while it's tempting to think of AngularJS as a way of building web apps, what it actually is underneath is an HTML compiler. It allows you to come up with a syntax that is best suited for building *your* application.

[Rebuilding DoubleClick with AngularJS](http://www.youtube.com/watch?v=oJoAnVRIVQo)

  * Directives are the key mechanism for reusability in AngularJS.
  * Tips for people starting with Angular (1:17:00 in):
    * Scope/Controller separation; "Scope" is really a "ViewModel," there doesn't have to be strictly one per controller
    * Danger of writing monolithic features; put logic in models, controllers are a thin wiring layer
      * (note: see [my `angular` branch of the Boggle project for an example](https://github.com/grockit/boggle/blob/angular/app/assets/javascripts/boggle.coffee), where the `GameController` mostly delegates to other model objects, and only contains the data necessary to bind game state to the DOM)
  * "The Angular Way"
    * jQuery = "I am the controller," reach out to the DOM and push changes
    * Angular = Represent your state in models, set up view bindings declaratively
  * Currently use inheritance for controller hierarchy, in hindsight would not do this again. Push code into models/services/mixins/components.
  * Divorce yourself from traditional jQuery usage ASAP - it has no place in an Angular application (even in directives, the traditional jQuery programming model is usually not correct)
  * A common pattern is services working on concert with directives; services are where you want to share state across controllers, and directives are where you want to manipulate DOM.
