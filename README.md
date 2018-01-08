
# What is Node?
Node is a javascript runfile that uses the v8 engine.

# What is v8 engine?
It is an opensource javascript engine written in c++ that takes javascript code and compiles it to machine code.

# Why is it so good at creating backend?
Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js' package ecosystem, npm, is the largest ecosystem of open source libraries in the world.

## I/O model-application
communication from our node application to other things inside of the internet of things.It could be a database, read/write req. for example, google maps---for apps like these, they need to take an input and give back an output which takes time.

## Diff b/w blocking and non-blocking I/O 

``` Blocking.js                                              
  var getUserSync=require('./getUserSync');

  var user1=getUserSync('123');
  console.log('user1', user1);
  
   var user2=getUserSync('321');
  console.log('user2', user2);

  var sum=1+2;
  console.log('The sum is ' + sum);
  
```

``` Non-blocking.js
  var getUser=require('./getUser');
  
  getUser('123',function(user1){
    console.log('user1', user1);
});
getUser('321',function(user2){
    console.log('user2', user2);
    
  var sum=1+2;
  console.log('The sum is ' + sum);
});
```

The first line on each of the above codes is responsible for fetching a function that gets called. and this function is gonna be our simulated I/O function,that is going to database,fetching some userdata and printing it to the screen.

Both files do the same thing they just do it in diff ways. after we load in the funciton, both files try to fetch a user with id 123 and when it gets that user it ptints it to the screen with the user1 string before and then it goes on and it fetches user 321 as id and prints it to the screen and adds 1+2 and prints the result. Both fetches same but work differently in the tim they execute each. Relative operating speed between the two differs. Fetching time of user id in blocking i/o is higher cuz, in 'blocking' the fetching and printing happens one after the other. simultaneous works cant be done, hence the name blocking.

In non-blocking application, it's the same but we wont wait,we start and kick off a fetch event as it falls into a loop...without printing first user data, we kick off second event of fetching second user's id...and sum happens simultaneously... no need to wait.
Non-blocking I/O lets us run more that one IO operations at the same time.
Inside of the nodeJs the event loop attaches a listener for the event to finish.

Instead of this whole example, if we take a webserver

## In WebServer
If a web server comes in looking to query the database we can't process other users requests without firing separate threads. But node js is single threaded,which means our app runs on one single thread.This is even better with non-blocking I/O as blocking I/O causes CPU RAM wastages.
