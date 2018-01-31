# Create a query to retrieve data from your Mongo database that involves multiple collections.

In this post I will show you how I created a query to retrieve data from multiple collections in mongodb. I will provide an example from my voting app project. The example will show you how I delete an authenticated user's poll. 

There are two collections that I will be accessing. They are the `Users` collection and the `Polls` collection.

First inside my `/:id/delete` route I am doing a lookup on my `Poll` model by invoking the method `findByIdAndRemove`. This will find the poll that corresponds to the id that I passed into the first argument of that method.

```
router.post('/:id/delete', checkAuthentication, function(req, res){
    
    
    Poll.findByIdAndRemove({ _id: req.params.id}, function(err, doc){
      
      if(err) {
        console.log(err);
      }
              
   })
      
})

```

Next inside the callback function of the `findByIdAndRemove` method I will do another look up inside another collection. This time I will look up the `User` that is currently authenticated and look for the reference to the `poll` document we just looked up in the previous code snippet. When it finds the `poll` reference inside the `user` document, then it will delete it from the `user` document.

```
router.post('/:id/delete', checkAuthentication, function(req, res){
    
    
    Poll.findByIdAndRemove({ _id: req.params.id}, function(err, poll){
      
      if(err) {
        console.log(err);
      }
      User.update({ twitterId: req.user.twitterId }, {"$pull": {"polls": poll.id }}, function(err){
            
            if(err){
                console.log(err);
            }
      }) 
              
   })
      
})



```

In the code snippet above I am using the `update` method on the `User` model to save the document once it makes the necessary changes. In the second argument I am passing the object `{"$pull": {"polls": poll.id }}`. The `$pull` operator will remove all instances of a value from an array that corresponds to `{ <field>: <value> }` pair which in this case is `{"polls": poll.id }}`

