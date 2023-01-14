---
title: Authentication
position_number: 2
parameters:
  - name:
    content:
content_markdown: >-
  The API uses JSON Web Tokens (JWT) for authentication. Each request to the API
  must include a valid JWT in the Authorization header. The token should be
  prefixed with Bearer followed by a space.


  *Obtaining a JWT*


  To obtain a JWT, go to [www.AS20z.com](http://www.AS20z.com) and login to user
  account. Navigate to the “User” page from the breadcrumbs at the top of the
  page and find your username. Click the 3-dot dropdown icon left of your name
  and select “Token”. On the popup, click create to obtain your token or copy an
  existing token if one has already been created for your user.


  If you do not have an account on [www.AS20z.com](http://www.AS20z.com),
  contact ControlTec directly to have an account or JWT created.


  *Using the JWT*


  Once you have obtained a JWT, you should include it in the Authorization
  header of all subsequent requests to the API.


  For example, to get a list of sites, you would send a GET request to the
  /sites endpoint with the following headers:


  Authorization: Bearer
  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV\_adQssw5c


  *Token expiration*


  JWT tokens are valid for a limited time. If a token expires, the API will
  return a 401 Unauthorized response. In this case, you will need to obtain a
  new JWT, repeat the steps above and create a new token.


  Nothing will work unless you include this API key

  {: .error}
left_code_blocks:
  - code_block:
    title:
    language:
right_code_blocks:
  - code_block: |2-
       $.get("http://api.myapp.com/books/", { "token": "YOUR_APP_KEY"}, function(data) {
         alert(data);
       });
    title: JQuery
    language: javascript
  - code_block: ' curl http://api.myapp.com/books?token=YOUR_APP_KEY'
    title: Curl
    language: bash
---
