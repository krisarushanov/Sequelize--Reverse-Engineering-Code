# Sequelize--Reverse-Engineering-Code

Using the given code, explain every file and how it interacts with other files.

AS A developer

I WANT a walk-through of the codebase

SO THAT I can use it as a starting point for a new project


MIDDLEWARE

isAuthenticated.js 
- Checks to see if user is authenticated
- Redirects incorrect route back to log in page
- Interacts with html-routes.js 


Passport.js
Used to implement a login system by offering authentication mechanisms. LocalStrategy is a session-based authentication method.
- JS logic using user and password info
- password verification
- Need an email + need a correct one, if email is wrong, send message
- interacts with server.js

MODELS

index.js 
- connects to database and imports users log in data 
- Require (‘fs’)  -  Uses File System module to call up the right file name
- uses config.json for connections to database
- If/Else conditional - go to mySQL and call up username and password
- new Sequelize- creating a new entry
- .forEach - importing this file with this directory and joining with path 
- Associating model with database then exporting data base


User.js
- requires "bcrypt" for password hashing making our database secure even if compromised.
- JS logic tells us what is being stored in the database
- Hook method- automatically take in password and hashes it


ROUTES

api-routes.js 
- contains routes to sign up , login and logout
- Serving out data (JSON)
- Static file Public js files are using these routes
 
Html-routes.js
-Serves out pages to be viewed by the browser
- Html routes based on of the user has an account
- GET method- name/value pairs are sent in the URL of the GET request
- Uses middleware - checks to see if user is authenticated

package.json 
- Stores dependencies and package information


server.js 
- requires packages, sets up PORT, creates express and middleware, creates routes and syncs
