# Seperate javascript and include in HTML

In order to include a sperate javascript file apart from your backend javascript files you will need to create a folder inside your folder where all your static assets are. In my case my static assets are in my `public` folder. This folder would hold static files like html and css files. 

1. Inside my `public` folder I created another folder called `client` to hold my javascript files for the client side of my project. 
2. Inside the `client` folder I created a javascript file called `index.js`. 
3. After that I go into my `index.html` file and include the `<script>` tag like so `<script src="client/index.js"></script>`. 

The `script` tag is written that way because the `index.html` file and the `client` folder are in the same directory level like so.

```
	public/
		client/
			index.js
		index.html

```
So in order access the `index.js` file from my `index.html` file I need to go inside the `client` folder to access the javascript file.