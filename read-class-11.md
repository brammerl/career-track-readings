# User Modeling
- user password should be encrypted
- email, username and addresses can be plain text as long as database is password protected or behind a firewall. 
- user models w sensitive data should never be sent to client apps. 
- create a 2nd profile model to hold data and strictly limit access to the profile model. 

# Crypotgraphy
- science which studies methods for encoding messages so they can only be read by a person who knows the secret information required for decoding

# Hash Algorithms
- takes a piece of data and produces a hash that is deliberately difficult to preserve. 
- if identicle data is passed into algorithm, same hash will always be produced. 
- hash password can be stored when user signs up and they can resent the password and can use the same hash algorithm. 

# Cypher Algorithms
- takes a piece of ata and a key and produces encrypte data. 

# Basic Authorization
- A common method used to send username/password in an http request
- resulting string (username:password) is set to the value of an authorization header 
- server can decode the basic authorization header to retrieve username and password. 

- atob and btoa to convert to/from base64 encoding in browsers. 

```
let encoded = window.btoa('someusername:P@55w0rD!')
// c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==

let decoded = window.atob('c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==');
// someusername:P@55w0rD!

request({
  method: 'GET',
  url: 'https://api.example.com/login',
  headers: {
    Authorization: `Basic ${encoded}`,
  },
})
.then(handleLogin)
.catch(handleLoginError)
```

Node app: 
```
let base64 = require('base-64');

let string = 'someusername:P@55w0rD!';
let encoded = base64.encode(string); // c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==
let decoded = base64.decode(encoded); // someusername:P@55w0rD!
```