# Read 02 - Express, NPM, TDD, and CI/CD

## Express and Node.js

### Big Picture

Node.js allows JavaScript to run outside of the browser and gives us the ability
to create server-side applications.

Express is a framework that runs on top of Node.js and makes building web
servers and APIs easier.

A useful mental model is:

JavaScript
    |
    v
Node.js
    |
    v
Express
    |
    v
Routes / Middleware / Application Logic
    |
    v
Response to Client

Node gives JavaScript the server environment.

Express gives us tools and structure for working inside that environment.

For example, Express helps us:

- create routes
- receive HTTP requests
- send HTTP responses
- use middleware
- handle errors
- organize server code
- build REST APIs

---

### Required Question: Explain middleware to a non-technical recruiter

Middleware is code that runs between receiving a request and sending the final
response.

A simple comparison is a series of checkpoints.

Imagine someone enters an office building and wants to reach a particular
office. Before reaching that office, they may pass through security, have their
ID checked, and receive directions.

Each checkpoint performs one job before allowing the person to continue.

Middleware works similarly:

Client Request
      |
      v
Middleware
      |
      v
Middleware
      |
      v
Route Handler
      |
      v
Response

For example, middleware might:

- log information about a request
- check whether required information is present
- verify that a user is authorized
- parse incoming data
- handle errors

In Express, middleware can perform its task and then use `next()` to allow the
request to continue to the next middleware function or route handler.

---

### Express is "unopinionated." What does that mean?

Calling Express unopinionated means that Express does not force developers to
organize an application in one specific way.

It provides useful tools for building a server, but the developer makes many
of the architectural decisions.

For example, developers can decide:

- how files and folders are organized
- how routes are structured
- which database to use
- how authentication is implemented
- which additional packages are installed

This gives Express flexibility.

The tradeoff is that the developer must make more decisions about how the
application should be structured.

A useful way to remember this is:

Opinionated framework:

"Here is the way your application should be organized."

Express:

"Here are the tools. You decide how you want to organize them."

---

### What is a module?

A module is a reusable piece of code that has a particular responsibility.

Instead of putting an entire application into one enormous JavaScript file, we
can divide the program into smaller files or modules.

For example, a Node/Express project might contain:

```text
index.js
server.js
middleware/
    logger.js
    validator.js
error-handlers/
    404.js
    500.js
```

Each module has a particular job.

One module might start the server.

Another might define middleware.

Another might handle errors.

---

### Why is modularity useful to developers?

Modularity helps us divide a large problem into smaller, understandable pieces.

It can make code:

- easier to read
- easier to test
- easier to debug
- easier to reuse
- easier to maintain
- easier for a team to work on

A useful mental model is:

Large Application
      |
      +---- Server
      |
      +---- Routes
      |
      +---- Middleware
      |
      +---- Error Handlers
      |
      +---- Models
      |
      +---- Tests

Each piece has a responsibility, but the pieces work together to form the
complete application.

This also explains why separating `server.js`, middleware, error handlers, and
tests is useful in a Node/Express project.

---

## Things I Want to Remember - Express

1. **Node.js provides the runtime; Express provides tools for building the server.**

2. **A route determines how the server responds to a particular HTTP request.**

3. **Middleware runs during the request/response process.**

4. **`next()` allows middleware to pass control to the next step.**

5. **Express is unopinionated, meaning it gives developers flexibility about
   application structure.**

6. **A module is a piece of code with a specific responsibility.**

7. **Modularity helps make applications easier to understand, test, debug,
   reuse, and maintain.**

   ---

## NPM - Node Package Manager

### Big Picture

npm is the package manager commonly used with Node.js.

It helps developers find, install, update, and manage reusable packages of
JavaScript code.

Instead of writing every feature of an application from scratch, we can install
packages that provide functionality we need.

Examples include:

- Express for building servers
- Jest for testing
- Supertest for testing HTTP servers
- dotenv for working with environment variables

A useful mental model is:

My Application
      |
      +---- My Code
      |
      +---- npm Packages
               |
               +---- Express
               +---- Jest
               +---- Supertest
               +---- dotenv

---

### What is a package?

A package is reusable code that can be installed into a project.

Packages can provide:

- libraries
- frameworks
- command-line tools
- testing tools
- utilities

Packages normally include a `package.json` file that describes the package and
its dependencies.

---

### What is package.json?

`package.json` describes a Node project.

It can contain information such as:

- project name
- version
- scripts
- dependencies
- development dependencies

Example:

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

This allows:

```bash
npm test
```

to run Jest.

---

### Dependencies

A dependency is another package that our application relies on.

For example:

```bash
npm install express
```

installs Express and records it as a dependency of the project.

Installed packages are normally placed inside:

```text
node_modules/
```

The `node_modules` directory normally should not be committed to Git because
the dependencies can be recreated using the project's package information.

---

### Required Question: What version of npm am I running?

I checked my local machine using:

```bash
npm -v
```

My current npm version is:

```text
11.6.1
```

This is useful because software versions can change over time. Running the
command tells me what is actually installed on my machine rather than assuming
a particular version.

---

### Required Question: How would I install a package called jshint?

The command is:

```bash
npm install jshint
```

This tells npm to locate the `jshint` package, download it and its required
dependencies, and install it into the current Node project.

A common shorthand for `install` is:

```bash
npm i jshint
```

---

### Useful npm Commands

Check the installed npm version:

```bash
npm -v
```

Install the dependencies listed for a project:

```bash
npm install
```

Install a particular package:

```bash
npm install express
```

Run the project's test script:

```bash
npm test
```

Initialize a new Node project:

```bash
npm init
```

Create a `package.json` using default answers:

```bash
npm init -y
```

---

## Things I Want to Remember - NPM

1. **Node runs JavaScript; npm manages packages used by Node projects.**

2. **A package is reusable code that can be installed into a project.**

3. **`package.json` describes the project and records dependencies and scripts.**

4. **`node_modules` contains installed packages.**

5. **`npm install` installs the dependencies required by a project.**

6. **`npm install package-name` installs a particular package.**

7. **My npm version at the time of this reading is 11.6.1.**

8. **I can always check the installed version with `npm -v`.**

---

## TDD - Test-Driven Development

### Big Picture

TDD stands for Test-Driven Development.

It is a development process where tests help guide the creation of the code.

Instead of writing an entire feature first and testing it afterward, the basic
TDD cycle is:

1. Write a test for the behavior you want.
2. Run the test and see it fail.
3. Write enough code to make the test pass.
4. Improve or refactor the code while keeping the test passing.
5. Repeat the process for the next behavior.

This cycle is commonly remembered as:

**RED -> GREEN -> REFACTOR**

RED:
The new test fails because the feature does not exist yet.

GREEN:
Write enough code to make the test pass.

REFACTOR:
Improve the code without changing its expected behavior.

### Mental Model

Think of a test as describing a promise:

> "When my program receives this input, I expect this result."

The implementation is then written to fulfill that promise.

---

### Required Question: Why are tests important?

Tests help us check that software behaves the way we expect it to behave.

To explain this to a non-technical elder, I might compare testing software to
checking important work before relying on it.

Imagine repairing something in a house.

After making the repair, we would not simply assume everything works. We would
turn it on, use it, and check that it behaves correctly.

Software tests do something similar.

They repeatedly check important parts of a program so that when the code
changes, we can discover whether something that worked before has been broken.

Tests do not guarantee that software has no bugs, but they give developers
evidence that expected behaviors are still working.

---

### Three Expected Benefits of Testing

#### 1. Tests help find problems earlier

A failing test can reveal that code does not behave as expected before the
problem reaches the user.

#### 2. Tests make changes safer

When developers modify or refactor code, existing tests can help determine
whether previously working behavior was accidentally broken.

This is useful for detecting **regressions**.

A regression occurs when a change causes something that previously worked to
stop working.

#### 3. Tests describe expected behavior

Tests can serve as another form of documentation.

A developer reading a test can see:

- what input is provided
- what action occurs
- what result is expected

This can help developers understand what a piece of software is supposed to do.

---

### Individual Pitfalls While Writing Tests

TDD and automated testing are useful, but developers can encounter problems.

#### Pitfall 1: Forgetting to start with a failing test

If a test immediately passes, it may not actually be testing the new behavior
we think it is testing.

Seeing the test fail first provides evidence that the test can detect the
missing behavior.

#### Pitfall 2: Writing too many tests at once

Trying to design a large number of tests and features simultaneously can make
the TDD cycle harder to follow.

TDD works best in small steps:

Test -> Fail -> Code -> Pass -> Refactor

#### Pitfall 3: Testing implementation instead of behavior

Tests that depend too heavily on exactly how the internal code is written can
become fragile.

A useful question is:

**What should this code do?**

rather than only:

**How is this code currently written?**

---

### Team Pitfalls While Writing Tests

Testing also requires teamwork and shared habits.

#### Team Pitfall 1: Team members use different testing approaches

If developers disagree about what should be tested or how tests should be
structured, the test suite can become inconsistent and difficult to maintain.

Teams benefit from shared testing conventions.

#### Team Pitfall 2: Tests become neglected

If failing tests are ignored or developers stop maintaining the test suite,
the team can lose confidence in the tests.

A test suite is useful when the team trusts that:

**passing tests mean something.**

#### Team Pitfall 3: Slow or complicated test suites

If tests take too long or are difficult to run, developers may avoid running
them frequently.

Fast and repeatable tests make it easier to include testing in the normal
development workflow.

---

## Jest and Supertest

In a Node/Express application, different tools can help us test our code.

### Jest

Jest is a JavaScript testing framework.

It provides tools for:

- defining tests
- running tests
- making assertions
- reporting which tests pass or fail

For example, conceptually:

```javascript
expect(result).toBe(expectedResult);
```

An assertion asks:

**Did the actual result match what I expected?**

---

### Supertest

Supertest is useful for testing HTTP servers.

Instead of manually opening the browser every time we want to test an Express
route, Supertest can send requests to the application during automated tests.

For example, a server test might check:

```text
GET /person?name=Luis
        |
        v
Expected status: 200
        |
        v
Expected response:
{ name: "Luis" }
```

Another test might intentionally send a bad request:

```text
GET /person
        |
        v
Expected error response
```

Testing both successful and unsuccessful behavior helps us verify that the
server handles different situations correctly.

---

### Happy Path, Expected Failure, and Edge Cases

A useful way to think about test coverage is to ask what kinds of situations
the application must handle.

#### Happy Path

The expected normal situation.

Example:

A valid request contains all required information and receives the expected
successful response.

#### Expected Failure

A known invalid situation.

Example:

A required query parameter is missing and the server returns an error.

#### Edge Case

An unusual or boundary situation that could reveal unexpected behavior.

Examples might include:

- an empty value
- an unusually large value
- unexpected input
- a boundary condition

---

### Things I Want to Remember - TDD

1. **TDD means Test-Driven Development.**

2. **The basic cycle is RED -> GREEN -> REFACTOR.**

3. **RED means write a test and see it fail.**

4. **GREEN means write enough code to make the test pass.**

5. **REFACTOR means improve the code while keeping its behavior working.**

6. **Tests help find problems and protect existing behavior from regressions.**

7. **Tests can document what the application is expected to do.**

8. **Jest provides the testing framework and assertions.**

9. **Supertest can send HTTP requests to an Express application during tests.**

10. **Good testing considers the happy path, expected failures, and relevant
    edge cases.**

### One Sentence to Remember

**A test describes what the program should do, and TDD uses those expectations
to help guide the code we write.**

---

## CI/CD - Continuous Integration and Continuous Delivery/Deployment

### Big Picture

CI/CD is a development process that helps teams integrate, test, and release
software more reliably.

CI stands for:

**Continuous Integration**

CD can refer to:

**Continuous Delivery**

or:

**Continuous Deployment**

A useful mental model is:

Developer writes code
        |
        v
Git Commit / Push
        |
        v
GitHub Repository
        |
        v
Automated Build and Tests
        |
        v
Code is Integrated
        |
        v
Delivery / Deployment

The goal is to catch problems earlier and make releasing software more
repeatable.

---

### Continuous Integration

Continuous Integration means developers frequently combine their changes into
a shared codebase.

When new code is pushed, automated processes can build the application and run
tests.

Instead of developers working separately for long periods and combining large
amounts of code later, integration happens frequently.

This can make conflicts and problems easier to discover.

---

### Required Question: What are three benefits of Continuous Integration?

#### 1. Problems are discovered earlier

Automated tests can run whenever code is integrated.

If something breaks, the team can discover the problem closer to the change
that caused it.

#### 2. Smaller changes are easier to integrate

Frequently combining smaller pieces of work is generally easier than waiting
until many large changes must be combined at once.

#### 3. The team receives faster feedback

Developers can quickly learn whether their changes build correctly and pass the
automated tests.

A useful way to remember CI is:

**Integrate often -> Test often -> Find problems sooner**

---

## Continuous Delivery vs Continuous Deployment

The names sound similar, but there is an important difference.

### Continuous Delivery

With Continuous Delivery, the software is automatically built and tested and
kept in a state where it is ready to release.

However, releasing the application to users still requires a deliberate
decision or manual approval.

Think:

Code
 |
 v
Build
 |
 v
Test
 |
 v
Ready to Release
 |
 v
MANUAL APPROVAL
 |
 v
Production

---

### Continuous Deployment

Continuous Deployment goes one step further.

If the code successfully passes the automated pipeline, it can automatically
be deployed to production without a separate manual release step.

Think:

Code
 |
 v
Build
 |
 v
Test
 |
 v
PASS
 |
 v
Automatically Deploy
 |
 v
Production

---

### Required Question: What is the difference?

The easiest distinction for me to remember is:

**Continuous Delivery = automatically ready to deploy**

**Continuous Deployment = automatically deployed**

Delivery still has a decision point before production.

Deployment removes that manual release step when the automated checks pass.

---

## How GitHub Fits Into CI/CD

### Explain this to a non-technical person

Think of GitHub as the shared location where a development team keeps the
official history of its project.

A developer works on some code and sends the changes to GitHub.

GitHub can then work with automated systems that check the new code.

Those checks might ask:

- Does the application build?
- Do the automated tests pass?
- Did the new change break existing behavior?
- Is the code ready for the next step?

If the checks succeed, the code can move farther through the development
process.

A simple comparison is a factory inspection line:

Developer
   |
   v
GitHub
   |
   v
Automated Inspection
   |
   +---- FAIL -> Fix the problem
   |
   +---- PASS
           |
           v
      Ready for Release
           |
           v
        Deployment

GitHub therefore provides more than a place to store code.

It can be part of a workflow where code changes are reviewed, tested, combined,
and prepared for release.

---

## GitHub Actions

One way GitHub can participate in Continuous Integration is through
**GitHub Actions**.

A workflow can be configured to run automatically when events occur, such as a
push or pull request.

For example:

```text
Push code
    |
    v
GitHub Action starts
    |
    v
Install dependencies
    |
    v
Run tests
    |
    +---- FAIL
    |       |
    |       v
    |   Developer fixes code
    |
    +---- PASS
            |
            v
       Change can continue
```

This connects automated testing to the Git workflow.

---

## Connection to TDD

TDD and CI solve related but different problems.

TDD helps guide how a developer writes and tests code.

CI helps make sure changes from developers continue working when they are
integrated into the shared project.

Think:

TDD
Developer writes tests and code
        |
        v
Local tests pass
        |
        v
Push to GitHub
        |
        v
CI
Automated tests run again
        |
        v
Team receives feedback

Tests therefore provide value both while developing locally and when code is
integrated into the shared repository.

---

## Things I Want to Remember - CI/CD

1. **CI means Continuous Integration.**

2. **Continuous Integration combines code frequently and uses automated
   feedback to find problems earlier.**

3. **CI can automatically build and test code after changes are pushed.**

4. **Continuous Delivery keeps tested software ready to release.**

5. **Continuous Deployment can automatically release successful changes to
   production.**

6. **Delivery = ready for deployment.**

7. **Deployment = actually deployed.**

8. **GitHub can serve as the shared repository and trigger automated
   workflows.**

9. **GitHub Actions can automatically run tasks such as installing
   dependencies and running tests.**

10. **CI/CD makes software integration and release more repeatable.**

### One Sentence to Remember

**CI checks that our changes work together; CD helps move working software
toward the users.**

---

## Bookmark and Review

These resources are useful references rather than material I need to memorize
all at once.

### Node.js Documentation

Use the Node.js documentation when I need information about Node itself,
including built-in modules and APIs.

Examples of things I may look up:

- file system operations
- HTTP
- paths
- environment and process information
- Node APIs

Mental model:

**Question about Node itself -> Node documentation**

---

### npm Documentation

Use the npm documentation when I need help with packages, dependencies,
`package.json`, scripts, or npm commands.

Examples:

```bash
npm install
npm install express
npm test
npm -v
```

Mental model:

**Question about packages or npm commands -> npm documentation**

---

### Express Documentation

Use the Express documentation when working with an Express server.

Important areas include:

- routes
- middleware
- requests
- responses
- error handling

Examples:

```javascript
app.get('/route', handler);
```

and:

```javascript
app.use(middleware);
```

Mental model:

**Question about my Express server -> Express documentation**

---

### HTTP Status Codes

HTTP status codes tell the client what happened when the server processed a
request.

They are grouped into categories:

```text
1xx -> Informational
2xx -> Success
3xx -> Redirection
4xx -> Client Error
5xx -> Server Error
```

Some important examples:

```text
200 -> OK
201 -> Created
400 -> Bad Request
401 -> Unauthorized
403 -> Forbidden
404 -> Not Found
500 -> Internal Server Error
```

A useful mental model is:

**The response body tells me information.**

**The status code tells me what happened.**

---

### Supertest

Supertest helps test Node HTTP servers.

It is especially useful with Express because tests can send requests to the
application and inspect the response.

Conceptually:

```text
Supertest
    |
    | GET /person
    v
Express Application
    |
    v
Response
    |
    +---- status?
    +---- body?
    +---- expected result?
```

This lets automated tests verify route behavior without manually testing every
request in a browser.

---

## Reflection

### What are my learning goals after reading and reviewing the Class 02 README?

My goal is to understand how the individual pieces of an Express application
work together instead of viewing them as unrelated files and commands.

I want to become comfortable following the complete request and response path:

```text
Client Request
      |
      v
Express Server
      |
      v
Middleware
      |
      v
Route
      |
      v
Application Logic
      |
      v
Response
```

I also want to understand why modularity matters.

Instead of putting everything into one file, I want to recognize why an
application separates responsibilities into areas such as:

```text
index.js
server.js
middleware/
error-handlers/
tests/
```

My testing goal is to understand tests as descriptions of expected behavior,
not simply something I run before submitting an assignment.

I want to become more comfortable with:

- writing tests before or alongside features
- understanding assertions
- recognizing happy paths and expected failures
- reading failed test output
- using Jest
- using Supertest
- understanding HTTP status codes
- debugging from evidence rather than guessing

I also want to understand how my local development workflow connects to a
larger professional workflow:

```text
Write Code
    |
    v
Test Locally
    |
    v
Commit
    |
    v
Push to GitHub
    |
    v
Automated CI Tests
    |
    v
Review / Integration
    |
    v
Delivery / Deployment
```

My overall goal is to understand not only how to make a server work, but how
developers organize, test, share, and safely release server applications.

---

## Read 02 - Study Map

The major concepts from this reading connect together:

```text
NODE.JS
   |
   | provides the runtime
   v
EXPRESS
   |
   | organizes server behavior
   v
ROUTES + MIDDLEWARE
   |
   | application is separated into
   v
MODULES
   |
   | packages are managed by
   v
NPM
   |
   | expected behavior is checked with
   v
TESTS
   |
   +---- Jest
   |
   +---- Supertest
   |
   | development can follow
   v
TDD
   |
   | RED -> GREEN -> REFACTOR
   v
GIT / GITHUB
   |
   | changes can trigger
   v
CONTINUOUS INTEGRATION
   |
   | successful software moves toward
   v
DELIVERY / DEPLOYMENT
```

---

## Read 02 - Quick Reference

### Express

Framework used with Node.js to build web servers and APIs.

### Middleware

Code that runs during the request/response process before the final response.

### Module

A reusable, focused piece of an application.

### Modularity

Breaking a large application into smaller pieces with clear responsibilities.

### npm

Package manager commonly used with Node.js.

### TDD

Test-Driven Development.

```text
RED -> GREEN -> REFACTOR
```

### Jest

JavaScript testing framework.

### Supertest

Tool for testing HTTP server behavior.

### CI

Continuous Integration.

Frequently integrate code and automatically check that changes work together.

### Continuous Delivery

Software is automatically tested and kept ready for release, with a release
decision still remaining.

### Continuous Deployment

Successful changes can automatically proceed into production.

---

## Things I Want to Remember

**Node runs the JavaScript.**

**Express helps organize the server.**

**Middleware performs work along the request/response path.**

**Modules separate responsibilities.**

**npm manages packages.**

**Tests describe expected behavior.**

**TDD uses tests to guide development.**

**Jest runs JavaScript tests.**

**Supertest helps test HTTP requests and responses.**

**GitHub stores and integrates shared project history.**

**CI checks changes as they are integrated.**

**CD helps move tested software toward production.**

### One Sentence to Remember

**A well-built server is not just code that works; it is organized into clear
responsibilities, tested against expected behavior, and supported by a
repeatable process for integrating and releasing changes.**