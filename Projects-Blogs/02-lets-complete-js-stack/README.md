

## lets complete js stack : nodejs, expressjs, meteorjs



This week I got some time for nodejs and related framework expressjs and meteorjs.

*********************************
 | Hacker News       | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [nodejs](https://hn.algolia.com/?query=nodejs&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [nodejs](https://medium.com/search?q=nodejs)  | [nodejs](https://www.reddit.com/r/node/)  | [nodejs](https://www.quora.com/topic/Node-js)  |  [nodejs](https://stackoverflow.com/search?q=nodejs)    | [nodejs](https://github.com/sindresorhus/awesome-nodejs)  | [nodejs](https://www.lynda.com/Node-js-training-tutorials/1283-0.html)  |[nodejs](https://nodejs.org/en/)  |
|  [expressjs](https://hn.algolia.com/?query=expressjs&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [expressjs](https://medium.com/tag/expressjs)  | [expressjs](https://www.reddit.com/r/node/)  | [expressjs](https://www.quora.com/topic/Express-Node-js-web-framework)  |   [expressjs](https://stackoverflow.com/search?q=expressjs)   | [expressjs](https://github.com/sindresorhus/awesome-nodejs)  | [expressjs](https://www.lynda.com/Express-js-training-tutorials/2086-0.html)  |[expressjs](https://expressjs.com/)  |
|  [meteorjs](https://hn.algolia.com/?query=meteorjs&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [meteorjs](https://medium.com/tag/meteor-framework/latest)  | [meteorjs](https://www.reddit.com/r/Meteor/)  | [meteorjs](https://www.quora.com/topic/Meteor-Javascript-platform)  |   [meteorjs](https://stackoverflow.com/search?q=meteor)  | [meteorjs](https://github.com/Urigo/awesome-meteor)  | [meteorjs](https://www.lynda.com/Meteor-tutorials/11118-0.html)  |[meteorjs](https://www.meteor.com/)  |
****************************
*****************************

Before getting into nodejs, lets learn about javascript history and basics of how exactly it works; 
******************

![js-history](http://adrianmejia.com/images/history-javascript-evolution-es6.png)

******************************
> ## A Short History of JavaScript

> JavaScript, not to be confused with Java, was created in 10 days in May 1995 by Brendan Eich, then working at Netscape and now of Mozilla. JavaScript was not always known as JavaScript: the original name was Mocha, a name chosen by Marc Andreessen, founder of Netscape. In September of 1995 the name was changed to LiveScript, then in December of the same year, upon receiving a trademark license from Sun, the name JavaScript was adopted. This was somewhat of a marketing move at the time, with Java being very popular around then.

> In 1996 - 1997 JavaScript was taken to ECMA to carve out a standard specification, which other browser vendors could then implement based on the work done at Netscape. The work done over this period of time eventually led to the official release of ECMA-262 Ed.1: ECMAScript is the name of the official standard, with JavaScript being the most well known of the implementations. ActionScript 3 is another well-known implementation of ECMAScript, with extensions.

> The standards process continued in cycles, with releases of ECMAScript 2 in 1998 and ECMAScript 3 in 1999, which is the baseline for modern day JavaScript. The "JS2" or "original ES4" work led by Waldemar Horwat (then of Netscape, now at Google) started in 2000 and at first, Microsoft seemed to participate and even implemented some of the proposals in their JScript.net language.

> Over time it was clear though that Microsoft had no intention of cooperating or implementing proper JS in IE, even though they had no competing proposal and they had a partial (and diverged at this point) implementation on the .NET server side. So by 2003 the JS2/original-ES4 work was mothballed.

> The next major event was in 2005, with two major happenings in JavaScript’s history. First, Brendan Eich and Mozilla rejoined Ecma as a not-for-profit member and work started on E4X, ECMA-357, which came from ex-Microsoft employees at BEA (originally acquired as Crossgain). This led to working jointly with Macromedia, who were implementing E4X in ActionScript 3(ActionScript 3 was a fork of Waldemar's JS2/original-ES4 work).

> So, along with Macromedia (later acquired by Adobe), work restarted on ECMAScript 4 with the goal of standardizing what was in AS3 and implementing it in SpiderMonkey. To this end, Adobe released the "AVM2", code named Tamarin, as an open source project. But Tamarin and AS3 were too different from web JavaScript to converge, as was realized by the parties in 2007 and 2008.

> Alas, there was still turmoil between the various players; Doug Crockford — then at Yahoo! — joined forces with Microsoft in 2007 to oppose ECMAScript 4, which led to the ECMAScript 3.1 effort.

> While all of this was happening the open source and developer communities set to work to revolutionize what could be done with JavaScript. This community effort was sparked in 2005 when Jesse James Garrett released a white paper in which he coined the term Ajax, and described a set of technologies, of which JavaScript was the backbone, used to create web applications where data can be loaded in the background, avoiding the need for full page reloads and resulting in more dynamic applications. This resulted in a renaissance period of JavaScript usage spearheaded by open source libraries and the communities that formed around them, with libraries such as Prototype, jQuery, Dojo and Mootools and others being released.

> In July of 2008 the disparate parties on either side came together in Oslo. This led to the eventual agreement in early 2009 to rename ECMAScript 3.1 to ECMAScript 5 and drive the language forward using an agenda that is known as Harmony.

> All of this then brings us to today, with JavaScript entering a completely new and exciting cycle of evolution, innovation and standardisation, with new developments such as the Nodejs platform, allowing us to use JavaScript on the server-side, and HTML5 APIs to control user media, open up web sockets for always-on communication, get data on geographical location and device features such as accelerometer, and more. It is an exciting time to learn JavaScript. (Source: W3Schools)

> For more on JS:
> * [js-history](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/js-history.md) 
> * [js-memory-management](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/js-memory-management.md) 
> * [js-engine-overview](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/js-engine-overview.md) 
> * [event-loop-and-asynchronuous-programmming](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/js-event%20loop%20and%20the%20rise%20of%20Async%20programming.md) 
> * [google-v8-enine](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/js-inside-the-V8-engine.md)


********************


## Nodejs

In simple words, Node.js is a very powerful JavaScript-based framework/platform for running JavaScript applications outside the browser built on Google Chrome's
JavaScript V8 Engine. It is used to develop I/O intensive web applications like video
streaming sites, single-page applications, and server-side web applications. Node.js is open
source, completely free, and used by thousands of developers around the world.

Many of the basic modules of Node.js are written in JavaScript. Node.js is mostly used to run real-time server applications.

The definition given by its official documentation is as follows:

>Node.js is a platform built on Chrome's JavaScript runtime for easily building fast and scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.?

Node.js also provides a rich library of various JavaScript modules to simplify the development of web applications.

> Node.js = Runtime Environment + JavaScript Library  

![Different parts of Node.js](https://www.javatpoint.com/js/nodejs/images/what-is-nodejs.png)

The reason why Node.js was originally started is because Ryan Dahl was fed up with the disconnect between the client and the web server. Each time the client wanted to be updated with new information it had to query the web server (for example, to keep track of progress of a file upload). This had been a long-standing problem in the field of web development, but most developers just decided to deal with it. Node.js was the first real attempt at solving this problem at the root by enabling real-time communication between the client and the server. It was immediately well received, as shown by the enthusiastic reaction of the audience during the original Node.js launch presentation.

> Its worth spending 1 hour time on [Ryan Dahl Node.js launch presentation](https://www.youtube.com/watch?v=jo_B4LTHi3I) before start learning it.

The total amount of active contributors to the project itself increased each year to a record amount of about 480 contributors at the end of 2016. The number of downloads also continues to grow, with the total amount of downloads averaging at over 484,121 avg / day. (source : https://nodesource.com/node-by-numbers)

Because of the immense popularity of Node.js I wanted to study its architecture and how it is used to achieve some of the unique functionalities Node.js has to offer. My initial commitment was to complete it in one/two days. after diving in came to know that node itself takes a week.

***********************************

> **Short history of nodejs**

> Node.js was created by Ryan Dahl and other developers working at Joyent in 2009. In 2011, the Node Package Manager, called NPM was released and it allowed for the sharing of open-source libraries. As the Node community grew, some conflicts started to emerge about the management of Node releases. The users wanted a project governed by the open-source community rather than a corporation. They also wanted to be able to incorporate the latest language and API features faster. So in December 2014, io.js created a fork of the Node.js project and went onto release several versions of io.js.

> Then in February of 2015, it was announced that a neutral Node.js foundation would be formed. A promise that was fulfilled in June of 2015 when Node.js and io.js voted to work together under the new Node.js foundation. The Node.js foundation is made up of several large companies including IBM, Microsoft, PayPal, Groupon and, of course, Joyent. It's referred to as a collaborative project by the Linux foundation. Officially on September 14, 2015, the Node.js foundation announced that the Node.js and io.js would be combined in a single code base and released as Node.js version 4.0.

> Included in the new release are a ton of new ES6 features and a plan for a regular release cycle. From the start of the Node.js project, a common refrain was that all versions of Node.js would be 0 releases, .08, .010, .012 until the project could release a stable version 1.0 with no breaking changes. Well, with the release of Node.js version 4.0, the much-awaited version 1.0 never happened. But now the community is united with the official Node release at version 4.0. and the present version is 6.11.4.

**********************************

## How Nodejs Works(analogy)

les take a look into how Node.js works and why it is so fast in simple words by taking an example of two restaurants(a popular example). The first restaurant is Apache Steaks and Chops. It is a big, nice, fancy restaurant. In this restaurant, every new guest represents a new user, and making an order is like making a request. If I place an order for a salad, the manager will need to hire a new waiter to take care of me. In this restaurant, our waiter represents a thread. We are going to have our own waiter, our own thread, and they will handle all of our orders. This is similar to how Apache works.

* Every request is single-threaded. After placing the order, the waiter will take the order to the kitchen and give it to the chef. And now the waiter just waits. He won't do anything else until the chef is finished making the food. I would like to order a glass of water, but I can't order anything until the chef finishes making that salad. 
* The chef is blocking me from being able to simply order a glass of water. In this analogy, the chef represents the file system or a data store. In Apache, the single thread waits for the file system to finish reading files before it can do anything else.

* We refer to this as blocking. Finally, my salad is ready. My waiter brings me the food. I can order my glass of water, and my waiter also brings me that, too. My request has been served. And now the manager is firing my waiter because they are not needed anymore. Now, when this restaurant gets busy for dinner service, every guest has their own waiter, which is pretty nice. That is pretty good service, but the waiters are mostly hanging around the kitchen and waiting for the chef to make the food. If this restaurant gets really popular, it requires a lot of space to expand because more guests means more waiters.

* Now, let's take a look at this other cafe, Chez Node. At this cafe, there is only one waiter because Node.js is single-threaded. Here, we can order some crepes. We can see that our waiter places the order for the food, then moves on to take an order from another new table. Hmm, this single thread services all of the restaurant guests. That is pretty cool. When my crepes are ready, the chef rings a bell, and our waiter goes and gets the crepes and delivers them to me. He then proceeds to take another order from a new table. When their food is ready, the waiter will bring it to them as soon as he can.

* We can say that this waiter behaves asynchronously. Everything this waiter needs to do represents a new event, a new table, placing orders, delivering orders. These are all events, and they will get handled in the order that they are raised. Our waiter does not wait. There is no blocking. Our single waiter is busy, busy, busy, but he is killing it because he can multitask. This is what it means when we say nonblocking, event-driven IO. We have a single thread that will respond to events in the order that they are raised.

* This thread behaves asynchronously because it does not have to wait for resources to finish doing what they're doing before our thread can do anything else. If this cafe gets popular, we can simply franchise it. Chez Node can easily be expanded by simply duplicating or forking the restaurant into a neighboring space. And this is precisely how we host Node.js applications in the cloud. Now, remember, Node.js is single-threaded. All of the users are sharing the same thread. Events are raised and recorded in an event queue and then handled in the order that they were raised.

Node.js is asynchronous, which means that it can do more than one thing at a time. This ability to multitask is what makes Node.js so fast and one of the reasons so many developers are building their web applications with Node.js.

****************************

### System scope(**Where to Use Node.js?**)

According to their own website, Node.js was designed to build scalable network applications. Node.js is mainly meant to provide developers with the foundations for common server-side functionalities, for example:

* Computer networking
* I/O bound Applications
* Data Streaming Applications
* Data Intensive Real-time Applications (DIRT)
* JSON APIs based Applications
* Single Page Applications

Node.js is very lightweight and many higher-level functionalities are intentionally relegated to the many packages that are offered through its package ecosystem (called npm), which provides access to the world's largest collection of open source libraries and frameworks.

There are different entities that are related to the actual development of Node.js, such as programming languages and testing.

**Programming languages:** Node.js is almost entirely written in JavaScript. It uses Google's V8 engine to execute all the JavaScript code, but since this engine is itself written in C++, some parts of Node.js's codebase that interact directly with this engine are also written in C++. Finally, Python is used to run many of the automated tests for Node.js.

**Dependencies:** There are a number of libraries or products that Node.js explicitly depends upon. Since Node.js was meant to be lightweight it offers only the most basic necessities for a product of its kind out of the box and thus, it does not have too many dependencies. Instead, it relies on the wide variety of additional plugins and libraries offered through npm, which can be used to extend the functionality of a Node.js application with many standardized solutions to common problems.

![nodejs](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs_architecture.JPG)
<ul>
                                                                <li><a href="https://github.com/libuv/libuv" target="_blank">libuv</a>: Node.js is asynchronous and libuv provides a consistent interface for common asynchronous tasks across all supported platforms.</li>
                                                                <li><a href="https://github.com/c-ares/c-ares" target="_blank">c-ares</a>: a library for asynchronous DNS requests.</li>
                                                                <li><a href="https://github.com/openssl/openssl" target="_blank">openssl</a>: a library of cryptographic functions for security purposes.</li>
                                                                <li><a href="https://github.com/nodejs/http-parser" target="_blank">http parser</a>: parses HTTP requests and responses.</li>
                                                                <li><a href="https://v8docs.nodesource.com/" target="_blank">v8</a>: the Javascript engine used by Node.js to run all of its JavaScript code.</li>
                                                                <li><a href="https://github.com/madler/zlib" target="_blank">zlib</a>: a library used for (de)compression.</li>
                                                            </ul>
                                                            <p><strong>Tools</strong></p>
                                                            <p>In addition to the dependencies mentioned above, Node.js makes use of a couple of additional tools. These are not dependencies in the sense that Node.js cannot work without them, but can be thought of as additional features that enrich the Node.js experience.</p>
                                                            <ul>
                                                                <li><a href="https://docs.npmjs.com/" target="_blank">npm</a>: the package manager of Node.js that offers access to a multitude of open source libraries.</li>
                                                                <li><a href="https://github.com/nodejs/node-gyp" target="_blank">gyp</a>: a build system to build those parts of Node.js and its dependencies that require compilation.</li>
                                                                <li><a href="https://github.com/google/googletest" target="_blank">gtest</a>: a unit testing suite for C and C++ code.</li>
                                                            </ul>
                                                            <p><strong>Competitors</strong></p>
                                                            <p>Node.js is of course not the only platform that provides server-side functionalities. The following is a list of competitors that provide in some way the same functionalities that Node.js provides:</p>
                                                            <ul>
                                                                <li><a href="http://php.net/" target="_blank">PHP</a></li>
                                                                <li><a href="https://golang.org/" target="_blank">Golang</a></li>
                                                                <li><a href="http://vertx.io/" target="_blank">Vert.x</a></li>
                                                                <li><a href="http://projectreactor.io/" target="_blank">Reactor project</a></li>
                                                                <li><a href="https://celluloid.io/" target="_blank">Celluloid-io</a></li>
                                                                <li><a href="http://reactphp.org/" target="_blank">Reactphp</a></li>
                                                                <li><a href="http://cyclone.io/" target="_blank">Cyclone.io</a></li>
                                                            </ul>
                                                            <h3 id="users">Users</h3>
                                                            <p>The users of Node.js can be divided into two subcategories. The individual community and enterprise.</p>
                                                            <p><strong>Individual community</strong></p>
                                                            <p>The individual community are the types of users that uses Node.js as hobby or for research. They do not intend to make money by using Node.js. Such users are developers and universities.</p>
                                                            <p><strong>Enterprise</strong></p>
                                                            <p>Enterprise are the users who do use Node.js as a tool in their company to help improve their product. Some major companies that use Node.js commercially are </p>
                                                            <ul>
                                                                <li>Netflix</li>
                                                                <li>PayPal</li>
                                                                <li>Uber</li>
                                                                <li>IBM</li>
                                                                <li>Microsoft</li>
                                                            </ul>
                                                            <h3 id="feedback--developers">Feedback &amp; Developers</h3>
                                                            <p>For real-time discussion about Node.js development there is the #node.js IRC channel on the irc.freenode.net server. For general communication to all people working <em>with</em> Node.js and not just <em>on</em> Node.js, they also have a number of communication channels:</p>
                                                            <ul>
                                                                <li>The official <a href="https://twitter.com/nodejs" target="_blank">Node Twitter account</a> through which they keep their followers up to date. </li>
                                                                <li>A weekly mailing list called Node Weekly, detailing the latest events within the Node.js community. </li>
                                                                <li>NodeUp, a podcast that covers the latest Node.js-related news.</li>
                                                            </ul>
                                                            <p>Feedback and help can be found on various platforms such as StackOverflow, GitHub and Google Groups, with all three platforms having an active community for Node.js. </p>
                                                            <p><strong>Version control &amp; Issue tracking</strong></p>
                                                            <p>Node.js is actively being developed on <a href="https://github.com/" target="_blank">GitHub</a> using Git as its version control system. The same system is also used to track issues, report bugs and discuss features.</p>
                                                            
                                                            
                                                           
***********************************************


## Nodejs Development View

The Development View details how the architecture supports the software development process and which development guidelines are to be taken into account by all developers. Development views communicate the aspects of the architecture of interest to those stakeholders involved in building, testing, maintaining, and enhancing the system.

* [nodejs-module-organization](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs-module-organisation.md)
* [nodejs-features](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs-features.md)
* [nodejs-architecture-and-working](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs-architecture.md)
* [nodejs-package-management-npm](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs-package-management-npm.md)
* [nodejs-design-patterns](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/nodejs-design-patterns.md)
                                                                               
*****************************
                                                                                
## Expressjs

Express is a Node.js web application framework that provides a robust
set of features to develop web and mobile applications. It facilitates the rapid development
of Node-based Web applications. It is designed for building web applications and APIs.Following are some of the core features of Express
framework:
* Allows to set up middlewares to respond to HTTP Requests.
* Defines a routing table which is used to perform different actions based on HTTP
Method and URL.
* Allows to dynamically render HTML Pages based on passing arguments to
templates.

While installing we should install the following
important modules along with express:
* body-parser - This is a node.js middleware for handling JSON, Raw, Text and URL
encoded form data.
* cookie-parser - Parse Cookie header and populate req.cookies with an object
keyed by the cookie names.
* multer - This is a node.js middleware for handling multipart/form-data


## Meteorjs

Meteor, or MeteorJS, is a free and open-source full Stack web application framework written using Node.js that has the front-end and back-end components to build a real-time applications. Meteor allows for rapid prototyping and produces cross-platform (Android, iOS, Web) code. It integrates with MongoDB and uses the Distributed Data Protocol and a publish–subscribe pattern to automatically propagate data changes to clients without requiring the developer to write any synchronization code. On the client, Meteor can be used with its own Blaze templating engine, as well as with the Angular framework or React library.

Official doc says:

> Meteor is a full-stack JavaScript platform for developing modern web and mobile applications. Meteor includes a key set of technologies for building connected-client reactive applications, a build tool, and a curated set of packages from the Node.js and general JavaScript community.
> * Meteor allows you to develop in one language, JavaScript, in all environments: application server, web browser, and mobile device.
> * Meteor uses data on the wire, meaning the server sends data, not HTML, and the client renders it.
> * Meteor embraces the ecosystem, bringing the best parts of the extremely active JavaScript community to you in a careful and considered way.
> * Meteor provides full stack reactivity, allowing your UI to seamlessly reflect the true state of the world with minimal development effort.

This [presentation](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/02-lets-complete-js-stack/Meteor_intro.pptx) gives basic overview on  meteor architecture. 


## Next steps:

Angularjs & vuejs


********************
                                                                                      
