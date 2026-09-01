# Read 01 - Node Ecosystem

## Introduction to Node.js

### Big Picture

Node.js allows JavaScript to run outside of the web browser.

Normally, we think of JavaScript as code that runs inside a browser and controls
things such as buttons, forms, page behavior, and user interaction.

Node changes that.

With Node.js, JavaScript can run directly on a computer or server. This allows
JavaScript to perform tasks such as:

- creating web servers
- handling HTTP requests
- communicating with databases
- reading and writing files
- building APIs
- running command-line programs
- running development tools and tests

This means JavaScript can be used for both the client side and the server side
of an application.

---

### What is Node.js?

Node.js is a JavaScript runtime built using Google's V8 JavaScript engine.

V8 is the JavaScript engine used by Google Chrome. Its job is to take JavaScript
and compile it into machine code that the computer can execute.

Node uses the V8 engine without requiring the browser.

A useful mental model is:

Browser:

JavaScript -> Browser -> V8 -> Computer

Node:

JavaScript -> Node.js -> V8 -> Computer

The important difference is the environment surrounding JavaScript.

Inside a browser, JavaScript has access to browser features such as the DOM.

Inside Node, JavaScript instead has access to features useful on a computer or
server, such as:

- the file system
- HTTP
- networking
- operating-system utilities

---

### Required Question: How would you describe Node to a non-technical friend?

I would describe Node.js as a way to let JavaScript work outside of a website.

JavaScript normally works inside the browser. Node gives JavaScript an
environment where it can run directly on a computer or server.

A simple comparison would be:

> JavaScript is the language, while Node is one of the environments that knows
> how to run that language.

This allows developers to use JavaScript to build the parts of an application
that work behind the scenes, not just what the user sees in the browser.

---

### Required Question: What does it mean that Node is a JavaScript runtime?

A runtime is the environment in which a program executes.

Calling Node a JavaScript runtime means that Node provides an environment where
JavaScript code can be executed without needing a browser.

Node uses the V8 JavaScript engine to execute the JavaScript and adds tools that
allow the program to interact with the computer and server environment.

So:

JavaScript = the programming language

V8 = the engine that executes JavaScript

Node.js = the runtime environment surrounding that engine

---

### Required Question: What is Node used for?

Node can be used for many kinds of development tasks.

Some important uses include:

- creating servers
- creating REST APIs
- communicating with databases
- building real-time applications
- handling many network requests
- running automated tests
- running build tools
- creating command-line applications
- automating repetitive tasks

Node is especially useful for applications that perform a lot of input/output
work, such as waiting for HTTP requests, database operations, or file
operations.

---

### Event-Driven and Non-Blocking

One of the important ideas behind Node is that it is event-driven and uses
non-blocking I/O.

A server frequently has to wait for something:

- a database query
- a file to load
- a network request
- another service to respond

Instead of stopping everything while one operation finishes, Node can continue
handling other work.

When the operation finishes, Node can return to the code that was waiting for
the result.

A useful mental model is:

Request comes in
      |
      v
Node starts the task
      |
      +---- task must wait
      |
      v
Node handles other work
      |
      v
Task finishes
      |
      v
Node handles the result

This helps Node efficiently handle many connections.

---

### npm and the Node Ecosystem

Node also works closely with npm.

npm stands for Node Package Manager.

It allows developers to install and manage packages created by other
developers.


For example:


```bash
npm install express  

```

---

## Additional Questions

### What do I look forward to learning in this module?

I look forward to understanding more about how the different pieces of a
server-side application work together.

I have already worked with Node, Express, APIs, routes, middleware, and
databases, but I want to understand more clearly what is happening underneath
the code instead of only knowing which commands or syntax to use.

I especially look forward to becoming more comfortable with:

- Node and the server-side JavaScript ecosystem
- Express servers and routing
- middleware
- REST APIs
- testing
- data modeling and databases
- authentication and authorization
- deploying server applications

My goal is to connect these concepts so I can understand the complete path of
a request through an application.

---

### What are my learning goals after reviewing the class README?

My main learning goal is to become more independent when building and
troubleshooting applications.

I want to move from recognizing code to understanding why the code works and
being able to explain it.

Some specific goals are:

- understand the purpose of each part of a Node/Express application
- become more comfortable reading documentation
- improve debugging skills
- understand error messages instead of immediately reacting to them
- become stronger with Git and branching
- write and understand automated tests
- understand how applications communicate with databases
- become comfortable designing and building APIs
- improve my ability to explain technical concepts in my own words

I also want to build habits that make development more organized and
repeatable rather than treating every assignment as a completely separate
problem.

---

## Quick Reference

### Node

JavaScript runtime that allows JavaScript to execute outside the browser.

### V8

JavaScript engine used by Chrome and Node to execute JavaScript.

### Runtime

The environment where a program executes.

### npm

Package manager commonly used with Node.

### package.json

Describes a Node project, including dependencies, scripts, and project
information.

### node_modules

Directory containing packages installed for the project.

### Server

A program that listens for requests and sends responses.

### API

A defined way for software systems to communicate with one another.

### Non-blocking

Allows Node to continue handling other work while waiting for certain
operations to finish.

### Event-driven

Code responds to events such as requests, completed operations, or user
actions.

---

## Mental Model

A simple Node server can be thought of as:

Client
  |
  | HTTP Request
  v
Node / Express Server
  |
  | Route
  v
Handler / Application Logic
  |
  | optional
  v
Database / Other Service
  |
  v
Response
  |
  v
Client

Another useful relationship is:

JavaScript
     |
     v
   Node.js
     |
     +---- npm packages
     |
     +---- file system
     |
     +---- HTTP
     |
     +---- databases
     |
     +---- operating system

Node is therefore not another programming language.

The language is still JavaScript.

Node provides the environment that allows JavaScript to perform work outside
the browser.

---

## Things I Want to Remember

1. **Node.js is a JavaScript runtime, not a programming language.**

2. **JavaScript is the language; Node is an environment where JavaScript can
   execute.**

3. **Node uses Google's V8 JavaScript engine.**

4. **Node allows JavaScript to run outside the browser.**

5. **Server-side JavaScript can handle requests, files, databases, APIs, and
   other backend operations.**

6. **Node is designed around event-driven, non-blocking operations.**

7. **npm manages packages used by Node projects.**

8. **`package.json` describes the project and its dependencies.**

9. **`node_modules` contains installed dependencies and normally should not be
   committed to Git.**

10. **Running `node index.js` means Node is executing the JavaScript contained
    in `index.js`.**

11. **A server receives a request, processes it, and returns a response.**

12. **My goal is not only to make the code work, but to understand the path the
    code takes and why each part exists.**

