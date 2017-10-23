* When Angular starts your application, it parses and processes this new markup from the template using the so called **compiler**. The loaded, transformed, and rendered DOM is then called the view. So, the view and template are really a different things. The template is HTML with additional markup, and the view is the output of compile process.
* AngularJS framework rely on the HTML for its template syntax.
* It depends on the browser to parse the template's text.
* After browser is done transforming the markup's text to the DOM tree, AngularJS kicks in and traverses the parsed DOM structure.
* We should ensure that the markup written on the template represents valid HTML.
* AngularJS promotes a declarative approach to UI construction.
* Templates are focused on describing a desired effect
* AngularJS heavily promotes declarative style of programming for templates and impervative one for the JavaScript code (controllers and business logic)
* Directives in AngularJS templates declaratively express the desired effect, so we freed from providing step-by-step instructions on how to change individual properties of DOM elements (as is often the case in applications based on jQuery).
* As a rule of thumb, one should never manipulate the DOM elements in AngularJS controllers. Getting a reference to a DOM element in a controller and manipulating element's properties indicate imperative approach to UI - something that goes againts AngularJS way of building UIs.
* Expressions access the variables and functions from the scope. An expression in a template is a JavaScript-like code snippet that allows to read and write variables that live in a scope.