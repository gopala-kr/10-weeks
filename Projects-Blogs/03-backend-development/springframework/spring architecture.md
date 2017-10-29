
### Spring Framework - Architecture

Spring could potentially be a one-stop shop for all our enterprise applications. However, Spring is modular, allowing us to pick and choose which modules are applicable for us, without having to bring in the rest. The following section provides details about all the modules available in Spring Framework.

The Spring Framework provides about 20 modules which can be used based on an application requirement.
<br>

![Spring Framework - Architecture](https://www.tutorialspoint.com/spring/images/spring_architecture.png)

<br>

**Core Container**

The Core Container consists of the Core, Beans, Context, and Expression Language modules the details of which are as follows 

* The Core module provides the fundamental parts of the framework, including the [IoC and Dependency Injection](https://en.wikipedia.org/wiki/Inversion_of_control) features.

* The Bean module provides BeanFactory, which is a sophisticated implementation of the factory pattern.

* The Context module builds on the solid base provided by the Core and Beans modules and it is a medium to access any objects defined and configured. The ApplicationContext interface is the focal point of the Context module.

* The SpEL module provides a powerful expression language for querying and manipulating an object graph at runtime.

**Data Access/Integration**

The Data Access/Integration layer consists of the JDBC, ORM, OXM, JMS and Transaction modules whose detail is as follows

* The JDBC module provides a JDBC-abstraction layer that removes the need for tedious JDBC related coding.

* The ORM module provides integration layers for popular object-relational mapping APIs, including JPA, JDO, Hibernate, and iBatis.

* The OXM module provides an abstraction layer that supports Object/XML mapping implementations for JAXB, Castor, XMLBeans, JiBX and XStream.

* The Java Messaging Service JMS module contains features for producing and consuming messages.

* The Transaction module supports programmatic and declarative transaction management for classes that implement special interfaces and for all your POJOs.

**Web**

The Web layer consists of the Web, Web-MVC, Web-Socket, and Web-Portlet modules the details of which are as follows 

* The Web module provides basic web-oriented integration features such as multipart file-upload functionality and the initialization of the IoC container using servlet listeners and a web-oriented application context.

* The Web-MVC module contains Spring's Model-View-Controller (MVC) implementation for web applications.

* The Web-Socket module provides support for WebSocket-based, two-way communication between the client and the server in web applications.

* The Web-Portlet module provides the MVC implementation to be used in a portlet environment and mirrors the functionality of Web-Servlet module.

There are few other important modules like AOP, Aspects, Instrumentation, Web and Test modules the details of which are as follows −

* The AOP module provides an aspect-oriented programming implementation allowing you to define method-interceptors and pointcuts to cleanly decouple code that implements functionality that should be separated.

* The Aspects module provides integration with AspectJ, which is again a powerful and mature AOP framework.

* The Instrumentation module provides class instrumentation support and class loader implementations to be used in certain application servers.

* The Messaging module provides support for STOMP as the WebSocket sub-protocol to use in applications. It also supports an annotation programming model for routing and processing STOMP messages from WebSocket clients.

* The Test module supports the testing of Spring components with JUnit or TestNG frameworks.

### Dependency Injection (DI)

The technology that Spring is most identified with is the Dependency Injection (DI) flavor of Inversion of Control. The Inversion of Control (IoC) is a general concept, and it can be expressed in many different ways. Dependency Injection is merely one concrete example of Inversion of Control.

When writing a complex Java application, application classes should be as independent as possible of other Java classes to increase the possibility to reuse these classes and to test them independently of other classes while unit testing. Dependency Injection helps in gluing these classes together and at the same time keeping them independent.

What is dependency injection exactly? Let's look at these two words separately. Here the dependency part translates into an association between two classes. For example, class A is dependent of class B. Now, let's look at the second part, injection. All this means is, class B will get injected into class A by the IoC.

Dependency injection can happen in the way of passing parameters to the constructor or by post-construction using setter methods. As Dependency Injection is the heart of Spring Framework, we will explain this concept in a separate chapter with relevant example.

### Aspect Oriented Programming (AOP)

One of the key components of Spring is the Aspect Oriented Programming (AOP) framework. The functions that span multiple points of an application are called cross-cutting concerns and these cross-cutting concerns are conceptually separate from the application's business logic. There are various common good examples of aspects including logging, declarative transactions, security, caching, etc.

The key unit of modularity in OOP is the class, whereas in AOP the unit of modularity is the aspect. DI helps you decouple your application objects from each other, while AOP helps you decouple cross-cutting concerns from the objects that they affect.

The AOP module of Spring Framework provides an aspect-oriented programming implementation allowing you to define method-interceptors and pointcuts to cleanly decouple code that implements functionality that should be separated. We will discuss more about Spring AOP concepts in a separate chapter.
