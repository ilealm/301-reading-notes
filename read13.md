# Read 13, Sending form data

## Client/server architecture:
>  A client (usually a web browser) sends a **_request_** to a server (most of the time a web >server like.The server answers the request using, generally, HTML protocol.

## On the client side: defining how to send the data

* The `<form>` element defines how the data will be sent. 
* All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. 
* The two most important attributes are:
  1. action.
  1. method.

## The action attribute
* It defines **where the data gets sent**. 
* If the value must be a valid relative or absolute URL. If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page.
* The action value should be a file on the server that can handle the incoming data, including ensuring server-side validation. 

_In this example, the data is sent to an absolute URL:_

`<form action="https://example.com">`

_Here, we use a relative URL — the data is sent to a different URL on the same origin:_

`<form action="/somewhere_else">`

_When specified with no attributes, as below, the <form> data is sent to the same page that the form is present on_

`<form>`

## The method attribute
* How the data is sent depends on the method attribute.
* HTTP protocol provides several ways to perform a request; different methods, the most common being the GET method and the POST method.
* An HTTP request consists of two parts: 
  1. A header that contains a set of global metadata about the browser's capabilities.
  1. And a body that can contain information necessary for the server to process the specific request.


## The GET method
> The GET method is the method used by the browser to ask the server to send back a given     resource: "Hey server, I want to get this resource." 

* In this case, the browser **_sends an empty body_**. 
* Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.
* Key/value pairs are send at the end of the URL, you'll see the URL www.foo.com`/?say=Hi&to=Mom`
* If you need to send a **_sensitive piece of data, never use the GET method_** or you risk displaying it in the URL bar, which would be very insecure.

_Example:_

>`<form action="http://www.foo.com" method="GET">`
>
>`  <div>`
>
>`    <label for="say">What greeting do you want to say?</label>`
>
>`    <input name="say" id="say" value="Hi">`
>
>`  </div>`
>
>`  <div>`
>
>`    <label for="to">Who do you want to say it to?</label>`
>
>`    <input name="to" id="to" value="Mom">`
>
>`  </div>`
>
>`  <div>`
>
>`    <button>Send my greetings</button>`
>
>`  </div>`
>
>`</form>`

_The HTTP request looks like this:_

> `GET /?say=Hi&to=Mom HTTP/2.0`
> 
> `Host: foo.com`


## The POST method
> It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." If a form is sent using this method, the data is appended to the body of the HTTP request.

* Using the POST method you get no data appended to the URL.
* If you **_need to send a large amount of data_**, the POST method is preferred because some browsers limit the sizes of URLs. In addition, many servers limit the length of URLs they accept.

_The HTTP request on the last example, using POST looks like this:_

> `POST / HTTP/2.0`

> `Host: foo.com`

> `Content-Type: application/x-www-form-urlencoded`

> `Content-Length: 13`

> `say=Hi&to=Mom`

* Content-Length header: indicates the size of the body.
* Content-Type header: indicates the type of resource sent to the server.


## On the server side: retrieving the data
*  the server receives a string that will be parsed in order to get the data as a list of key/value pairs. 
* The way you access this list depends on the development platform you use and on any specific frameworks you may be using with it.

## A special case: sending files
* Files are binary data. 
* Because HTTP is a text protocol, there are special requirements for handling binary data.

### The enctype attribute
* This attribute lets you specify the value of the Content-Type HTTP header included in the request generated when the form is submitted. 
* This header is very important because it tells the server what kind of data is being sent. 
* By default, its value is application/x-www-form-urlencoded. 
* If you want to send files, you need to take three extra steps:
  1. Set the method attribute to POST because file content can't be put inside URL parameters.
  1. Set the value of enctype to multipart/form-data because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).
  1. Include one or more `<input type="file">` controls to allow your users to select the file(s) that will be uploaded.

_For example:_

>`<form method="post" action="https://www.foo.com" enctype="multipart/form-data">`
>
>`  <div>`

>`    <label for="file">Choose a file</label>`

>`    <input type="file" id="file" name="myFile">`

>`  </div>`

>`  <div>`

>`    <button>Send the file</button>`

>`  </div>`

>`</form>`

## Security issues
* Each time you send data to a server, you need to consider security. 
* HTML forms are by far the most common server attack vectors.
* All data that comes to your server must be checked and sanitized. Always. No exception.
* Escape potentially dangerous characters:
  * The specific characters you should be cautious with vary depending on the context in which the data is used and the server platform you employ, but all server-side languages have functions for this. Things to watch out for are character sequences that look like executable code (such as JavaScript or SQL commands).
* Limit the incoming amount of data to allow only what's necessary.
* Sandbox uploaded files:
  * Store them on a different server and allow access to the file only through a different subdomain or even better through a completely different domain.