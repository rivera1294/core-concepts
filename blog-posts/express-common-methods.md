#Express methods

There are 3 common express methods that are used in projects.

1. `listen()`: Binds and listens for connections on the specified host and port. This method is identical to Node’s http.Server.listen(). This method provides you access to the port where you can access your project. In this case the your project would be on `localhost:3000`.
	
	```
	var express = require('express');
	var app = express();
	app.listen(3000);
	
	```
2. `get()`: Routes HTTP GET requests to the specified path with the specified callback functions. The first parameter of this method will be the path that is being requested and the second parameter is a callback function that will be called when that path is accessed.
	
	```
	app.get('/', function (req, res) {
  		res.send('GET request to homepage');
	});
	
	``` 		
	
3. `post()`: Routes HTTP POST requests to the specified path with the specified callback functions. This is very similair to the `get()` method but instead this will be used to post data to the specified path.

	```
		app.post('/', function (req, res) {
  			res.send('POST request to homepage');
		});
	
	```
4. `use()`: Mounts the specified middleware function or functions at the specified path: the middleware function is executed when the base of the requested path matches path. 
