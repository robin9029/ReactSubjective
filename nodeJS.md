
## nodejs - how to send html
  ```
app.set("view engine", "ejs");

app.get("/", (req, res) => {
    res.render("index", { title: "Home Page" });
});
```
```
app.get("/", (req, res) => {
    res.send("<h1>Welcome to My Website</h1>");
});
```
```
app.get("/", (req, res) => {
    res.sendFile(path.join(__dirname, "index.html"));
});
```
-  create server
```
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
OR
 res.status(200).send("Hello, world!");

})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

```
Without express 
const http = require('http');

const server = http.createServer((req, res) => {
  // Routing
  if (req.url === '/') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('Hello, world!');
  } else if (req.url === '/about') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('About page');
  } else {
    res.writeHead(404, { 'Content-Type': 'text/plain' });
    res.end('Page not found');
  }
});

const port = 3000;
server.listen(port, () => {
  console.log(`Server listening on port ${port}`);
});
```

-  Socket
## Stream

- when ask to read 50MB data it usess 400 to read if 100 users it will crash so read it in chunks
- We created pipeline - the time data comes , we stream to front end in chunks 

```
const fs = require('fs');
const readStream  = fs.createReadStream('/read.txt');

readStream.on('data', (chunk)= > {
   console.log(chunk);
});
```

```
app.get("/", (req, res) =>
  const stream = fs.createReadStream("./sample.txt", "utf-g"):  // read stream 
  stream.on ("data", (chunk) => res.write (chunk)) :              // when data comes write to response in chunk 
  stream. on ("end",() => res.end ()) }):   // stream ends stop the response
```
-  Load balancer
-  Call one api Inside that  two api calls Concatenate two api response and Send back to api
-  What is process 
- 2 node server and api request hitting server 1 if more capacity then it should redireact to 2nd server? how
  - horizontal some cluster type , vertical or load balancer
-  If we want to import one variable from package how can we do it - Eg axios install, them import and use it
- Event loop in node js
- What is cluster - when resource is fully occupied we use cluster
- Architecture of node js
- Reactor pattern ? used for de multiplexer input output operation
- Middleware in node js- https
- Libuv library in node js
- Error first callback
- What is thread pool and which library handles thread pool
- If I upload 1gb in nodesjs how do you handle it - express-upload-post request and check the file sizeHow do handle If you use read Stream for 1 gb
- Middle wehre used Can http accept req bodyUser
- hit our api 5 per sec how do you handle it- request we get incremental value ,
  -  so if every request is new how to get incremental value- socket can be used

## Js 
- Cyclic rotation arrayArray [1234]Output [3412]
- Data types in js
- Coercin
- Pass by value and pass by reference
    - How we can achieve pass by Val in JS
- Immediately invoked fn in JS eg fun(){}()


## Html css
- Void element
## Mongo
- How do you handle join- using find then lookup

- Socket 
- Stream
- Load balancer

- Call one api 
- Inside two api calls 
- Concatenate two api response and 
- Send back to api

- What is process 

- 2 node server and api request hitting server 1 if more capacity then it should redireact to 2nd server - horizontal some cluster type , vertical or load balancer 
- What is ecmascript 
- If we want to import one variable from package how can we do it - Eg axios install, them import and use it 
- Event loop in node js
- What is cluster - when resource is fully occupied we use cluster
- Architecture of node js
- Reactor pattern used for de multiplexer input output operation 
- Middleware in node js- https
- Libuv library in node js
- Error first callback
- What is thread pool and which library handles thread pool
- If I upload 1gb in nodesjs how do you handle it - express-upload-post request and check the file size
- How do handle If you use read Stream for 1 gb
- Middle wehre used 
- Can http accept req body
- User hit our api 5 per sec how do you handle it- request we get incremental value , so if every request is new how to get incremental value- socket can be used


- Js 
- Cyclic rotation array
- Array [1234]
- Output [3412]

- Data types in js
- Coercin
- Pass by value and pass by reference
- How we can achieve pass by Val in JS
- Immediately invoked fn in JS 
eg fun(){}()

- Html css 
- Void element

- Mongo
- How do you handle join- using find then lookup

- https://gist.github.com/paulfranco/9f88a2879b7b7d88de5d1921aef2093b

- Node architecture ?

- How multithreading works?
- How many task you can allocate to number of thread-depends on system cpu core if 8 max 8 thread can be allowed ?
- If you have more than 8 How to handle? 
- If two of the core failed How you handle ?
