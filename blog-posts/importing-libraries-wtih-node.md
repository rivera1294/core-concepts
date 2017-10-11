#Importing libraries into Node

When you are starting a new node project or even just javascript you're more than likely to use some type of open source library.  Npm is one of the most common used package managers out there. 

In order to start using npm to import third party libraries there are a few things you need to do to at the start.

1. Go into your root directory project folder from the terminal and run the command `npm init`. This will automaticallly create a `package.json` file for you and it will prompt you for some information for your project. You can click enter through all of them to get the default set up. Your `package.json` should look something like this.
	
	```
	//package.json
	{
	  "name": "my-app",
	  "version": "1.0.0",
	  "description": "",
	  "main": "app.js",
	  "scripts": {
	    "test": "echo \"Error: no test specified\" && exit 1"
	  },
	  "author": "",
	  "license": "ISC",
	  "dependencies": {
	    "multer": "^1.3.0"
	  }
	}


	```

2. Now to import a library or package into your project you will run this command `npm install --save multer` inside your terminal from the root directory of your project. I am installing the library `multer` but you can install which ever library you want.
3. Now to start using you library in your project go to your `app.js` file or whatever you named it when you created your `package.json`. To import you library you code should look something like this.

	```
	//app.js

	var multer = require('multer');

	```
	
Now your `package.json` should look something like this.


	//package.json
	{
	  "name": "my-app",
	  "version": "1.0.0",
	  "description": "",
	  "main": "app.js",
	  "scripts": {
	    "test": "echo \"Error: no test specified\" && exit 1"
	  },
	  "author": "",
	  "license": "ISC",
	  "dependencies": {
	    "multer": "^1.3.0"
	  }
	}




	




