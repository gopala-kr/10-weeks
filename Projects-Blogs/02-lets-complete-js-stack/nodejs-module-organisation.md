**Module Organization**

Node.js is both a product of its own as well as a service upon which other applications can be built. Because of this, it is useful to consider the design choices made for both in our analysis. Some of the choices made at a basic level in the Node.js architecture affect how applications using Node.js should be developed. Figure 4 shows a diagram depicting the high-level layered structure of Node.js as described in.

![Module Organization](https://delftswa.gitbooks.io/desosa-2017/content/node/images-node/module_organization.jpg)

The Module and Application Ecosystem refers to the collection of all software that was built using Node.js. It is connected to all other layers in the diagram, which signifies that in theory developers of Node.js applications are free to connect to any of Node.js' layers. In practice most applications limit themselves to accessing only the Node.js Core Library.

This Core Library contains a variety of JavaScript files that simplify the development process for Node.js users. It offers a lot of common functionality out of the box, such as cryptography, network connections, event handling, etc. A part of the code in this library is marked as "internal", which hides a part of the API from the end user. The end user can still call these API functions if they wanted to, but since the format of these APIs can change without notice, they are marked as internal to discourage people from doing so.

The Application Binary Interface (commonly referred to as the ABI) is a relatively new part of Node.js. The idea behind the ABI is to provide the end user with a stable API through which they can access the underlying JavaScript engine. At this point that engine is Google's V8, but the ABI allows Node.js to potentially switch to a different engine in the future. Also the ABI ensures that no new version of Node.js is required if changes are made to Google's V8 engine. The Binary Abstraction Layer serves a similar purpose, but it abstracts the ABI even further. On top of that, it also provides abstracted access to other dependencies aside from the JavaScript engine.
