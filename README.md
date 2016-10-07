# jwt-session - Session for express using JSON Web Tokens
## Introduction
`jwt-session` provides you a fully automated express-middleware session that stores the session-data client-side using JSON Web Tokens.
### Example - Demo
```
const jwtSession = require('jwt-session');
const express = require('express');

const app = express();

app.use(jwtSession());

app.get('/', (req, res, next) => {
    //write sth. into the session
    req.session.user = 'hans';
});
```
The req.session object will be packed into a JWT.
The JWT ist set as a cookie named `sess` on the client's pc.
When the user visits your site again the sess object is imported automatically.
