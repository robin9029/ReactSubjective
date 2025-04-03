### **4) JavaScript, TypeScript**  
  - `"A" - "B" = NaN`  
  - `"2" - "2" = 0`  
- `"2" + 2 = "22"`  
- **Event loop?** → Call stack, callback queue, Microtask queue (priority-based), provided by browser runtime/Node runtime.  
- **Promise & setTimeout: Which one executes first?** → Promise, because it runs on the Microtask queue.  
- **Prototypes?** → Default constructor, default object created, prototype chain leads to `null`.  
- **`this` keyword?** → Behaves differently in function/global scope, arrow function points to the parent object, strict mode refers to `undefined`, event refers to the element.
- **JS?** → Used for creating interactive UI applications.  
- **`map` vs `forEach`?** → Both iterate over an array, but `map` creates a new array while `forEach` does not.  
- **`map`, `filter`, `find`?** →  
  - `map`: Transforms elements (e.g., square each number).  
  - `filter`: Returns elements that meet a condition (e.g., find odd numbers).  
  - `find`: Returns the first element that satisfies a condition.  

- **Difference between `let`, `const`, and `var` scope?**  
  - `var` supports hoisting → initialized as `undefined` before declaration.  
  - `let` & `const` → Reference error if used before declaration.  
  - `const` has block scope and holds a constant reference (objects/arrays can be modified).  
- **Spread operator?** → Used to update objects. Example:  
  ```js
  const student = { name: 'ravi', place: 'Sahibganj', age: 33 };
  let StudentOne = { ...student, name: 'Kumar' };
  ```  
- **JavaScript: Single-threaded or multi-threaded?**  
  - JavaScript is **single-threaded**, uses **FIFO**.  
  - Asynchronous behavior is handled via Promises and Callbacks.  
- **Event Loop?**  
  - Moves execution context from call stack to call stack.  
  - Monitors the call stack and executes when empty.  
  - **Microtask queue (fetch API)** has higher priority than **callback queue (setTimeout)**.  
- **Closures?** → A function inside another function can access its parent's variables. Example:  
  ```js
  function x() {
      let a = 10;
      function y() {
          console.log(a);
      }
      return y;
  }
  var z = x();
  z(); // Output: 10
  ```  
- **Function Currying?** → Transforming a function with multiple arguments into nested functions. Example:  
  ```js
  var x = (a) => (b) => a * b;
  console.log(x(2)(3)); // Output: 6
  ```  
- **Number Digit Sum until Single Digit?**  
  ```js
  function convertSingleDigit(n) {
      let arr = [...`${n}`].map(Number);
      let sum = arr.reduce((acc, num) => acc + num, 0);
      return sum > 9 ? convertSingleDigit(sum) : sum;
  }
  console.log(convertSingleDigit(5431)); // Output: 4
  ```

- **Precedence in Event Loop?**  
  - `Promise` executes first because it is in the **Microtask Queue**.  
  - `setTimeout` executes later in the **Callback Queue**.  
- **`setTimeout` vs `setInterval`?**  
  - `setTimeout`: Runs once after the timer expires.  
  - `setInterval`: Runs repeatedly at the specified interval.  
  - **Stopping `setInterval`** → Use `clearInterval(intervalId)`.  
- **ES6 Features?**  
  - `let`, `const`, arrow functions, spread/rest operators, template literals, promises.  
- **Rest Operator?** → Used in function parameters. Example:  
  ```js
  function demo(name, age, ...rest) {
      console.log(rest);
  }
  ```  
- **Palindrome Check?** → Use `.reverse()` to compare original and reversed strings.  
- **Reverse Function in JavaScript?**  
  ```js
  function reverseString(str) {
      return str.split("").reverse().join("");
  }
  console.log(reverseString("abcba")); // Output: abcba
  ```  
- **Shallow Copy vs Deep Copy?**  
  - **Shallow Copy** → Copies references (`=` assignment).  
  - **Deep Copy** → Creates a completely new copy (e.g., `JSON.parse(JSON.stringify(obj))`).  
- **Closures?** → Functions that remember variables from their lexical scope.  
- **`map` vs `reduce`?**  
  - `map`: Transforms each element in an array.  
  - `reduce`: Accumulates values using an accumulator and current value.  
- **Promises vs Callbacks?**  
  - Promises improve readability & manage async operations with `.then()` and `.catch()`.  
  - Promises have **3 states** → Pending, Resolved, Rejected.
- **Function `fun1()` Execution?**  
  ```js
  function fun1() {
      setTimeout(() => {
          console.log(x);
          console.log(y);
      }, 3000);
      var x = 2;
      let y = 7;
  }
  fun1();
  ```
  **Output:**  
  - `var x` gets **hoisted** but initialized as `undefined`.  
  - `let y` is **not accessible before declaration**.  
  - Error if `y` were accessed before initialization inside `setTimeout()`.  
  - Expected output: **`2, 7`** (since `setTimeout` executes after 3 seconds).  

- **Object Key Behavior in JavaScript?**  
  ```js
  let x = {}, y = { name: "Ronny" }, z = { name: "Jhon" };
  
  x[y] = { name: "Vivek" };
  x[z] = { name: "Akki" };
  
  console.log(x[y]); // {name: 'Akki'}
  console.log(x[z]); // {name: 'Akki'}
  console.log(x);    // {[object Object]: {name: 'Akki'}}
  ```
  **Explanation:**  
  - JavaScript **object keys must be strings**.  
  - `{}` objects (`y` and `z`) are implicitly converted to `"[object Object]"`.  
  - `x["[object Object]"]` is overwritten with `{ name: "Akki" }`.  
- **Why use `console.log()` in projects?**  
  - Used for **debugging and testing**.  
  - Helps check **what data is arriving** in a function or component.  

- **How to disable excessive `console.log()` in large projects?**  
  - Since `console` is part of the `window` object, you can **override** it:  
    ```js
    if (process.env.NODE_ENV === "production") {
      console.log = () => {};
    }
    ```  
  - Alternatively, use **log management tools** like `winston` or `log4js`.  

- **Use of ES6 in React?**  
  - `let` & `const` (Block-scoped variables).  
  - Arrow functions (`() => {}` syntax).  
  - Destructuring (`const {name} = user`).  
  - Promises (`fetch(url).then(res => res.json())`).  
  - Callback functions (`setTimeout(() => {...}, 1000)`).  

- **What is ECMAScript?**  
  - A **standard** for JavaScript.  
  - JavaScript follows **ECMAScript rules** (e.g., ES6 introduced `let`, `const`, arrow functions).  

- **`let` vs. `const` vs. `var`**  
  | Feature | `var` | `let` | `const` |
  |---------|------|------|-------|
  | Scope | **Function scoped** | **Block scoped** | **Block scoped** |
  | Hoisting | Yes (undefined) | Yes (Temporal Dead Zone) | Yes (TDZ) |
  | Reassignable? | Yes | Yes | **No** |
  | Redeclarable? | Yes | **No** | **No** |
  | Must initialize? | No | No | **Yes** |

  ```js
  var x = 10; // Function-scoped
  let y = 20; // Block-scoped
  const z = 30; // Block-scoped and cannot be reassigned
  ```

- **Spread Operator (`...`)**  
  ```js
  const a = [1, 2];
  const b = [3, 4];
  const c = [...a, ...b]; // [1, 2, 3, 4]
  ```

- **Arrow Functions**  
  ```js
  let numbers = [4, 2, 6];
  numbers.sort((a, b) => b - a); // Correct, implicit return
  ```

---

### **4) JavaScript Timing Functions**  
- **`setTimeout()` vs. `setInterval()`**  
  | Function | Behavior |
  |----------|---------|
  | `setTimeout(fn, ms)` | Executes **once** after `ms` milliseconds |
  | `setInterval(fn, ms)` | Executes **repeatedly** every `ms` milliseconds |
  | `clearInterval(id)` | Stops `setInterval()` |

  ```js
  const intervalId = setInterval(() => console.log("Hello"), 1000);
  setTimeout(() => clearInterval(intervalId), 5000); // Stops after 5s
  ```

---

### **5) Count the Highest Occurrence in an Array**  
```js
const arr = [1, 1, 2, 3, 1, 4];
const count = {};

for (const num of arr) {
  count[num] = (count[num] || 0) + 1;
}

console.log(count);
// Output: { '1': 3, '2': 1, '3': 1, '4': 1 }
```

To find the **most frequent number**:
```js
const maxOccurrence = Object.entries(count).reduce((max, curr) => 
  curr[1] > max[1] ? curr : max
);

console.log(`Most Frequent: ${maxOccurrence[0]}, Occurrences: ${maxOccurrence[1]}`);
// Output: Most Frequent: 1, Occurrences: 3
```

- **Sort an object array in ascending order**  
  - Using `.sort()` to compare object properties (`objArray.sort((a, b) => {...})`).  
- **Extracting parts and query params from a URL (`www.google.com/45/?id=89`)**  
  - Using `URL`, `URLSearchParams`, and `useSearchParams()`.  
- Regular function vs arrow function: bind, simple ES6.
- Callback function: pass a function as an argument and return a value.
- Recursive function: function calling itself—for example, summing numbers recursively.
1. What is EventBubbling and EventLooping in JavaScript?
   - EventLoop: Handles asynchronous data.
   - EventBubbling: When there is an event triggered, nested elements are handled by the parent DOM.  
     - Tries to handle by `EVENTHANDLES`, then bubbles to the parent element & continues till it reaches the root.  
     - Use `event.stopPropagation`.  
     - Example: When you try to hit a button, there are multiple events defined on the same button.
6. Closure: Hiding your code data security.  
7. Var vs Let: Hoisting.
1. 
```javascript
function x(){
    setTimeout(() => {
        console.log(i);
    }, 1000)
    var i = 10;
}
x(); // Output: 10
```
2. `setTimeout()` example output:
   - Set timeout calls:
     ```javascript
     setTimeout(() => { console.log(2); }, 1000);
     setTimeout(() => { console.log(1); }, 1);
     // Output: 1, 2
     ```
3. How to store nested objects in an array using recursive functions.
1. 
```html
<body>
    <h1 class='heading'>hello</h1>
</body>
h1 { color: blue; }
h1 { color: red; }
```
Explanation: The second CSS rule (`color: red`) will override the first, applying the red color to the `<h1>` element due to the cascade order.

2. What is a class in JavaScript in ES6?  
   - Before ES6, classes existed in the form of functions.  

3. Constructor function in JavaScript and how to create a new object:  
   ```javascript
   function person(name, age) {
       this.name = name;
       this.age = age;
   }
   var person1 = new person('Ravi', 23);
   ```
   Explanation: The `person` function is used as a constructor to create new instances with `new`, setting `name` and `age` properties for `person1`.

4. What is closure?  

5. Find the unique data in an array list:
   - Using `Set`:
     ```javascript
     const input = [2, 3, 5, 6, 7, 3, 4, 5, 3];
     const unique = [...new Set(input)];
     ```
   - Using iteration:
     ```javascript
     const uniqueArray = [];
     for (let i = 0; i < input.length; i++) {
         if (!uniqueArray.includes(input[i])) {
             uniqueArray.push(input[i]);
         }
     }
     ```

6. Deep copy example:
   ```javascript
   let a = { name: "test" };
   let b = { ...a }; // Deep copy
   b.name = 'test2';
   // a = "test"
   // b = "test2"
   ```

7. Deep copy with nested object example:
   ```javascript
   let a = { name: "test", add: { code: 1 } };
   let b = { ...a };
   b.add.code = 2;
   // Both `a` and `b` will have the same `add.code` value due to shallow copying of nested objects.
   ```

8. Polyfill for `Promise.all`.

1. **Filter JSON data based on age and print in HTML**:
   ```javascript
   const element = [
       { name: 'ravi', age: 30 },
       { name: 'avi', age: 20 },
       { name: 'vi', age: 25 },
       { name: 'iravi', age: 35 }
   ];

   const container = document.getElementById('myelement');

   const res = element.filter(item => item.age < 26);
   console.log(res);

   res.map(item => {
       const p = document.createElement('p');
       p.textContent = `Name : ${item.name} ===> Age: ${item.age}`;
       container.appendChild(p);
   });
   ```

2. **What is the `onBlur` function?**  
   - The `onBlur` function is triggered when a user moves focus away from an element (e.g., clicking elsewhere after typing in a text box).  

3. **Write `console.log()` using Document** (Incomplete example provided: `Const container =`).

4. **Prototype Output**:
   ```javascript
   EmployeeName.prototype = {
       names: [],
       showNames: function () {
           return this.names;
       }
   };
   var e1 = new EmployeeName();
   e1.names.push("foo"); // "foo"
   console.log(e1.showNames());

   var e2 = new EmployeeName();
   e2.names.push("bar"); // "foo bar" - e2 accesses e1's names
   console.log(e2.showNames());
   ```

5. **Write a Promise which resolves if a number is less than 4, else rejects**:
   ```javascript
   const myPromise = new Promise((resolve, reject) => {
       let value = 6; // Change value to test
       if (value < 4) resolve("Value is less than 4");
       else reject("Value is greater than 4");
   });

   myPromise
       .then(res => console.log("Resolved:", res))
       .catch(err => console.log("Error on rejection:", err));
   // Output: Error on rejection: Value is greater than 4
   ```
### **Progressive Web Apps (PWA)**
6. **What are Progressive Web Apps (PWAs)?**
   - PWAs allow websites to run offline like mobile apps.
   - Optimize web app performance by minifying code and reducing file sizes using tools like Google Insights/DevTools.

7. **Service Worker**:
   - A service worker is a JavaScript file that enables offline support for websites.
   - Service workers run in a separate thread from the main web page thread and are event-driven.
   - They support background processing, background sync, caching, and offline functionality.

1. 
```javascript
var a = 10;
{
    var a = -10;
}
let b = a;
{
    let b = -20;
}
console.log(b); // Output: -10
```

2. 
```javascript
c = 25;
var c;
console.log(c); // Output: 25
```

3. Object-Oriented Programming (OOP):
   - **Polymorphism**: Different forms.
   - **Abstraction**: Hide complexity.
   - **Encapsulation**: Follow a defined process (e.g., putting petrol in a petrol car).
   - **Inheritance**: Features of the parent are used in the child component via `super`.

4. **Properties of a class**: Can functions be properties?  
   Example:
   ```javascript
   class Example {
       // Instance field
       name = "Instance Field";

       // Static property
       static staticName = "Static Field";

       // Instance method
       sayHello() {
           console.log("Hello!");
       }

       // Arrow function as a class property
       arrowFunction = () => {
           console.log("Bound to instance automatically");
       };

       // Static method
       static staticMethod() {
           console.log("I am a static method");
       }
   }
   ```

1. **Explain `var`, `let`, and `const` with respect to Hoisting**:  
   - `var`: Hoisted with `undefined` as the default value. Accessible before initialization but results in `undefined`.  
   - `let` & `const`: Hoisted but not initialized. Accessing them before their initialization results in a `ReferenceError`.

2. **Output Question**:
   ```javascript
   obj1 = {a: 10};
   const obj2 = obj1;
   obj2.a = 20;
   console.log(obj1); // ReferenceError due to missing `let obj1` initialization.
   console.log(obj2);
   let obj1; // Error: Cannot access 'obj1' before initialization.
   ```

3. **What is Deep Copy and Shallow Copy?**  
   - **Shallow Copy**: Copies the object, but nested objects retain references. Changes in nested objects affect both copies.  
   - **Deep Copy**: Creates a completely new instance, including nested objects, ensuring no shared references.

4. **Shallow Copy Example Using Spread Operator**:
   ```javascript
   let o1 = { a: 1 };
   let o2 = { ...o1 };
   console.log(o1 == o2); // false
   console.log(o1 === o2); // false
   // Explanation: Spread operator creates a new object, but primitives like `a` are copied by value, not reference.
   ```

5. **Null vs Undefined**:
   ```javascript
   console.log(null == undefined); // true (allows coercion).
   console.log(null === undefined); // false (strict equality check).  
   // Falsy values: false, 0, -0, "", '', ``, null, undefined, NaN.
   ```

6. **Multiply Function with Currying**:
   - Using arrow functions:
     ```javascript
     let mul = a => b => c => a * b * c;
     ```
   - Using regular functions:
     ```javascript
     function mul(a) {
         return function(b) {
             return function(c) {
                 return a * b * c;
             }
         }
     }
     ```

7. **Map, Reduce, and Filter**:
   - `map`: Transforms each array element and returns a new array.
   - `reduce`: Aggregates array elements into a single value (e.g., sum).
   - `filter`: Returns a new array with elements meeting a condition.
  
1. **Difference between `let`, `var`, and `const`:**  
   - `var`: Hoisted with undefined, globally scoped or function scoped.  
   - `let`: Hoisted but not initialized, block scoped.  
   - `const`: Hoisted but not initialized, block scoped, immutable references.  

2. **Output 1, 2 without using `let`:**  
   ```javascript
   function print(i) {
       setTimeout(function() { console.log(i); }, 1000);
   }
   for (var i = 0; i <= 2; i++) { print(i); }
   ```

3. **Types of Copy (Shallow vs Deep):**  
   - **Shallow Copy:** Copies the object but nested objects retain references.  
   - **Deep Copy:** Creates completely new instances of both the object and its nested objects.  

4. **Map vs Filter:**  
   - `map`: Transforms each element in an array and returns a new array.  
   - `filter`: Filters elements based on a condition and returns a new array.

5. **Prototype and How It Works?**  
   - A prototype is an object that other objects can inherit properties from. Methods on prototypes are shared across instances.

6. **Arrow Function and Advantages:**  
   - Arrow functions don’t have their own `this`. Instead, they inherit `this` from the closest enclosing scope.  
   - No `arguments` object—use the rest operator instead.  
   - Concise syntax, not hoisted.

7. **Bind vs Call vs Apply:**  
   - `bind`: Creates a new function with a specified `this` context.  
   - `call`: Invokes a function with a specified `this` context and arguments as a list.  
   - `apply`: Invokes a function with a specified `this` context and arguments as an array.

8. **Difference Between Spread and Rest Operators:**  
   - Spread (`...`): Expands elements or objects into individual components.  
   - Rest (`...`): Collects multiple elements into a single array or object.  

9. **Get Second Last Element from Array:**  
   ```javascript
   let arr = ["a", "b", "c", "d", "e", "f"];
   console.log(arr[arr.length - 2]); // Output: "e"
   ```

10. **Output:**
    ```javascript
    console.log(3 + "3"); // Output: "33"
    console.log(3 - "3"); // Output: 0
    ```
1. **What are higher-order functions?**  
   - Functions that take other functions as arguments or return functions. Examples include `map`, `reduce`, and `filter`.

2. **Global Execution Context:**  
   - The default execution context where variables and functions are globally scoped.

3. **Lexical Scoping:**  
   - A concept where a function can access variables defined in its outer scope.

4. **Program to Find Occurrence of Array Elements:**  
   ```javascript
   const arr = [2, 3, 2, 4, 3, 2];
   const occurrences = arr.reduce((acc, num) => {
       acc[num] = (acc[num] || 0) + 1;
       return acc;
   }, {});
   console.log(occurrences); // Output: {2: 3, 3: 2, 4: 1}
   ```

5. **Program to Create Sub-Array of Repeating Elements:**  
   ```javascript
   const arr = [2, 3, 2, 4, 3, 2];
   const repeated = arr.filter((item, index, self) => self.indexOf(item) !== index);
   console.log(repeated); // Output: [2, 3, 2]
   ```

1. **Flatten Array**:
   ```javascript
   function flattenArray(arr) {
       let flattened = [];
       for (let i = 0; i < arr.length; i++) {
           if (Array.isArray(arr[i])) {
               let subArr = flattenArray(arr[i]);
               for (let j = 0; j < subArr.length; j++) {
                   flattened.push(subArr[j]);
               }
           } else {
               flattened.push(arr[i]);
           }
       }
       return flattened;
   }
   const arr1 = [1, 2, [3, 4], [4, 5, [7, 8]]];
   console.log(flattenArray(arr1)); // Output: [1, 2, 3, 4, 5, 7, 8]
   ```

2. **Difference Between Promise and Async/Await**:
   - **Promise**: Manages asynchronous code by chaining `.then()` callbacks.  
   - **Async/Await**: Latest syntax for asynchronous calls, makes code cleaner and easier to read. Await pauses the execution until the promise resolves.  

3. **Hoisting**:
   - Variables declared with `var` are hoisted with `undefined`.  
   - Variables declared with `let`/`const` are hoisted but not initialized.  
   - Functions are hoisted with their definitions.  

4. **For Loop Output Using `setTimeout`**:
   ```javascript
   for (var i = 0; i < 3; i++) {
       setTimeout(function() {
           console.log("Inside: ", i);
       }, 1000);
   }
   // Output: "Inside: 3" printed 3 times due to var being global-scoped.
   // Corrected using closure:
   for (var i = 0; i < 3; i++) {
       (function(i) {
           setTimeout(function() {
               console.log("Inside: ", i);
           }, 1000);
       })(i);
   }
   ```

5. **Call Stack**:
   - A data structure that manages function execution. Functions are added to the stack when called and removed after execution.  
   - Memory and code execution follow lexical/global scope rules.  

6. **Asynchronous Call Stack**:
   - The async call stack allows promises and `async` calls to resolve without blocking the main thread. A `Task Queue` handles callbacks and pushes them to the stack once it’s clear.

7. **Reverse String**:
   ```javascript
   let str = "hello world";
   let reversed = str.split("").reverse().join("");
   console.log(reversed); // Output: "dlrow olleh"
   ```
1. **Fibonacci Series:**
   ```javascript
   function fibonacci(n) {
       if (n <= 1) return n;
       return fibonacci(n - 1) + fibonacci(n - 2);
   }
   console.log(fibonacci(5)); // Output: 5
   ```

2. **Design Patterns in JavaScript:**
   - Examples: Singleton, Factory, Module, and Observer patterns.

1. **Constant Array Modification:**
   ```javascript
   const arr = [1, 2, 3];
   console.log(arr);
   arr.push(4); 
   console.log(arr); // Output: [1, 2, 3, 4] (reference remains constant, values can change)
   ```

2. **Using `var` in Loops and Correcting for Proper Output:**
   ```javascript
   for (var i = 0; i <= 5; i++) {
       setTimeout(() => {
           console.log(i);
       }, 1000);
   }
   // Output: 6, 6, 6, 6, 6, 6 (all references point to the same i)

   // To get 0, 1, 2, 3, 4, 5:
   for (let i = 0; i <= 5; i++) {
       setTimeout(() => {
           console.log(i);
       }, 1000);
   }
   ```

3. **Spread Operator Usage:**
   ```javascript
   const arr = [1, 2, 3];
   const arr2 = [3, 4, 5];
   const arr3 = [...arr, 7, 9, 10, ...arr2];
   console.log(arr3); // Output: [1, 2, 3, 7, 9, 10, 3, 4, 5]
   ```

   - **As function arguments:**
     ```javascript
     function getSum(...nums) {
         return nums.reduce((sum, num) => sum + num, 0);
     }
     console.log(getSum(1, 2, 3)); // Output: 6
     ```
6. **Object Chaining and Null Check:**  
   - Use optional chaining (`?.`) or ternary (`?:`) to check for null values:  
     ```javascript
     const obj = null;
     const value = obj?.key || "default";
     console.log(value); // Output: "default"
     ```

1. **String Manipulation and Reversal**:
   - Replace strings using:
     ```javascript
     let res = str.replace(/hello/g, 'hello Shaket');
     ```
   - Reverse entire string:
     ```javascript
     const ReverseString = str => [...str].reverse().join('');
     console.log(ReverseString("Geeks for Geeks")); // Output: "skeeG rof skeeG"
     ```
   - Reverse each word in a string:
     ```javascript
     function wordsReverser(str) {
         return str.replace(/[a-zA-Z]+/gm, function(item) {
             return item.split('').reverse().join('');
         });
     }
     console.log(wordsReverser("This is fun, hopefully."));
     // Output: "sihT si nuf ,yllufepoh"
     ```

2. **Reverse Function Using Loops**:
   ```javascript
   function reverse(s) {
       var o = '';
       for (var i = s.length - 1; i >= 0; i--)
           o += s[i];
       return o;
   }
   console.log(reverse("Here are those implementation:"));
   ```

3. **Fetch Data from URL**:
   - Example fetching data from `https://jsonplaceholder.typicode.com/posts`:
     ```javascript
     fetch("https://jsonplaceholder.typicode.com/posts")
         .then(response => response.json())
         .then(data => {
             data.forEach(post => {
                 const card = document.createElement("div");
                 card.className = "card";
                 card.innerHTML = `<h2>${post.title}</h2><p>${post.body}</p>`;
                 document.body.appendChild(card);
             });
         });
     ```

6. **Object Reference Example:**
   ```javascript
   const a = { firstName: "John" };
   const b = a;
   b.lastName = 'Cena';
   b.gender = 'Male';
   console.log(a); // { firstName: "John", lastName: "Cena", gender: "Male" }
   console.log(b); // { firstName: "John", lastName: "Cena", gender: "Male" }
   ```
   - Since objects are passed by reference, both `a` and `b` share the same memory address.

7. **`null == undefined` Output and Difference:**
   - Output:
     ```javascript
     console.log(null == undefined); // true (type coercion)
     console.log(null === undefined); // false (strict comparison)
     ```
   - Differences:
     - `''`: A non-empty string is a valid string.  
     - `null`: Represents the absence of a value (explicitly set).  
     - `undefined`: Represents a variable that has been declared but not initialized.

8. **`useStrict` in JavaScript:**
   - Enables strict syntax checking, restricts the binding of `this`, and prevents silent errors.

9. **Find Only Non-Null Keys:**
   ```javascript
   const obj1 = {
       key1: 'test1',
       key2: 'test2',
       key3: 'test3',
       key4: '',
       key5: false
   };

   function findNonEmptyKeys(obj) {
       const nonEmptyKeys = [];
       for (let key in obj) {
           if (obj[key] !== '' && obj[key] !== null && obj[key] !== undefined) {
               nonEmptyKeys.push(key);
           }
       }
       return nonEmptyKeys;
   }

   console.log(findNonEmptyKeys(obj1)); // Output: ['key1', 'key2', 'key3']
   ```

10. **Delete Keys from an Object:**
    ```javascript
    const employee = { firstname: "John", lastname: "Doe" };
    delete employee.firstname;
    console.log(employee); // { lastname: "Doe" }
    ```

11. **Array Usage:**
    - Push elements to the back:
      ```javascript
      const arr = [1, 2];
      arr.push(3); // [1, 2, 3]
      ```
    - Add elements to the front:
      ```javascript
      arr.unshift(0); // [0, 1, 2, 3]
      ```
    - Insert elements using splice:
      ```javascript
      arr.splice(1, 0, 5); // [0, 5, 1, 2, 3]
      ```

12. **Use of `this` Operator:**
    - Refers to the owner of the function or object in the current context.

5. **FizzBuzz Loop**:
   ```javascript
   for (let i = 1; i < 100; i++) {
       if (i % 15 === 0) {
           console.log('fizzbuzz');
       } else if (i % 3 === 0) {
           console.log('fizz');
       } else if (i % 5 === 0) {
           console.log('buzz');
       } else {
           console.log(i);
       }
   }
   ```

6. **Display Character Count While Typing**:
   Example implementation:
   ```javascript
   const textarea = document.getElementById("text");
   const characterCount = document.getElementById("character-count");

   textarea.addEventListener("input", (event) => {
       characterCount.textContent = event.target.value.length;
   });
   ```

7. **Event Delegation**:
   - A technique where you add an event listener to a parent element and let events propagate from child elements. Improves performance for dynamic DOM manipulation.

8. **Promise vs Callback**:
   - **Callback**: Functions passed as arguments to execute after an operation finishes.
   - **Promise**: A modern approach to handling asynchronous tasks, providing `.then()` and `.catch()` chaining for readability.

10. **Difference Between Local Storage and Session Storage**:
   - **Local Storage**: Persists data even after the browser is closed.  
   - **Session Storage**: Stores data temporarily for the session and clears it after the browser or tab is closed.


4. **Behavior of `this` in Arrow vs Normal Functions**:
   - **Normal Function**: Uses the context in which the function is called (e.g., the `obj` object).
   - **Arrow Function**: Lexically binds `this` to the scope in which it was defined (e.g., the global scope).  
     Example:
     ```javascript
     const obj = {
         value: "Inner",
         normal: function() {
             console.log(this.value); // "Inner"
         },
         arrow: () => {
             console.log(this.value); // "undefined"
         }
     };
     obj.normal();
     obj.arrow();
     ```

5. **Memory Leakage**:
   - Memory leakage occurs when objects are not freed or released properly.
   - Example using closures:
     ```javascript
     function createClosure() {
         let data = "Memory Leak";
         return () => console.log(data);
     }
     let closure = createClosure();
     closure(); // Output: "Memory Leak"
     closure = null; // Free up memory
     ```

6. **Event Loop**:
   - JavaScript uses a single-threaded event loop to manage asynchronous operations by adding tasks to a queue and processing them one by one.

7. **Foreach vs Map**:
   - **Foreach**: Iterates over each element, does not return a new array. Typically used for side effects like updating the DOM.
     Example:
     ```javascript
     arr.forEach(item => console.log(item * 2));
     ```
   - **Map**: Iterates and transforms elements, returning a new array.
     Example:
     ```javascript
     const result = arr.map(item => item * 2);
     console.log(result); // Output: [2, 4, 6, 8]
     ```

5. **Browser Object Model (BOM):**  
   - BOM refers to the browser-related APIs provided by JavaScript for interacting with the browser. Examples:  
     - `window` object.  
     - Methods like `alert()`, `prompt()`, and `confirm()`.  
     - Access to `navigator`, `location`, and `history` objects.

6. **Map Object vs Object:**  
   - **Map Object**:  
     - Allows any value type as keys (e.g., objects, functions).  
     - Maintains the order of key-value pairs.  
     - Example:
       ```javascript
       const map = new Map();
       map.set('key1', 'value1');
       ```
   - **Object**:  
     - Keys are always strings or symbols.  
     - Does not guarantee order.

7. **For-In vs For-Of:**  
   - `for-in`: Loops over enumerable properties of an object.
     ```javascript
     const obj = { a: 1, b: 2 };
     for (const key in obj) {
         console.log(key, obj[key]); // Logs keys and values of the object
     }
     ```
   - `for-of`: Loops over iterable objects like arrays.
     ```javascript
     const arr = [1, 2, 3];
     for (const value of arr) {
         console.log(value); // Logs each value in the array
     }
     ```

8. **Event Curry:**  
   - Currying is a technique where a function is broken into multiple functions, each taking a single argument.  
   - Usage: Improves readability, reusability, and helps prevent errors.  
   - Example:
     ```javascript
     const multiply = (a) => (b) => a * b;
     const multiplyByTwo = multiply(2);
     console.log(multiplyByTwo(5)); // Output: 10
     ```


11. **`var` Example (Hoisting):**
    ```javascript
    var x = 21;
    function xyz() {
        console.log(x); // Output: undefined (due to hoisting of 'var x')
        var x = 20;
    }
    xyz();
    ```

12. **Memory Leakage in JavaScript:**  
    - Memory leaks occur when objects or data are not properly released from memory.  
    - Mitigation Example:
      ```javascript
      let closure = () => console.log("Leaked");
      closure = null; // Clears memory reference
      ```

13. **Difference Between Session Broker and Web Worker:**  
    - **Session Broker:** Works offline to manage session data.  
    - **Web Worker:** Runs in the background on separate threads to improve performance.

14. **Event Propagation vs Immediate Propagation:**  
    - Event propagation consists of `bubbling` and `capturing` phases.  
    - **Immediate Propagation:** Stops event propagation and prevents other event listeners on the same element from being executed.
      ```javascript
      event.stopImmediatePropagation();
      ```

1. **Traffic Light Decision Maker:**
   This function handles the different traffic light colors and their corresponding actions:
   ```javascript
   function TrafficLight(input) {
       if (input === 'red') {
           console.log('Not Allowed to Move, stay behind the cross line');
       } else if (input === 'green') {
           console.log('Keep Moving');
       } else if (input === 'yellow') {
           console.log('get ready to Move, need to wait for few secs');
           setTimeout(() => {
               console.log('keep moving');
           }, 2000);
       }
   }
   TrafficLight('yellow'); // Call the function with the input 'yellow'
   ```

2. **Reverse a String:**
   - To reverse the string `'get ready to Move'`:
     ```javascript
     const str = 'get ready to Move';
     console.log(str.split('').reverse().join('')); // Output: 'evoM ot ydaer teg'
     ```

   - Alternate looping method for reversal:
     ```javascript
     const str = 'get ready to Move';
     let reversed = '';
     for (let i = str.length - 1; i >= 0; i--) {
         reversed += str[i];
     }
     console.log(reversed); // Output: 'evoM ot ydaer teg'
     ```

1. **Fixing Object Spread Syntax:**
   The spread operator in JavaScript (`...`) is used to clone or merge arrays/objects:
   ```javascript
   const a = { firstName: 'John' };
   const b = { ...a, lastName: 'Cena', gender: 'Male' };
   console.log(a); // Output: { firstName: 'John' }
   console.log(b); // Output: { firstName: 'John', lastName: 'Cena', gender: 'Male' }
   ```
1. **Declarative vs Imperative Programming**:
   - **Declarative**: Focuses on describing *what* you want to achieve without specifying *how* to do it. Examples include React and Redux, which emphasize functional and logical programming.
   - **Imperative**: Specifies *how* to achieve the desired result step by step. Examples include procedural programming and object-oriented programming (OOP).

1. **Sort Based on Values and Remove Duplicates on Key**:
   - Code:
     ```javascript
     const a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}];
     const sortedAndDistinct = [...new Map(a.map(item => [JSON.stringify(item), item]))
         .values()].sort((obj1, obj2) => Object.values(obj1)[0] - Object.values(obj2)[0]);
     console.log(sortedAndDistinct);
     // Output: [{c: 0}, {a: 1}, {b: 2}]
     ```

2. **Check If a Given Number is an Integer Without Using `typeof`**:
   - Using `Math.floor`:
     ```javascript
     const isInteger = (num) => num === Math.floor(num);
     console.log(isInteger(10)); // true
     console.log(isInteger(10.5)); // false
     ```

3. **Object Behavior in Nested Functions**:
   - Code:
     ```javascript
     var myObject = {
         foo: "bar",
         func: function() {
             var self = this;
             console.log("outer func:  this.foo = " + this.foo);
             console.log("outer func:  self.foo = " + self.foo);
             (function() {
                 console.log("inner func:  this.foo = " + this.foo);
                 console.log("inner func:  self.foo = " + self.foo);
             }());
         }
     };
     myObject.func();
     // Output:
     // outer func:  this.foo = bar
     // outer func:  self.foo = bar
     // inner func:  this.foo = undefined
     // inner func:  self.foo = bar
     ```

4. **Flatten Array**:
   - Recursive flattening:
     ```javascript
     const flattenArray = (arr) => 
         arr.reduce((acc, val) => Array.isArray(val) ? acc.concat(flattenArray(val)) : acc.concat(val), []);
     const nestedArray = [1, [2, [3, 4], 5]];
     console.log(flattenArray(nestedArray)); // Output: [1, 2, 3, 4, 5]
     ```

5. **Generics for Reusability**:
   - Code:
     ```javascript
     function getArray<T>(items: T[]): T[] {
         return items.map(item => item);
     }
     const numbers = getArray<number>([1, 2, 3, 4, 5]);
     const strings = getArray<string>(['hello', 'world', 'foo', 'bar']);
     console.log(numbers); // Output: [1, 2, 3, 4, 5]
     console.log(strings); // Output: ['hello', 'world', 'foo', 'bar']
     ```

6. **Class vs Interface**:
   - **Class**:
     - Blueprint for creating objects.
     - Can have both implementation and declarations.
   - **Interface**:
     - Used to define the structure of an object.
     - Cannot include implementation.


1. **Define `.apply()` with Real-Life Example**:
   - `.apply()` calls a function with a given `this` value and arguments provided as an array.  
   - Example:
     ```javascript
     let myFun = function(name, city) {
         console.log("name: " + name + " | city: " + city);
     };

     myFun.apply(null, ["Ravi", "Bangalore"]); 
     // Output: name: Ravi | city: Bangalore
     ```

2. **`Object.assign`: Shallow vs Deep Copy**:
   - **Shallow Copy**: Copies top-level properties, but references for nested objects.
   - Example:
     ```javascript
     const target = { a: 1, b: 2 };
     const source = { b: 4, c: 5 };
     const returnedTarget = Object.assign(target, source);
     console.log(returnedTarget); // Output: { a: 1, b: 4, c: 5 }
     ```
   - **Deep Copy**: Requires external libraries (like Lodash) or manual recursion for nested objects.

3. **Display Object Keys Without a Loop & Find Null Keys**:
   ```javascript
   const user = {
       name: "Balaji",
       age: 23,
       greet: () => "Hello",
       emptyKey: null
   };

   // Display keys
   console.log(Object.keys(user)); // Output: ['name', 'age', 'greet', 'emptyKey']

   // Find null keys
   const nullKeys = Object.keys(user).filter(key => user[key] === null);
   console.log(nullKeys); // Output: ['emptyKey']
   ```


1. **Sort Array**:
   Example for sorting:
   ```javascript
   const arr = [5, 3, 8, 1];
   arr.sort((a, b) => a - b); // Ascending order
   console.log(arr); // Output: [1, 3, 5, 8]
   ```

2. **Closure Example**:
   ```javascript
   function x() {
       var a = 10; // Using var for function scope
       return function y() {
           console.log(a);
       };
   }

   const z = x();
   z(); // Output: 10
   z(); // Output: 10
   // The same `a` value is shared across all calls because of closure.
   ```

3. **Promise Execution Order**:
   ```javascript
   const promise = new Promise((resolve, reject) => {
       console.log(1);
       setTimeout(() => {
           console.log("timerStart");
           resolve("success");
           console.log("timerEnd");
       }, 0);
       console.log(2);
   });
   promise.then((res) => {
       console.log(res);
   });
   console.log(4);
   // Output: 1, 2, 4, timerStart, timerEnd, success
   ```

4. **Call, Bind, Apply**:
   - **Call**: Calls a function with a specific `this` and arguments:
     ```javascript
     function greet(city) {
         console.log(`${this.name} from ${city}`);
     }
     greet.call({ name: "Alice" }, "London"); // Output: Alice from London
     ```
   - **Bind**: Returns a new function:
     ```javascript
     const greetLondon = greet.bind({ name: "Alice" }, "London");
     greetLondon(); // Output: Alice from London
     ```
   - **Apply**: Similar to `call`, but arguments are in an array:
     ```javascript
     greet.apply({ name: "Alice" }, ["London"]); // Output: Alice from London
     ```

5. **Fetch vs Axios for POST Method**:
   - **Using Fetch**:
     ```javascript
     fetch("https://api.example.com/data", {
         method: "POST",
         headers: { "Content-Type": "application/json" },
         body: JSON.stringify({ key: "value" })
     }).then(response => response.json())
       .then(data => console.log(data))
       .catch(error => console.error(error));
     ```
   - **Using Axios**:
     ```javascript
     axios.post("https://api.example.com/data", { key: "value" })
         .then(response => console.log(response.data))
         .catch(error => console.error(error));

1. **Output using Closure**:
   ```javascript
   function count() {
       let num = 0; // Variable is shared between all calls
       return () => ++num;
   }
   const counter = count();
   console.log(counter()); // Output: 1
   console.log(counter()); // Output: 2
   console.log(counter()); // Output: 3
   ```

2. **Memory Leakage**:
   - **Example:**
     ```javascript
     function createLeak() {
         let largeArray = new Array(1000000).fill("leak");
         return function() {
             console.log(largeArray.length);
         };
     }
     let leakyFunction = createLeak();
     leakyFunction(); // Output: 1000000
     ```
   - **Leakage Type**: Closure holds reference to `largeArray`, preventing garbage collection.
   - **Solution**: Set closure variable to `null`:
     ```javascript
     leakyFunction = null; // Removes reference and allows garbage collection
     ```

3. **Inheritance in ES5**:
   ```javascript
   let car = { engine: true };
   let bus = Object.create(car);
   console.log(bus.engine); // Output: true
   ```

4. **Push Multiple Items to Array**:
   - Yes, you can push multiple items:
     ```javascript
     let arr = [1, 2, 3, 4, 5];
     arr.push(6, null); 
     console.log(arr); // Output: [1, 2, 3, 4, 5, 6, null]
     ```

5. **What is Promise?**:
   - An object that represents the eventual completion or failure of an asynchronous operation.
   - **Convert Function to Promise**:
     ```javascript
     const asyncFunction = (input) => new Promise((resolve, reject) => {
         if (input) {
             resolve("Success");
         } else {
             reject("Failure");
         }
     });
     asyncFunction(true).then(console.log).catch(console.error);
     ```


