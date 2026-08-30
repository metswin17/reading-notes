# Read 03

## JavaScript Classes

### Key Points

- A class is a template for creating objects.
- Classes group data and behavior together.
- `constructor()` runs when a new instance is created.
- `this` refers to the current instance.
- Methods are functions that belong to a class.
- `static` members belong to the class rather than an instance.
- Private fields begin with `#`.
- `extends` allows one class to inherit from another.
- `super()` accesses the parent class.

### Quick Reference

- `class` → blueprint/template for objects
- `new` → creates an instance
- `constructor` → initializes an instance
- `this` → current instance
- method → behavior belonging to the class
- `static` → belongs to the class itself
- `#` → private field or method
- `extends` → inheritance
- `super` → parent class

### Mental Model

Class → `new` → Object / Instance

An object has:
- Properties → what it HAS
- Methods → what it DOES

---

## Express Routing

### Key Points

- Routing determines how a server responds to a client request.
- A route combines an HTTP method, path, and handler.
- `GET` reads data.
- `POST` creates data.
- `PUT` updates data.
- `DELETE` removes data.
- Dynamic URL values such as `/food/:id` are available through `req.params`.
- `req` represents the incoming request.
- `res` represents the outgoing response.
- `next()` passes control to the next handler or middleware.

### Quick Reference

- `app.get()` → handle GET
- `app.post()` → handle POST
- `app.put()` → handle PUT
- `app.delete()` → handle DELETE
- `req.params` → URL parameters
- `req.body` → submitted request data
- `res.json()` → send JSON
- `res.status()` → set HTTP status
- `next()` → continue to next handler

### REST / CRUD Pattern

- POST `/food` → CREATE
- GET `/food` → READ ALL
- GET `/food/:id` → READ ONE
- PUT `/food/:id` → UPDATE
- DELETE `/food/:id` → DELETE

---

## Express Router

### Key Points

- `express.Router()` creates a modular group of routes.
- A Router acts like a small routing application.
- Routers help separate features into different files.
- Routes and middleware can be grouped together.
- `app.use()` mounts a router into the main application.

### Example Structure

server.js

    |
    +-- /food ------> foodRouter
    |
    +-- /clothes ---> clothesRouter

### Quick Reference

- `express.Router()` → create a router
- `router.get()` → GET route
- `router.post()` → POST route
- `router.put()` → PUT route
- `router.delete()` → DELETE route
- `router.use()` → router middleware
- `app.use()` → mount router

---

## Things I Want to Remember

- A **class** is a blueprint used to create objects.
- **Properties** describe what an object has.
- **Methods** describe what an object does.
- An Express **route** connects an HTTP request to a handler.
- `req` comes **into** the server.
- `res` goes **out** from the server.
- `req.params` comes from the URL.
- `req.body` comes from data sent with the request.
- `express.Router()` keeps related routes modular and organized.
- `app.use()` connects middleware and routers to the application.