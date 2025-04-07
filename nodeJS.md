
## nodejs - how to send html
```javascript

app.set("view engine", "ejs");
app.get("/", (req, res) => {
    res.render("index", { title: "Home Page" });
});
```
```javascript
app.get("/", (req, res) => {
    res.send("<h1>Welcome to My Website</h1>");
});
```
```javascript
app.get("/", (req, res) => {
    res.sendFile(path.join(__dirname, "index.html"));
});
```
-  create server
```javascript
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

```javascript
//Without express 
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

```javascript
const fs = require('fs');
const readStream  = fs.createReadStream('/read.txt');

readStream.on('data', (chunk)= > {
   console.log(chunk);
});
```

```javascript
app.get("/", (req, res) =>
  const stream = fs.createReadStream("./sample.txt", "utf-g"):  // read stream 
  stream.on ("data", (chunk) => res.write (chunk)) :              // when data comes write to response in chunk 
  stream. on ("end",() => res.end ()) }):   // stream ends stop the response
```
### Cluster  works on round robin Algo 1-1,2-2
- clusters of Node.js processes can be used to run multiple instances of Node.js that can distribute workloads among their application threads
- - What is cluster - when resource is fully occupied we use cluster
```javascript
const cluster = require('node:cluster');
const express = require('express')
const os = require('os').availableParallelism();
const process = require('node:process');

Const numCPUs= os.cpus.length()

if (cluster.isPrimary) {
  console.log(`Primary ${process.pid} is running`);

  // Fork workers.
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }
} else {
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

  console.log(`Worker ${process.pid} started`);
}
```
### Load balancer
### Calld one api Inside that,  two api calls Concatenate two api response and Send back to api
```javascript
const express = require("express");
const axios = require("axios");

const app = express();

app.get("/combined-api", async (req, res) => {
    try {
        // Call two external APIs in parallel
        const [response1, response2] = await Promise.all([
            axios.get("https://jsonplaceholder.typicode.com/posts/1"),  // First API
            axios.get("https://jsonplaceholder.typicode.com/users/1")   // Second API
        ]);

        // Combine responses
        const combinedResponse = {
            post: response1.data,
            user: response2.data
        };

        res.json(combinedResponse); // Send back the combined response
    } catch (error) {
        res.status(500).json({ error: "Error fetching data" });
    }
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`);
});

```
### What is process 
### 2 node server and api request hitting server 1 if more capacity then it should redireact to 2nd server? how
- horizontal some cluster type , vertical or load balancer
- httpProxy.createProxyServer()
- ngnix
```
    http {
    upstream backend_servers {
        server 127.0.0.1:3000;  # Server 1
        server 127.0.0.1:4000;  # Server 2
    }

    server {
        listen 80;

        location / {
            proxy_pass http://backend_servers;
        }
    }
}
```

### If we want to import one variable from package how can we do it - Eg axios install, them import and use it
```javascript
//Default
const myVar = "Hello from myModule!";
module.exports = myVar;

//Importing in Another File
const myVar = require("./myModule");
console.log(myVar);  // Output: Hello from myModule!
```
```javascript
//Named
export const myVar = "Hello from myModule!";

//Importing in Another File (app.mjs)
import { myVar } from "./myModule.mjs";
console.log(myVar);  // Output: Hello from myModule!
```
- Event loop in node js
- Architecture of node js
- Reactor pattern ? used for de multiplexer input output operation
- Middleware in node js- https,express - next(), authentication etc 
- Libuv library in node js
### Error first callback takes two argument (error, data) - if data return data else error
```javascript
const fs = require("fs");

// This file exists
const file = "file.txt";

// Error first callback
// function with two
// arguments error and data
const ErrorFirstCallback = (err, data) => {
if (err) {
	return console.log(err);
}
console.log("Function successfully executed");
console.log(data.toString());
};

// function execution
// This will return
// data object
fs.readFile(file, ErrorFirstCallback);

```
  
### What is thread pool and which library handles thread pool - liBUV
- Thread Pool is a group of worker threads used to execute tasks asynchronously in Node.js
- libuv is the C++ library used internally by Node.js to manage asynchronous I/O and thread pooling.
  
### If I upload 1gb in nodesjs how do you handle it - express-upload request and check the file sizeHow do handle If you use read Stream for 1 gb
-Limitation:  this is not recomended : express-fileupload
```javascript
const fileUpload = require("express-fileupload");

const app = express();

// Middleware for file upload with size limit (1GB)
app.use(fileUpload({
    limits: { fileSize: 1024 * 1024 * 1024 }, // 1GB limit
}));

app.post("/upload", (req, res) => {
    if (!req.files || !req.files.file) {
        return res.status(400).send("No file uploaded.");
    }

    const file = req.files.file;
    
    if (file.size > 1024 * 1024 * 1024) {  // Extra size check (1GB)
        return res.status(400).send("File is too large.");
    }

    file.mv(`./uploads/${file.name}`, (err) => {
        if (err) return res.status(500).send(err);
        res.send("File uploaded successfully.");
    });
});
```
- Use Readable Streams (Best for Large Files)
  - multer
  - createWriteStream
    

- Middle where used can http accept req bodyUser
### hit our api 5 per sec how do you handle it- request we get incremental value ,
-  so if every request is new how to get incremental value- socket can be used
-  Limit request rate (Rate Limiting) : express-rate-limit
- Track incremental values per request
- Use WebSockets if you need real-time updates
```javascript
const express = require("express");
const { WebSocketServer } = require("ws");

const app = express();
const PORT = 3000;

// Create an HTTP server with Express
const server = app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});

// Attach WebSocket Server to Express
const wss = new WebSocketServer({ server });

let counter = 0;

// Handle WebSocket Connections
wss.on("connection", (ws) => {
    console.log("Client connected");

    const interval = setInterval(() => {
        counter++; // Incremental value
        ws.send(JSON.stringify({ requestNumber: counter }));
    }, 200); // Every 200ms = 5 times per second

    ws.on("close", () => {
        clearInterval(interval);
        console.log("Client disconnected");
    });
});

// Express Route for Testing
app.get("/", (req, res) => {
    res.send("WebSocket server is running!");
});
```
```javascript
// Clinet
const socket = new WebSocket("ws://localhost:3000");

socket.onmessage = (event) => {
    console.log("Incremental Value:", JSON.parse(event.data));
};

```

### How many task you can allocate to number of thread-depends on system cpu core if 8 max 8 thread can be allowed ? 
#### If you have more than 8 How to handle?  Lets say two is wating 
  - Swap Long-Running Tasks: worker.terminate()
  - Cancel & Reassign Tasks Dynamically
  - Task Queue with Priority Scheduling
    
#### If two of the core failed How you handle ?
1️⃣ Detect Core Failures – Monitor CPU usage & process failures
2️⃣ Redistribute Work – Shift tasks to available cores
3️⃣ Restart Failed Workers – Use process managers like PM2
4️⃣ Load Balancing – Use external balancers (Nginx, HAProxy, Kubernetes)

## if  blocking operation runs on main thread and taking more time how will you handle it in node js ?
## **🔥 Which Solution Should You Use?**
| **Scenario** | **Best Solution** |
|-------------|------------------|
| CPU-heavy task (encryption, ML, parsing) | **Worker Threads** |
| Running external scripts or processes | **Child Processes** |
| Large file processing (uploads, logs) | **Streams** |
| Background jobs (email, notifications) | **Bull.js (Job Queue)** |


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
