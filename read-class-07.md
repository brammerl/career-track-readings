# Express Routing
- Event driven system
```js
app.get('/thing', (req, res) => {})
```
- The Request Object
```js
(req...)
/:parameters
  app.get('/api/:thing',...) = (req.params.thing)
Query strings
  http://server/route?ball=round = req.query.ball
```
- The response object
```
(..., res) responsible for sending data back to the browser
  has methods like send() and status()
    sends Headers
      cookies
      status codes
```
# Express Middleware 
- Each function receives request, response and next as parameters 
-App middleware
  - error handling
  - bringing in other routes
  - applies defaults
  - json, body and form parsing
  - runs on every request

- Route Middleware
  - Dealing w/ specific things for a route
  - generally, things many routes would participate in 
    - loged in? 
    - IP?
    - Have you been to the site before? 

# Modularlization & Seperation of Concerns
- Break things up so they make sense and can be digested in consumable amounts

# Server Testing
- Avoid starting actual server before testing
- Use super test in a module library
- wrape superagent in module 

# Test Pyramid
- Server testing crosses boundaries
  - Units: Server internal fxns 
  - Integration: how it connects to other servies
  - Acceptance: Server might be a dependancy of another test