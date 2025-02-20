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

# frequntly asked
```
1) SCOPE VAR/LET /CONST 
	TEMPORAL DEAD ZONE: Time between a(variable) memory allocation( a =undefined)   and a(20)initialised
2) Callback hell:  Issue with CALLBACK
Asynchronous Programming exist in JS exist due to CALLBACK
3)  Promise: is an object representation of Eventual Completion or failure of Async Opeartion
 How to fetch data from backend ? Multiple fetch api: Promise.all() and map()
Write a promise if number is more than 2 Resolve it else error 
4) Closure : function with lexical scope , when function return function which can remember	pervious function data/varibale
issue with Closure
5)This keyword: behaves differently how it is called
6) Object Assignation Method & why Object.create is preferable & write own polyfil-protoype 
7)setTimeout + Closures & setInterval & clearInterval(NULL)
8) call apply bind [CAB] passing Object to Function  OR Function.OBJECT
9)Event loop ? call stack/microstack queue /callback Queue ? How to improve queue 
10)Cookies VS local VS Sesssion 
11)Event delegation vs enent Propagation and immediate propagation and EventBubbling and eventLooping 
12 ES6 standard : literal, spread, rest, destructure, arrow function 
13)Progressive Web App (PWA)/ service worker /Web accessibility /AA,AAA standard/Accessibility 
14)Intereceptor
15)What is generator function and why do we use it 
What will happen if no next is called ? on the iterator object, the generator function will not execute
16)Deep copy - separate copy 
const deepCopy = JSON.parse(JSON.stringify(nestedObject));
17)Event curry ? what is the usage why we use it 
18)Memory leakage 
19)declarative and imperative : JS is both 
20)Difference between MAPOBJECT vs object 
21)  global key- payment keys/ gateway keys- these are common and can’t be changed 
			- store in CONST : block
			- store in VAR: GLOBAL
What is difference and how this will impact code/speed: VAR,GLOBAL- increase the speed - we can’t	be used for const
22)for every change in textbook will trigger the Render how to prevent that 
	Debouncing[Depth-Search] is commonly used for scenarios like search input fields, where you want to wait for the user to finish typing before triggering a search request.
	Throttling is commonly used for scenarios like handling scroll events, where you want to limit the frequency of function invocations to avoid performance issues.
	PreventDefault()
23)OOBJ - Polymorphism, -different form, abstraction:hide ,encapsulation:follow process -Petrol car put petrol ,inheritance- feature parent in child component super
24)JS security 
25) Function return vs no return both are same 
Const fun =() => true 
Const fun =() => { return true }
```
