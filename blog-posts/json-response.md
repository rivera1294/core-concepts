# Understand how to send a json response from server and parse the response in the client.

Here is an example snippet from my project that is sending a json response from the server.

```

app.post('/upload', upload.single('file'), function(req, res, next) {
    
    console.log(req.file);
    return res.json(req.file);
});


```

The code snippet above is returning data in a json format. 

The code below will show how the client will take the response and parse it.

```

 $.ajax({
      type: 'POST',
      url: '/upload',
      processData: false,
      contentType: false,
      cache: false,
      data: data,
      success: function(data){
        
        alert(data.size);
      }
      
    });

```

The ajax method is receiving the request in the success callback function and passing the data in a alert method.