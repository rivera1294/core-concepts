# What is an AJAX request

AJAX stands for stands for asynchronuos javascript and XML. Ajax is known as a technique for sending and retrieving data in the background without refreshing the web page. An example of an ajax call in real life would be the twitter feed feature. When you are scrolling through your twitter feed, twitter is using ajax in the background to retrieve new tweets as you scroll down. 

Twitter is making an ajax call to its servers, there it is running some logic and than going into the database to retrieve the new tweets. The server recieves the new tweets and sends the data back in json format. Here is an illustration of an ajax call being done while scrolling through twitter.
![Imgur](https://i.imgur.com/jOWuOI9.png?1)



Ajax is most commonly used in web forms as well. I created a file meta data project that basically takes a file that the user uploads and upon submitting the form my program will run an ajax call with the form data and make a request to my server. The difference between my previous example is that we are making an ajax call to post data, not just revcieve data. The term `POST` is known as an http method. There are four main methods. They are `GET`, `POST`, `PUT` and `DELETE`. Since the user is submitting form data, or in other words `posting` data, the correct method to use for this scenerio would be the `POST` method.

When the user submits the form my server will take the form data it recieved through the ajax call and run some logic to extract the size of the file that was uploaded. This data extraction is done with the help of a third-party library called multer. When the size data is extracted my server will send a json response of that data. While all that server logic is happening my ajax call is waiting in the background for that response data. This is the `asychronous` nature of ajax. Once it recieves the data my callback function will display the size data in an alert box on the page. This whole process is done without refreshing the page. 

Here is an illustration of the ajax call

![Imgur](https://i.imgur.com/2X6k2G7.png)

There are a few different ways to make an ajax call in javascript. I used the jQuery ajax method to make my ajax call. 
```
$('form').submit(function(event) {

    var data = new FormData(this);
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
    return false;
}
```
The ajax call can take a variety of parameters. Depeding on what you are building you may need more than the required parameters. 

I'll list the parameters I used for my ajax call and give a brief definiion.

* `type`: Specifies the type of request. (GET or POST)
* `url`: Specifies the URL to send the request to. Default is the current page
* `processData`: A Boolean value specifying whether or not data sent with the request should be transformed into a query string. Default is true
* `contentType`: The content type used when sending data to the server. Default is: "application/x-www-form-urlencoded"
* `cache`: A Boolean value indicating whether the browser should cache the requested pages. Default is true
* `data`: Specifies data to be sent to the server
* `success`: A function to be run when the request succeeds





