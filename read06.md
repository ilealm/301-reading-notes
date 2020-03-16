# Read: 06 - Node, Express, and APIs

## What Is Node.js?
> Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.

* The V8 engine is the open-source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers.
* It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.
* Node.js is a program we can use to execute JavaScript on our computers. In other words, it’s a JavaScript runtime.
* Node.js has excellent support for modern JavaScript. Means not to worry about compatibility issues — as you would if you were writing JavaScript that would run in different browsers.
* npm is also the world’s largest software registry.
* One of the most important characteristic cases for Node.js: *_running JavaScript on the server_*.
* Node’s execution model causes the server very little overhead.
* Node is particularly suited to building applications that require some form of real-time interaction or collaboration, or for sites involving data streaming. Node.js can also can be used to build cross-platform desktop apps
*  Node.js speaks JSON.

_* npm stands for *_
> Node Package Manager

## Steps to run a simple Node.js
1. In terminal (mac), create a new file hello.js and copy in the following code:
`console.log("Hello, World!");`
1. To run the example, enter the following command:
`node hello.js`

## Installing a Package Globally
`npm install -g jshint`

## Installing a Package Locally
`npm init -y`

## Working with the package.json File
* The node_modules is created by json.
* This directory can be re-created at any time by running npm install from within the project’s root.


## The Node.js Execution Model
> "In very simplistic terms, when you connect to a traditional server, such as Apache, it will spawn a new thread to handle the request. In a language >such as PHP or Ruby, any subsequent I/O operations (for example, interacting with a database) block the execution of your code until the operation has >completed. That is, the server has to wait for the database lookup to complete before it can move on to processing the result. If new requests come in >while this is happening, the server will spawn new threads to deal with them. This is potentially inefficient, as a large number of threads can cause a >system to become sluggish — and, in the worst case, for the site to go down."

[Credit...](https://www.sitepoint.com/an-introduction-to-node-js/)

* Node.js, _* is single-threaded.*_
* It’s also event-driven, which means that everything that happens in Node is in reaction to an event. 

>"everything that happens in Node is in reaction to an event. For >example, when a new request comes in (one kind of event) the server >will start processing it. If it then encounters a blocking I/O >operation, instead of waiting for this to complete, it will register ?>a callback before continuing to process the next event. When the I/O >operation has finished (another kind of event), the server will >execute the callback and continue working on the original request."