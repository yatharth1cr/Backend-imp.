### Server Side Apps with Express.js and MongoDB

#### Express Fundamentals

##### 1. NPM & package.json
- **NPM (Node Package Manager):**
  - Tool for managing JavaScript packages.
  - Used to install, update, and manage project dependencies.
- **package.json:**
  - A file that contains project metadata.
  - Lists dependencies and scripts.
  - Created using `npm init`.

##### 2. Express Basics
- **Express:**
  - A minimal and flexible Node.js web application framework.
  - Simplifies the process of building server-side applications.
- **Installation:**
  - Install with `npm install express`.
- **Basic Setup:**
  - Create an Express application using `const app = express()`.
  - Start the server with `app.listen(port, callback)`.

##### 3. Middlewares in Express
- **Middleware:**
  - Functions that execute during the request-response cycle.
  - Can modify the request or response objects, end the request-response cycle, or call the next middleware function.
- **Usage:**
  - Define with `app.use(middlewareFunction)`.
  - Example: `app.use(express.json())` to parse JSON bodies.
- **Types:**
  - Application-level, Router-level, Built-in, Third-party.

##### 4. Routes in Express
- **Routes:**
  - Define the endpoints for the application.
  - Specify how the server should respond to client requests.
- **Basic Route Setup:**
  - Use `app.get('/path', (req, res) => { ... })` for GET requests.
  - Similar methods for POST, PUT, DELETE: `app.post()`, `app.put()`, `app.delete()`.
- **Route Parameters:**
  - Define with `app.get('/user/:id', (req, res) => { ... })`.
  - Access parameters using `req.params`.

##### 5. Error Handler Middlewares
- **Error Handling:**
  - Middleware to handle errors in the application.
  - Defined with four arguments: `(err, req, res, next)`.
- **Usage:**
  - Example: 
    ```javascript
    app.use((err, req, res, next) => {
      res.status(500).json({ message: err.message });
    });
    ```
- **Placement:**
  - Typically placed after all route handlers.
