## Q. issue with CALLBACK?
- we loose control of execution where callback called inside another callback CALLBACK HELL
- we are giving control to other function and we don’t know what is happening - it may not be called or may called 2 times INVERSION OF CONROL
## Q. if JS is singleThreaded then, how callback and promise works
- Callbacks (used in setTimeout, event listeners, etc.) are executed by JavaScript, but Web APIs handle the actual async execution.
- Promises are native to JavaScript (ES6), but their resolution (.then(), .catch()) is managed by the Microtask Queue, which runs after each synchronous operation

- Call Stack – Executes synchronous code.
- Web APIs – Handles async tasks (setTimeout, fetch, DOM events, etc.).
- Callback Queue – Stores callback functions waiting to execute.
- Microtask Queue – Stores Promises and MutationObserver callbacks.
- Event Loop – Moves tasks from the callback/microtask queue to the call stack when it's empty.

## Q. Scenario	-> Synchronous or Asynchronous?
- Direct function call inside another function	✅ Synchronous
- Used with setTimeout/setInterval	⏳ Asynchronous
- Used in fetch API / Promises	⏳ Asynchronous
- Used in event listeners (addEventListener)	⏳ Asynchronous
- Array methods (map, forEach)	✅ Synchronous

## Q. Fetch vs Asyn & Awaits if both does same then why we prefer asyn & Await ? more explanation required
### Fetch Promise 
```
console.log("Start");

const fetchData = () => {
    fetch("https://api.example.com/data")
        .then(response => response.json()) // Convert response to JSON
        .then(data => console.log("Data received:", data)) // Handle data
        .catch(err => console.log("Error:", err)); // Handle errors

    console.log("Fetching data..."); // This runs synchronously
};

fetchData();
console.log("End");
```
```
Start
Fetching data...
End
Data received: { ...API Response... } (after some delay)
```
- issue is Callbacks inside .then() make it harder to read for multiple async calls. or if nested calls
#### Async & await
```
console.log("Start");

const fetchData = async () => {
    try {
        console.log("Fetching data...");
        const response = await fetch("https://api.example.com/data"); // Wait for fetch
        const data = await response.json(); // Wait for JSON conversion
        console.log("Data received:", data);
    } catch (error) {
        console.log("Error:", error);
    }
};

fetchData();
console.log("End");
```
```
Start
Fetching data...
End
Data received: { ...API Response... } (after some delay)
```
