# reverseAuthentication
Instructions


UNDER CONFIG.JSON 

-- 'development is used while the program is in development pulling in mySQL to the program for databases.

-- "test is used for the testing

-- production is used post development and testing.

-- these are your usernames and passwords

UNDER PASSPORT.JS

-- line 1 -- "this brings the node module 'passport' in for use, this is a form of user authentication.

-- This line is just how you use passport. 

--Line 4 brings in the module folder for use
// this tells passport we want to use a Local Strategy. so, we want login with a username/email and password
-- where this states /module it automatically uses index.js as the default( shorter way of daying /model/index.js

-- line 7
// Our user will sign in using an email, rather than a "username"

--line 12
// When a user tries to sign in this code runs

--line 20
// If there's no user with the given email (explain !)

--line 24
// If there is a user with the given email, but the password the user gives us is incorrect

--line30
// If none of the above applies, return the user

--line 33
// In order to help keep authentication state across HTTP requests,
// Sequelize needs to serialize and deserialize the user
// you could call this the boilerplate needed to make it all work


// Then this just exports the configured pass



INDEX.JS

--LINE 1
// this makes it so youre unable to create loose code. its very important for the fact youre messing with files on your computer.

// these are going to bring in all the modules that you will be using here

line 6
//This will be the baseline which will be your filename or repo

line 7
//your env is saying im logged in or im in development or on heroku or something similar. if the process.env is blank
it will pick development

line 8
// this is grabbing the config.json while passing along the env

line 9
// and the database or db is an empty object

go to config

//its checking to see if you have any.env in your config file.


line 12
// this is set up if there is an env variable it will create sequilize with whatever that variable is. otherwise jsut make a normal
seq

line 17 
//fs will envoke the file

read dir sync will read the file dirname is the file of the current location

then you filter through what you pulled from the above lines. (explain) needs to have these three things to be true - no period
does not include itself(index) - makes sure is .js

line 22
//a loop similar to a map youre reconstructing the link to the file here... making every file use seq. 

you took all the files you looked through and the ones to be put out are put into model.name
line 24
// youre saying modelName will equal the whole model all of user.js plus seq 

// object.keys is a way to loop through the keys of an obj. its going through the db here and making sure it associated.

line 33 
// and this will export the database.


USER.JS
line 1
// Requiring bcrypt for password hashing. Using the bcryptjs version as the regular 
bcrypt module sometimes causes errors on Windows machines

line 4
// Creating our User model

line 6 
// The email cannot be null, and must be a proper email before creation

line 16
// this is saying this password cannot be null

line 20
  // Creating a custom method for our User model. This will check if an unhashed password entered by the user can be compared to the 
hashed password stored in the database

line 24
  // Hooks are automatic methods that runs during various phases of the User Model lifecycle
  // In this case, before a User is created, we will automatically hash their password

ISAUTHENTICATED.JS	

line 1
// This is middleware for restricting routes a user is not allowed to visit if not logged in

line 4
//if the user is logged in, continue with the request to the restricted route

line 8
// If the user isn't logged in, redirect them to the login page


LOGIN.JS

line 1
// this makes this function ready when the page loads

line 2
// Getting references to our form and inputs

lines 7
// When the form is submitted, we validate there's an email and password entered

line 20
// If we have an email and password we run the loginUser function and clear the form

line 26
// loginUser does a post to our "api/login" route and if successful, redirects us the the members page

line 34
// if theres an error log the error


MEMBER.JS

line 4
this file does a GEt request to figure out which user is logged in and updates the HTML page

SIGNUP.JS

































