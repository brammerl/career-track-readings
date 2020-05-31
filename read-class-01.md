1. Why would you want to run JavaScript code outside of a browser?
- It seems you want to run javascript code outside of a browser so that an user cannot access it. When you run it inside of the browser, you're interacting with the UI wich can also affect the way the user interacts with your app. Source (https://www.quora.com/What-exactly-does-running-JavaScript-inside-a-browser-and-outside-of-a-browser-mean)
2. What is the difference between a module and a package?
- A package contains subpackages and modules. Modules are a way for programmers to break up their code so that it is easier to organize and sort through. Source (https://data-flair.training/blogs/python-modules-vs-packages/)
3. What does the node package manager do?
- the node package manager allows programmers to install packages to their code. It's basically a middle man that handles the installation of packages. Source (https://www.tutorialsteacher.com/nodejs/what-is-node-package-manager)
4. Provide code snippets showing 3 different ways to export a function from a node module
```js
module.exports = function (paramter) {
    console.log(parameter)
}

module.exports = function(parameter1, parameter2) {
    this.parameter1 = parameter1,
    this.parameter2 = parameter2

    this.function = function() {
        return this.parameter1 + this.parameter2;
    }
}

var newImport = requre('./source.js)
```
Source (https://www.tutorialsteacher.com/nodejs/nodejs-module-exports)

Vocabulary: 

Ecosystem: a collection of software packages, libraries etc that help with development as they integrate with each other. 

Node.js: a platform built on chrome's javascript runtime for easily building fast/scalable newtork apps. Uses an event-driven, nonblocking I/O model that makes it lightweight/effecient. Good for data-intensive, real-time appls that run across different devices. 

V8 Engine: google's open source high performance javascript and web assembly engine. Used in chrome and node.js

Module: A simple/complex functionally organized single or multiple javascript files that can be used throughout the node. 

Package: A collection of modules in directories that give package hierachy/organization. 

Node package manager: package manager for javascript. default package manager for javascript runtime environment node.js . consists of a command line client and an online database for public/paid-for private packages. 

Server: server software/hardware dedicated to running software that can satisfy all the requests it gets. Processes incoming network requests over http and other related protocols. 

environemnt: a place to put variables and utilize them without having to code them each time you need them. Think of it as a place to hold variables that are gonna be utilized across different javascript files. 

Interpreter: Installation of node.js on ocmputer or remote host or in a virtual environment. 