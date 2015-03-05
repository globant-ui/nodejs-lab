# NodeJS Lab
*This document is a Work In Progress.*

## Table of Content
1. Introduction to NodeJS
  1. CommonJS Modules
  2. Intro to npm
  3. Globals, Process and Buffer
2. Asynchronous Patterns
  1. Event loop
  2. Async functions
  3. Control Flow and Exception Handling
3. Communication 
  1. EventEmitter
  2. Cluster
  3. Streams
  4. Socket.io
4. RESTful API
  1. HTTP (methods, headers)
  2. REST principles
5. Express
  1. Starting with Express
  2. Templating
6. Data Repositories
	1. MongoDB
  		1. Intro to MongoDB
  		2. Mongoose
	2. Reddis
7. Debugging and Profiling
8. Others
  1. Popular modules
  2. Links

## Introduction to NodeJS ##
In this section, you will learn the basics of NodeJS. From how NodeJS application organize their source code, to how application dependencies are handled by NPM, and which global objects are provided by default.

### CommonJS Modules ###
NodeJS application organize their code into modules. There are a couple of standards on how to write a module in JavaScript. By convention, NodeJS has decided to use the CommonJS Module Specification.

* [Module 1.0 - CommonJS Specification](http://www.commonjs.org/specs/modules/1.0/ "Module 1.0 - CommonJS Specification")
* [A complete explanation of the 3 most used module definitions](http://addyosmani.com/writing-modular-js/ "Modules in JavaScript")
### Intro to NPM ###
NPM is a package manager for JavaScript, and is the default for Node.js. NPM makes it easy for JavaScript developers to share and reuse code, and it makes it easy to update the code that you're sharing.

* [What is NPM? Short explanation video](https://www.youtube.com/watch?v=pa4dc480Apo)
* [Installing node and updating NPM](https://docs.npmjs.com/getting-started/installing-node)
* [Create and publish modules to NPM](https://quickleft.com/blog/creating-and-publishing-a-node-js-module/)

### Globals, Process and Buffer###
As we have learnt, NodeJS's module system discourages the use of globals. However, it provides a few important globals that we can use. This section list the most important ones.

- [Buffer](http://nodejs.org/api/buffer.html): To handle binary data, NodeJS provides the global Buffer object. Buffer instances represent memory allocated independently of V8's heap. [Here](http://www.w3resource.com/node.js/nodejs-buffer.php) is an example of how to use buffers.	 
- [Global](http://nodejs.org/api/globals.html): This module represent the global scope. It is not a good practice to use this global. When you define a global variable in a browser, its scope is the global one, but in node is different: you define a variable inside a module without "var" and its scope is the module itself.
- [Process](http://nodejs.org/api/process.html): Process is a node module that can be accessed anywhere without the need to be required. It exposes process manipulation such as signalling, exiting, the process id (pid), and more.
## Asynchronous Patterns ##
This section introduces NodeJS's event loop, and different patterns to deal with asynchronous control-flow.

### Event loop ###
- [Understanding Node Event Loop](https://nodesource.com/blog/understanding-the-nodejs-event-loop)
- [Why Single threaded and Event Loop](http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/)

### Async functions ###
- [Callback Hell](http://callbackhell.com/)
- [Using async functions in practice](http://www.sebastianseilund.com/nodejs-async-in-practice)
- [Async iteration patterns](http://metaduck.com/01-asynchronous-iteration-patterns.html)

### Control Flow and Exception Handling ###
- [Solutions to control the flow](http://book.mixu.net/node/ch7.html)
- [Managing the asynchronous nature of NodeJS](http://code.tutsplus.com/tutorials/managing-the-asynchronous-nature-of-nodejs--net-36183)
- [The Async library](https://github.com/caolan/async)
- [Error Handling in NodeJS](https://www.joyent.com/developers/node/design/errors)

## Communication ##
This section introduces the use of events, clusters, and streams in NodeJS.

### EventEmitter ###
Many objects in Node emit events: a net.Server emits an event each time a peer connects to it, a fs.readStream emits an event when the file is opened. All objects which emit events are instances of events.EventEmitter.
[http://nodejs.org/api/events.html](http://nodejs.org/api/events.html)

### Cluster ###
A single instance of Node runs in a single thread. To take advantage of multi-core systems the user will sometimes want to launch a cluster of Node processes to handle the load. [http://nodejs.org/api/cluster.html](http://nodejs.org/api/cluster.html)

### Streams ###
A stream is an abstract interface implemented by various objects in Node. Streams are pipes that let you easily read data from a source and pipe it to a destination. [http://nodejs.org/api/stream.html](http://nodejs.org/api/stream.html): 

### Socket.io ###
 Socket.IO enables real-time bidirectional event-based communication.
It works on every platform, browser or device, focusing equally on reliability and speed.


* [Engine.IO: the realtime engine](https://github.com/Automattic/engine.io)
* [Socket.IO](http://socket.io/docs/)
* [Migration from 0.9 to 1.0](http://socket.io/docs/migrating-from-0-9/)
* [Example application](https://github.com/Automattic/socket.io/tree/master/examples/chat)

## RESTful API ##
This section introduces RESTful principles, along with the HTTP protocol basics.

### HTTP (methods, headers) ###
- [RFC 2616: HTTP Methods](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html)
- [RFC 2616: HTTP Header fields](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html)
- [How to make a simple HTTP request in Node](http://davidwalsh.name/nodejs-http-request "HTTP request")
- [Node API: HTTP documentation](http://nodejs.org/api/http.html)


### REST principles ###
- [What is REST? Brief introduction video](https://www.youtube.com/watch?v=7YcW25PHnAA)
- [REST Principles](http://en.wikipedia.org/wiki/Representational_state_transfer#Architectural_constraints)
## Express ##
Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

### Starting with Express ###
- [Generating the application](http://expressjs.com/starter/generator.html)
- [Example application: Hello World!](http://expressjs.com/starter/hello-world.html)
- [Basic routing using Express](http://expressjs.com/guide/routing.html)
- [Using middlewares](http://expressjs.com/guide/using-middleware.html)
- [Migrating from 3.x to 4.x](https://github.com/strongloop/express/wiki/Migrating-from-3.x-to-4.x)
- [Express Module Repository](https://github.com/strongloop/express)

### Templating ###
- [Configuring template engines](http://expressjs-book.com/forums/topic/how-to-use-alternative-non-jade-template-engines-with-express/)
- [Template engine consolidation library](https://www.npmjs.com/package/consolidate)

## Data Repositories ##
### MongoDB ###
MongoDB is an open source document-oriented database that provides high availability, high performance and automatic scaling.

- [Official documentation](http://docs.mongodb.org/manual/)
- [MongoDB architecture: Data Model, Query Model and Management](http://www.mongodb.com/mongodb-architecture)
- [Performance best practices for MongoDB](http://info.mongodb.com/rs/mongodb/images/MongoDB-Performance-Best-Practices.pdf)
- [Tutorial: creating an API with Node and MongoDB](http://adrianmejia.com/blog/2014/10/01/creating-a-restful-api-tutorial-with-nodejs-and-mongodb/)

### Redis ###
Redis is an open source, BSD licensed, advanced key-value cache and store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets, sorted sets, bitmaps and hyperloglogs.

* [Introduction to Redis.io](http://en.wikipedia.org/wiki/Redis)
* [High performance Redis Config](http://www.symantec.com/connect/blogs/configuring-redis-high-availability)
* [Redis repository in Github](https://github.com/antirez/redis)

## Debugging and Profiling ##
In this section, you will learn how to debug, and profile a NodeJS application.

- [How to debug using Node inspector](https://vimeo.com/77870960)
- [Debugging apps using WebStorm](https://www.jetbrains.com/webstorm/help/running-and-debugging-node-js.html)
- [Profiling NodeJS applications](http://www.willvillanueva.com/the-node-js-profiling-guide-that-hasnt-existed-profiling-node-js-applications-part-1/)
- [CPU Profiling](http://www.clock.co.uk/blog/easy-cpu-profiling-in-node-js)

## Others ##
### Popular modules ###
This section presents relevant modules written by the community, which are proven, and useful to write any NodeJS application. In addition, we provide further documentation to for you to explore.

- **Express Framework**: Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. [https://www.npmjs.com/package/express](https://www.npmjs.com/package/express "Express Framework")

- **Async Library**: Async is a utility module which provides straight-forward, powerful functions for working with asynchronous JavaScript. [https://www.npmjs.com/package/async](https://www.npmjs.com/package/async "Async Library")

- **Request**: Request is a simplified HTTP request client, designed to be the simplest way possible to make HTTP calls. It also supports HTTPS. [https://www.npmjs.com/package/request](https://www.npmjs.com/package/request "Request Library")

- **Socket.io**: Socket.IO is used to create realtime web applications. It enables realtime, bi-directional communication between web clients and server. [https://www.npmjs.com/package/socket.io](https://www.npmjs.com/package/socket.io "Socket.io")

- **Lodash**: Lodash is a toolkit of Javascript functions that provides clean, performant methods for manipulating objects and collections. [https://www.npmjs.com/package/lodash](https://www.npmjs.com/package/lodash "Lodash Library")

- **Mocha**: Mocha is a feature-rich JavaScript test framework running on node.js and the browser, making asynchronous testing flexible and simple. [https://www.npmjs.com/package/mocha](https://www.npmjs.com/package/mocha "Mocha Library")

- **Mongoose**: Mongoose is a MongoDB object modeling tool designed to work in an asynchronous environment. If you use MongoDB, this is a must. [https://www.npmjs.com/package/mongoose](https://www.npmjs.com/package/mongoose "Mongoose")

- **Underscore**: Underscore.js is a utility library that provides support for the usual functional suspects without extending any core JavaScript objects. [https://www.npmjs.com/package/underscore](https://www.npmjs.com/package/underscore "Underscore Utility")

- **Redis**: Redis is an open source, BSD licensed, advanced key-value cache and store. You can store keys in memory with optional durability. [https://www.npmjs.com/package/redis](https://www.npmjs.com/package/redis "Redis")

- **Jade**: Jade is a high performance template engine heavily influenced by Haml and implemented with JavaScript for node and browsers. [https://www.npmjs.com/package/jade](https://www.npmjs.com/package/jade "Jade Library")

- **Moment**: A lightweight JavaScript date library for parsing, validating, manipulating, and formatting dates. It was designed to work both in the browser and in Node.JS. [https://www.npmjs.com/package/moment](https://www.npmjs.com/package/moment "MomentJS Library")

- **Passport**: Passport is an authentication middleware. It's sole purpose is to authenticate requests through an extensible set of plugins known as strategies.  [https://www.npmjs.com/package/passport](https://www.npmjs.com/package/passport "Passport Library")

- **Nodemailer**: Nodemailer is an easy to use module to send e-mails with Node.JS (using SMTP or sendmail or Amazon SES) and is unicode friendly. [https://www.npmjs.com/package/nodemailer](https://www.npmjs.com/package/nodemailer "Nodemailer")

- **Q**: A JavaScript library for promises (CommonJS/Promises/A,B,D). [https://www.npmjs.com/package/q](https://www.npmjs.com/package/q "Q Library")

- **Mongodb**: A node.js driver for MongoDB [https://www.npmjs.com/package/mongodb](https://www.npmjs.com/package/mongodb "MongoDB")

- **MySQL**: A node.js driver for MySQL. [https://www.npmjs.com/package/mysql](https://www.npmjs.com/package/mysql "MySQL Driver")

- **Nodemon**: Nodemon is a simple monitor script for using during development of a node.js app. [https://www.npmjs.com/package/nodemon](https://www.npmjs.com/package/nodemon "Nodemon Library")

- **Hapi**: Hapi is a simple to use framework with support for input validation, caching, authentication, and other essential facilities for building web and services applications. [https://www.npmjs.com/package/hapi](https://www.npmjs.com/package/hapi "Hapi Framework")

### Links ###
1. Official documentation: [http://nodejs.org/api/](http://nodejs.org/api/ "NodeJS API docs")
2. IO.js Official Documentation: [https://iojs.org/api/](https://iojs.org/api/ "io.js docs")
3. Comparison between NodeJS and Java: [http://www.infoworld.com/article/2883328/java/java-vs-nodejs-an-epic-battle-for-developer-mindshare.html](http://www.infoworld.com/article/2883328/java/java-vs-nodejs-an-epic-battle-for-developer-mindshare.html)
4. 6 things you should know about JavaScript: An interesting article about Node.js [http://www.javaworld.com/article/2079190/scripting-jvm-languages/6-things-you-should-know-about-node-js.html](http://www.javaworld.com/article/2079190/scripting-jvm-languages/6-things-you-should-know-about-node-js.html)
5. Tips to make your app faster: [http://www.sitepoint.com/10-tips-make-node-js-web-app-faster/](http://www.sitepoint.com/10-tips-make-node-js-web-app-faster/)