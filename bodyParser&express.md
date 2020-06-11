<div align= center><h1>bodyParser.json() vs express.json() & express.urlencoded() vs express.json()</h1></div>


**What is Middleware?** It is those methods/functions/operations that are called BETWEEN processing the Request and sending the Response in your application method.


Node/Express Framework have been used to installing another piece of middleware in order for us to be able to``` read the “body” of an incoming JSON object```. This piece of middleware was called ```body-parser``` and used to not be part of the Express framework.Express version 4.16+, their own body-parser implementation is now included in the default Express package so there is no need for you to download another dependency.



## bodyParser.json() vs express.json() 

Earlier versions of Express used to have a lot of ```middleware``` bundled with it. 
```bodyParser was one of the middlewares``` that came it. When Express 4.0 was released they decided to remove the
bundled middleware from Express and make them separate packages instead. The syntax then changed from 
app.use(express.json()) to app.use(bodyParser.json()) after installing the bodyParser module.

bodyParser was added back to Express in release 4.16.0.That means you don't have to use bodyParser.json() 
anymore if you are on the latest release.You can use express.json() instead.

**note:** There are still some very specific cases where body-parser might still be necessary but for the most part Express’ implementation of body-parser is all you will need for the majority of use cases.

---

## express.json() vs express.urlencoded()

Here is the explanation that should clear doubts on express.json() and express.urlencoded()
and the use of body-parser.

When talking about ```express.json()``` and ``` express.urlencoded()``` think specifically about POST requests (i.e. the .post request object) and PUT Requests (i.e. the .put request object).You DO NOT NEED express.json() and express.urlencoded() for GET Requests or DELETE Requests.You NEED ```express.json()``` and ```express.urlencoded()``` for POST and PUT requests, because in both these requests you are sending data (in the form of some data object) to the server and you are asking the server to accept or store that data (object), which is enclosed in the body (i.e. req.body) of that (POST or PUT) Request.

**express.json()** is a method inbuilt in express to recognize the incoming Request Object as a JSON Object. This method is called as a middleware in your application using the code: app.use(express.json());

**express.urlencoded()** is a method inbuilt in express to recognize the incoming Request Object as strings or arrays. This method is called as a middleware in your application using the code: app.use(express.urlencoded());

```javascript

// parse application/json, basically parse incoming Request Object as a JSON Object 
app.use(express.json());

// parse application/x-www-form-urlencoded, basically can only parse incoming Request Object if strings or arrays
app.use(express.urlencoded({ extended: false }));

// parse incoming Request Object if object, with nested objects, or generally any type.
app.use(express.urlencoded({ extended: true }));

```
**note:** This option allows to choose between parsing the URL-encoded data with the **querystring library (when false)** or the **qs library (when true)**.



