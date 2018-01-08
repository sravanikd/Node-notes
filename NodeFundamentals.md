# Node Fundamentals

Includes learning all built in modules that come with node..These are objects, functions that lets us do stuff with javascript we've never been able to do before.

we'll learn:
#1 How to do things like read and write from the file system which we'll be using in Notes application to persist our data.
#2 Third party NPM modules(big part of the reason why node became so popular)
#3 Debugging broken apps.
#4 Look at new ES6 features

### Modules inside of node
Modules are units of functionality.Ex: Creating functions that help with math and bundle that up as a module and give it a name and other people could use it. We need to learn how we can use modules. This is going to get done using a function in node called require.

## REQUIRE
#1 It lets us load in modules that come bundled with nodeJs.
  Ex: HTTP modules which lets us make a web server and the FS module which lets us access the file system for our machine.
#2 Lets us load in 3rd party libraries like Express which helps us write less code. We use pre written modules to use the functions and solve problems by calling a few methods.
#3 We use require to require our very own files.

# STEPS TO CREATE OUR APP:

## Make a folder:
mkdir ----folder----
to go into files.. cd filename

### Built in Modules: 
No need to install anything in the terminal (obviously!) we can simply require them inside of our node files

## APP.JS file
After making folder, opening it up. we need to open up the directory we just created and make a file and put that in the root of the project. It should be called app.js This is where our application is going to start.
we'll write other files to use throughout the app but this is the only file that we'll run from terminal.This is the initialization file for our application.

Here in this app.js we can load in builtin module using require. We can get a complete list of node module on the nodeJs API docs. to view this, in browser, go to nodejs.org/api it has long list of built in modules.

### Using a module
in nodejs.org/api we will now see how to use the 1# file system module to create a new file --> Here we'll create a file and append(joining) to it . Insife file system there is a file to append. In append there are two parts: one is file name and second one is the data that we want to append to the file. To do this, we need to require the append file. 

we require append file from app.js,
#1 create a const variable and
#2 give it a name ex fs and set it equal to require and pass in just one string 'any' in require arguments list.here we'll pass in the module name fs and put a semicolon at the end
 const fs= require('fs');
#3 now append file 
fs.appendFileSync('fileName.txt','text you wanna append to the file');

and
2# OS module to let us fetch things like the user name for the currently logged.

