<div align= center><h1>bodyParser.json() vs express.json() & express.urlencoded() vs express.json()</h1></div>

## bodyParser.json() vs express.json() 


Earlier versions of Express used to have a lot of ```middleware``` bundled with it. 
```bodyParser was one of the middlewares``` that came it. When Express 4.0 was released they decided to remove the
bundled middleware from Express and make them separate packages instead. The syntax then changed from 
app.use(express.json()) to app.use(bodyParser.json()) after installing the bodyParser module.

bodyParser was added back to Express in release 4.16.0.That means you don't have to use bodyParser.json() 
anymore if you are on the latest release.You can use express.json() instead.

---

