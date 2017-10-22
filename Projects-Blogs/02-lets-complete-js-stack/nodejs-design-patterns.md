### Design Patterns

Some of the design patterns used in Node.js.

**Singleton Pattern:** The singleton pattern limits the number of instances of a particular object to just one. Node.js uses module caching to implement the Singleton pattern and caches a module after the first time it is loaded. Every subsequent call to a module using require(<module_name>) returns the same instance of the cached module. In that way, these modules can thus be thought of as singletons.

**Dependency Injection Container:** Application modules built on Node.js typically use a backbone object that acts as a dependency injection container. Services such as logging and database access which are required throughout almost any application built on Node.js are attached to the backbone object and this object in turn can be used by the modules that require these services. In this way, modules have their dependencies injected from the outside through the use of the backbone object. The module is thus isolated from any changes in its dependencies.

**Event-Driven Programming:** In an event-driven program the flow of the application is the result of events that are fired or states that are changed. In general there is one single, global mechanism that listens for such events and whenever one is fired it will call the corresponding callback function. In Node.js this mechanism is called the Event Loop, which we will discuss in great detail in the Functional View and the Performance and Scalability Perspective.
