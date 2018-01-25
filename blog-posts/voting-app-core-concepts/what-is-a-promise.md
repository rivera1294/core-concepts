# Understand how promises work. How do they solve "Callback hell"?

The mozilla developer network defines a `Promise` as an object that represents the eventual completion (or failure) of an asynchronous operation, and its resulting value. Promises are used as an alternative for executing and handling asynchronous operations. The traditional way of handling these asynchronous operations are call-back approaches.

Promises have 3 states
	
* Pending
* Fulfilled
* Rejected

When a promise is pending it means the asynchronous action hasn't finished.

When it is fulfilled it means the asynchronous action has finished.

When it is rejected then the promise failed and the promise will not be fulfilled.

Promises have been used to solve the callback hell problem. Callback hell refers to multiple nested callback functions, which makes it difficult to read.

Here is an example of callback hell

```
task1(function(){
    task2(function(){
        task3(function(){
                ....
        });
    });
});

```

Now here is an example of using promises.

```
task1(function(){..})
    .then(task2)
    .then(task3)

```

As you can see promises make code a bit more intuitive to understand because it makes asynchronous code look synchronous.
