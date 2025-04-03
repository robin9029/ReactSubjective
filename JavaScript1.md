### ** JavaScript, TypeScript**  
  - `"A" - "B" = NaN`  
  - `"2" - "2" = 0`  
- `"2" + 2 = "22"`  
- **Event loop?** → Call stack, callback queue, Microtask queue (priority-based), provided by browser runtime/Node runtime.   
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
      - Variables declared with `var` are hoisted and initialized with `undefined`.  
      - `let` and `const` are hoisted but not initialized (temporal dead zone).

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
- **Reverse Function in JavaScript?**  
  ```js
  function reverseString(str) {
      return str.split("").reverse().join("");
  }
  console.log(reverseString("abcba")); // Output: abcba
  ```  

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


### **Optimized JavaScript and TypeScript Content**

#### **Core Concepts**
1. **Event Loop**:
   - **Flow**: Call stack, Microtask queue (Promise), Callback queue (setTimeout).
   - **Execution Order**:
     ```javascript
     setTimeout(() => console.log("Timer"), 0);
     Promise.resolve().then(() => console.log("Promise"));
     console.log("Sync Code");
     // Output: Sync Code, Promise, Timer
     ```

2. **Closure**:
   - A function retains access to its parent scope even after the parent function has returned.
     ```javascript
     function closureExample() {
         let a = 10;
         return function () {
             console.log(a);
         };
     }
     const closure = closureExample();
     closure(); // Output: 10
     ```

3. **Promises**:
   - Represent asynchronous operations; have **three states**: Pending, Fulfilled, Rejected.
     ```javascript
     const myPromise = new Promise((resolve, reject) => {
         const value = Math.random() > 0.5 ? "Success" : "Failure";
         value === "Success" ? resolve(value) : reject(value);
     });
     myPromise.then(console.log).catch(console.error);
     ```

4. **Function Currying**:
   - Converting a function with multiple arguments into a series of functions, each taking one argument.
     ```javascript
     const curriedMultiply = (a) => (b) => a * b;
     console.log(curriedMultiply(2)(3)); // Output: 6
     ```

#### **Arrays and Objects**
5. **Unique Elements in an Array**:
   - Using `Set`:
     ```javascript
     const unique = [...new Set([2, 3, 3, 5])];
     console.log(unique); // [2, 3, 5]
     ```

6. **Object Copying**:
   - **Shallow Copy**:
     ```javascript
     const obj = { a: 1, b: { c: 2 } };
     const shallowCopy = { ...obj };
     shallowCopy.b.c = 5;
     console.log(obj.b.c); // Output: 5 (shared reference)
     ```
   - **Deep Copy**:
     ```javascript
     const deepCopy = JSON.parse(JSON.stringify(obj));
     deepCopy.b.c = 10;
     console.log(obj.b.c); // Output: 2 (independent copy)
     ```

7. **Accessing Object Keys**:
   ```javascript
   const obj = { a: 1, b: 2, c: 3 };
   console.log(Object.keys(obj)); // ["a", "b", "c"]
   ```

8. **Sorting an Array of Objects**:
   ```javascript
   const objArr = [{ age: 30 }, { age: 20 }, { age: 25 }];
   objArr.sort((a, b) => a.age - b.age);
   console.log(objArr); // [{ age: 20 }, { age: 25 }, { age: 30 }]
   ```

#### **Functions**
9. **Arrow Functions vs Regular Functions**:
   - Arrow functions don’t have their own `this`; they inherit from the parent scope.
   - Regular functions bind `this` dynamically depending on their context.

10. **Recursive Functions**:
    ```javascript
    function sum(n) {
        return n === 1 ? 1 : n + sum(n - 1);
    }
    console.log(sum(5)); // Output: 15
    ```

#### **String Manipulation**
11. **Palindrome Check**:
    ```javascript
    const isPalindrome = (str) => str === str.split("").reverse().join("");
    console.log(isPalindrome("racecar")); // Output: true
    ```

12. **Filter JSON Data and Display in HTML**:
    ```javascript
    const data = [{ name: "Ravi", age: 30 }, { name: "Avi", age: 20 }];
    const filtered = data.filter((item) => item.age < 26);
    const container = document.getElementById("output");
    filtered.forEach((item) => {
        const p = document.createElement("p");
        p.textContent = `${item.name}: ${item.age}`;
        container.appendChild(p);
    });
    ```

#### **Advanced Topics**
13. **Polyfill for `Promise.all`**:
    ```javascript
    const promiseAll = (promises) =>
        new Promise((resolve, reject) => {
            let results = [];
            let completed = 0;
            promises.forEach((promise, index) => {
                promise.then((value) => {
                    results[index] = value;
                    completed += 1;
                    if (completed === promises.length) resolve(results);
                }).catch(reject);
            });
        });
    ```

14. **Event Bubbling**:
    - Event propagates from child to parent. Use `stopPropagation()` to prevent bubbling.
      ```javascript
      document.getElementById("child").addEventListener("click", (e) => {
          e.stopPropagation();
          console.log("Child clicked");
      });
      ```

15. **Progressive Web Apps (PWAs)**:
    - Enable offline support using Service Workers.
    - Service Worker Example:
      ```javascript
      self.addEventListener("install", (event) => {
          event.waitUntil(caches.open("cache-v1").then((cache) => cache.add("/")));
      });
      ```

#### **Core Concepts**
1. **Output Example**:
   ```javascript
   console.log(3 + "3"); // Output: "33" (string concatenation)
   console.log(3 - "3"); // Output: 0 (type coercion)
   ```

2. **Higher-Order Functions**:
   - Functions that accept other functions as arguments or return them.
     Examples: `map`, `filter`, `reduce`.

3. **Global Execution Context**:
   - The environment where global variables and functions are defined.

4. **Lexical Scoping**:
   - Functions have access to the variables in their outer scope.

---

### **Array and Object Operations**
1. **Find Occurrences in an Array**:
   ```javascript
   const arr = [2, 3, 2, 4, 3, 2];
   const occurrences = arr.reduce((acc, num) => {
       acc[num] = (acc[num] || 0) + 1;
       return acc;
   }, {});
   console.log(occurrences); // {2: 3, 3: 2, 4: 1}
   ```

2. **Find Repeating Elements**:
   ```javascript
   const repeated = arr.filter((item, index, self) => self.indexOf(item) !== index);
   console.log(repeated); // [2, 3, 2]
   ```

3. **Flatten Array**:
   ```javascript
   function flattenArray(arr) {
       return arr.reduce((flat, item) => flat.concat(Array.isArray(item) ? flattenArray(item) : item), []);
   }
   const nested = [1, 2, [3, 4], [5, [6, 7]]];
   console.log(flattenArray(nested)); // [1, 2, 3, 4, 5, 6, 7]
   ```

---

### **Promises and Async/Await**
1. **Promises**:
   ```javascript
   new Promise((resolve, reject) => {
       const success = true;
       success ? resolve("Done!") : reject("Failed!");
   })
   .then((res) => console.log(res))
   .catch((err) => console.log(err));
   ```

2. **Async/Await**:
   ```javascript
   async function fetchData() {
       try {
           const response = await fetch("https://api.example.com");
           const data = await response.json();
           console.log(data);
       } catch (error) {
           console.error(error);
       }
   }
   ```

---

### **Event Loop and Asynchronous Programming**
1. **setTimeout Output**:
   ```javascript
   for (let i = 0; i < 3; i++) {
       setTimeout(() => console.log(i), 1000); // Output: 0, 1, 2 (using let)
   }
   ```

2. **Call Stack & Task Queue**:
   - The **Event Loop** manages execution between the Call Stack and Task Queue.
   - **Microtasks** (`Promise`) have higher priority than **macrotasks** (`setTimeout`).

---

### **String Manipulation**
1. **Reverse a String**:
   ```javascript
   const reverseString = (str) => str.split("").reverse().join("");
   console.log(reverseString("hello")); // "olleh"
   ```

2. **Reverse Words**:
   ```javascript
   const reverseWords = (str) => str.split(" ").map(word => word.split("").reverse().join("")).join(" ");
   console.log(reverseWords("This is fun")); // "sihT si nuf"
   ```

---

### **Object Utilities**
1. **Find Non-Null Keys**:
   ```javascript
   const obj = { a: 1, b: null, c: 2, d: undefined };
   const nonNullKeys = Object.keys(obj).filter((key) => obj[key] != null);
   console.log(nonNullKeys); // ["a", "c"]
   ```

2. **Object Deep Copy**:
   ```javascript
   const obj = { a: 1, b: { c: 2 } };
   const deepCopy = JSON.parse(JSON.stringify(obj));
   ```

---

### **Patterns and Algorithms**
1. **Fibonacci Series**:
   ```javascript
   function fibonacci(n) {
       if (n <= 1) return n;
       return fibonacci(n - 1) + fibonacci(n - 2);
   }
   ```

2. **Find Unique Elements**:
   ```javascript
   const unique = [...new Set([1, 2, 2, 3])];
   console.log(unique); // [1, 2, 3]
   ```

---

### **Core JavaScript Features**
1. **Hoisting**:
   - Variables declared with `var` are hoisted and initialized with `undefined`.  
   - `let` and `const` are hoisted but not initialized (temporal dead zone).

2. **Map vs Filter**:
   - `map`: Transforms each element.
   - `filter`: Returns elements that satisfy a condition.

3. **Spread Operator**:
   ```javascript
   const combined = [...[1, 2], ...[3, 4]];
   console.log(combined); // [1, 2, 3, 4]
   ```

4. **Call, Apply, Bind**:
   - `call`: Calls a function with arguments passed individually.
   - `apply`: Arguments are passed as an array.
   - `bind`: Returns a new function with a specified `this`.


1. **Delete Keys**:
   ```javascript
   const obj = { name: "John", age: 30 };
   delete obj.age;
   console.log(obj); // { name: "John" }
   ```

### **Refined JavaScript and TypeScript Content**

#### **Core Concepts**
1. **`this` Operator**:
   - Refers to the owner of the function or object in the current context.
   - Example:
     ```javascript
     const obj = {
         value: "Inner",
         normal: function() {
             console.log(this.value); // "Inner"
         },
         arrow: () => {
             console.log(this.value); // "undefined" (arrow inherits `this` from parent scope)
         }
     };
     obj.normal();
     obj.arrow();
     ```

2. **FizzBuzz Loop**:
   - A classic program that checks divisibility:
     ```javascript
     for (let i = 1; i <= 100; i++) {
         if (i % 15 === 0) console.log('fizzbuzz');
         else if (i % 3 === 0) console.log('fizz');
         else if (i % 5 === 0) console.log('buzz');
         else console.log(i);
     }
     ```

3. **Memory Leakage**:
   - Occurs when objects are not properly released, causing memory exhaustion.
   - Example:
     ```javascript
     function createClosure() {
         let data = "Memory Leak";
         return () => console.log(data);
     }
     let closure = createClosure();
     closure(); // Outputs: Memory Leak
     closure = null; // Free up memory
     ```

4. **Event Loop**:
   - JavaScript uses a single-threaded event loop to manage asynchronous tasks.
   - **Microtasks** (e.g., `Promise`) have higher priority than **Macrotasks** (e.g., `setTimeout`).

---

### **Data Structures and Manipulations**
5. **Finding Unique Array Elements**:
   - Using `Set`:
     ```javascript
     const unique = [...new Set([1, 2, 2, 3])];
     console.log(unique); // [1, 2, 3]
     ```

6. **Sorting Objects and Removing Duplicates**:
   ```javascript
   const arr = [{a: 1}, {b: 2}, {a: 1}, {c: 0}];
   const sortedDistinct = [...new Map(arr.map(item => [JSON.stringify(item), item])).values()]
       .sort((a, b) => Object.values(a)[0] - Object.values(b)[0]);
   console.log(sortedDistinct); // [{c: 0}, {a: 1}, {b: 2}]
   ```

7. **Flatten Nested Arrays**:
   - Using recursion:
     ```javascript
     const flatten = (arr) => arr.reduce((acc, val) => 
         acc.concat(Array.isArray(val) ? flatten(val) : val), []);
     const nested = [1, [2, [3, 4], 5]];
     console.log(flatten(nested)); // [1, 2, 3, 4, 5]
     ```

---

### **String Manipulations**
8. **Reverse String and Words**:
   ```javascript
   const reverseString = (str) => str.split("").reverse().join("");
   const reverseWords = (str) => str.split(" ").map(word => reverseString(word)).join(" ");
   console.log(reverseWords("Hello World")); // "olleH dlroW"
   ```

---

### **Advanced Topics**
9. **Promise vs Callback**:
   - **Callback**: Functions passed as arguments to handle async tasks.
   - **Promise**: Handles async tasks with `.then()` and `.catch()`:
     ```javascript
     const myPromise = new Promise((resolve, reject) => {
         const success = true;
         success ? resolve("Done!") : reject("Failed!");
     });
     myPromise.then(console.log).catch(console.error);
     ```

10. **Currying Functions**:
    - Breaking functions into smaller functions taking single arguments:
      ```javascript
      const multiply = (a) => (b) => a * b;
      console.log(multiply(2)(3)); // Output: 6
      ```

---

### **Miscellaneous**
11. **Local vs Session Storage**:
    - **Local Storage**: Persists across browser sessions.
    - **Session Storage**: Cleared once the tab is closed.

12. **Event Delegation**:
    - Attaching an event listener to a parent element to handle events for its child elements:
      ```javascript
      document.getElementById("parent").addEventListener("click", (event) => {
          if (event.target.tagName === "BUTTON") {
              console.log("Button clicked!");
          }
      });
      ```
    - ED Propagates CBI
    - ED -a technique that allows you to listen for events on a parent element` always attacks on TOP- parent`
    - EP- Propagation : Event DOM main kise travel karega 2 types top-down and vice versa
        - CP(Capturing Phase)- The event starts from the root and moves down to the target element.`TOP down approach `
        - Bubbling Phase: The event starts from the target element and moves up to the root. ` DOWN to TOP `
    - Immediate Propagation: allows us to prevent other event listeners on the same element
        ` same button has multiple event listeners & want to stop some of of the event of buttion ` 


13. **Deleting Object Keys**:
    ```javascript
    const obj = { name: "John", age: 30 };
    delete obj.age;
    console.log(obj); // { name: "John" }
    ```

15. **Generics for Reusability**:
    - Example in TypeScript:
      ```typescript
      function getArray<T>(items: T[]): T[] {
          return [...items];
      }
      console.log(getArray<number>([1, 2, 3])); // Output: [1, 2, 3]
      console.log(getArray<string>(["A", "B", "C"])); // Output: ["A", "B", "C"]
      ```

### **Refined JavaScript and TypeScript Concepts**

#### **Core Concepts**
1. **Shallow vs Deep Copy (`Object.assign`)**:
   - **Shallow Copy**: Only top-level properties are copied; nested objects retain references.
     ```javascript
     const target = { a: 1, b: { c: 2 } };
     const shallowCopy = Object.assign({}, target);
     shallowCopy.b.c = 3;
     console.log(target.b.c); // Output: 3 (shared reference)
     ```
   - **Deep Copy**: Requires libraries (e.g., Lodash) or manual recursion.
     ```javascript
     const deepCopy = JSON.parse(JSON.stringify(target));
     ```
- **Shallow Copy vs Deep Copy?**  
  - **Shallow Copy** → Copies references (`=` assignment).  
  - **Deep Copy** → Creates a completely new copy (e.g., `JSON.parse(JSON.stringify(obj))`).  
 
2. **Object Key Access and Null Filtering**:
   ```javascript
   const obj = { name: "John", age: 30, greet: () => "Hi", emptyKey: null };
   console.log(Object.keys(obj)); // ['name', 'age', 'greet', 'emptyKey']
   const nullKeys = Object.keys(obj).filter((key) => obj[key] === null);
   console.log(nullKeys); // ['emptyKey']
   ```

#### **Arrays and Data Manipulation**
3. **Sorting an Array**:
   ```javascript
   const numbers = [5, 3, 8, 1];
   numbers.sort((a, b) => a - b);
   console.log(numbers); // [1, 3, 5, 8]
   ```

4. **Closure Example**:
   ```javascript
   function counter() {
       let count = 0;
       return () => ++count;
   }
   const increment = counter();
   console.log(increment()); // 1
   console.log(increment()); // 2
   ```

5. **Push Multiple Items to an Array**:
   ```javascript
   const arr = [1, 2, 3];
   arr.push(4, 5, null);
   console.log(arr); // [1, 2, 3, 4, 5, null]
   ```

#### **Asynchronous Programming**
6. **Promise Execution Order**:
   ```javascript
   const promise = new Promise((resolve) => {
       console.log(1);
       setTimeout(() => {
           console.log("Timer Start");
           resolve("Resolved");
           console.log("Timer End");
       }, 0);
       console.log(2);
   });
   promise.then(console.log);
   console.log(4);
   // Output: 1, 2, 4, Timer Start, Timer End, Resolved
   ```

7. **Promises vs `async/await`**:
   - **Promise Example**:
     ```javascript
     fetch("https://api.example.com")
         .then((res) => res.json())
         .then(console.log)
         .catch(console.error);
     ```
   - **Async/Await Example**:
     ```javascript
     async function fetchData() {
         try {
             const res = await fetch("https://api.example.com");
             const data = await res.json();
             console.log(data);
         } catch (err) {
             console.error(err);
         }
     }
     ```

8. **Convert a Function to a Promise**:
   ```javascript
   const asyncFunction = (input) => new Promise((resolve, reject) => {
       input ? resolve("Success") : reject("Error");
   });
   asyncFunction(true).then(console.log).catch(console.error);
   ```

#### **Function Applications**
9. **Call, Bind, Apply**:
   - **Call**:
     ```javascript
     const greet = function (city) {
         console.log(`${this.name} from ${city}`);
     };
     greet.call({ name: "Alice" }, "London"); // Alice from London
     ```
   - **Bind**:
     ```javascript
     const greetLondon = greet.bind({ name: "Alice" }, "London");
     greetLondon(); // Alice from London
     ```
   - **Apply**:
     ```javascript
     greet.apply({ name: "Alice" }, ["London"]); // Alice from London
     ```

#### **Inheritance and Memory Management**
10. **Inheritance in ES5**:
    ```javascript
    const car = { engine: true };
    const bus = Object.create(car);
    console.log(bus.engine); // true
    ```

11. **Memory Leak Example**:
    ```javascript
    function leakExample() {
        const largeArray = new Array(1000000).fill("leak");
        return () => console.log(largeArray.length);
    }
    let leakyFn = leakExample();
    leakyFn(); // 1000000
    leakyFn = null; // Prevent memory leaks
    ```

#### **Sorting and Unique Elements**
12. **Sort and Remove Duplicates in an Object Array**:
    ```javascript
    const arr = [{ a: 1 }, { b: 2 }, { a: 1 }, { c: 0 }];
    const sortedDistinct = [
        ...new Map(arr.map((item) => [JSON.stringify(item), item])).values(),
    ].sort((x, y) => Object.values(x)[0] - Object.values(y)[0]);
    console.log(sortedDistinct); // [{c: 0}, {a: 1}, {b: 2}]
    ```

#### **Other Applications**

14. **Check for Integer Without `typeof`**:
    ```javascript
    const isInteger = (num) => num === Math.floor(num);
    console.log(isInteger(4)); // true
    console.log(isInteger(4.5)); // false
    ```

15. **Sorting and Finding Unique Data**:
    ```javascript
    const numbers = [4, 2, 2, 5, 5];
    console.log([...new Set(numbers)].sort((a, b) => a - b)); // [2, 4, 5]
    ```

### ** Frequntly asked  JavaScript and TypeScript Concepts**

1. **Scope of `var`, `let`, and `const`**  
   - Temporal Dead Zone: Time between variable memory allocation and initialization.

2. **Callback Hell**  
   - Synchronous vs Asynchronous programming and its relation to callbacks.

3. **Promise**  
   - Representation of eventual completion or failure of an asynchronous operation.  
   - Fetch data using `Promise.all()` and `map`.  
   - Custom promise example to resolve or reject based on a condition.  
   - Comparison: Promise vs Async/Await.  
   - `Promise.all()` fetch API works for parallel execution, but using `Promise.allSettled()` can handle both resolved and rejected promises gracefully.

   ```javascript
   Promise.allSettled([fetch(url1), fetch(url2)]).then((responses) => {
       responses.forEach((res) => console.log(res.status));
   });
   ```


4. **Closure**  
   - Functions with lexical scope that remember their parent function's data and variables.

5. **`this` Keyword**  
   - Behavior depends on how it is called.  

6. **Object Creation Techniques**  
   - Using `Object.assign`, `Object.create`, and prototypes.  
   - Display keys of an object.
   - `Object.create` is preferable for prototypal inheritance. Clarify "polyfill" as an implementation that replicates modern functionality in older environments:
     ```javascript
     if (!Object.create) {
         Object.create = function(proto) {
             function F() {}
             F.prototype = proto;
             return new F();
         };
     }
     ```

7. **`setTimeout` and `setInterval`**  
   - Use with `clearInterval` for stopping intervals.

8. **Call, Apply, Bind**  
   - Passing objects to functions and practical usage.

9. **Event Loop**  
   - Mechanisms: Call stack, Microtask queue, Callback queue.  
   - Optimization strategies - starvation using timeout
   - Include Priority Handling: Microtasks (Promise, Mutation Observer) are executed before Macrotasks (setTimeout, setInterval).

10. **Cookies vs Local Storage vs Session Storage**  

11. **Event Handling**  
   - Delegation, Propagation, Immediate Propagation, Bubbling, Looping.  
   - ED propagates CBI

12. **ES6 Standards**  
   - Features: Template literals, spread/rest operators, destructuring, arrow functions, promises, `let`, `const`, and classes.

13. **Progressive Web App (PWA)**  
   - Offline support using service workers.  
   - Web accessibility standards (AA/AAA compliance).

14. **Interceptors** 
- Expand: Interceptors are middleware (used in Axios) to intercept requests and responses for logging, modifying, or handling errors:
      ```javascript
      axios.interceptors.request.use((config) => {
          console.log("Request sent", config);
          return config;
      });
      ```


15. **Generator Functions**  
   - Use of `yield`, execution pauses and resumes on `next`.  

16. **Deep Copy**  
   - Example: `JSON.parse(JSON.stringify(nestedObject))`.

17. **Event Currying**  
   - Transform functions into callable forms by splitting arguments.  
   - Partial function applications.

18. **Memory Leakage**  
   - Detection using Chrome DevTools memory profiler.  
   - Avoid global variables.
   - Avoid circular references to prevent leaks. Example:
      ```javascript
      const circularObj = {};
      circularObj.self = circularObj; // Break reference by assigning null
      ```


19. **Declarative vs Imperative Programming**  
   - JavaScript supports both paradigms.

20. **Map Object vs Regular Object**  
    - Clarify Map Object benefits:
    - Map maintains order of insertion, accepts any key type, and is iterable.
      ```javascript
      const map = new Map();
      map.set(1, "one");
      console.log(map.get(1)); // Output: "one"
      ```


21. **Global Keys**  
   - Payment/gateway keys stored as `const` (block-scoped) or `var` (global-scoped).

22. **Preventing Textbox Trigger Render**  
   - Debouncing and throttling techniques.  
   - Use `preventDefault()` to stop browser reload.
   - De-bouncing - search is commonly used for scenarios like search input fields
   - Throttling is commonly used for scenarios like handling scroll events

23. **OOP Concepts**  
   - Polymorphism, abstraction, encapsulation, inheritance, and the use of `super`.

24. **Class vs Function**  
   - Constructors in classes vs initial state in functions.  
   - TypeScript: Classes vs interfaces.

25. **Regular Functions vs Arrow Functions**  
   - Features of arrow functions: compact, inherits `this` from outer context, not usable as a constructor.

26. **Map vs ForEach**  
   - Map: Returns a new array, supports chaining.  
   - ForEach: Executes a callback for each element, does not return a new array.

27. **Async to Sync**  
   - Remove callback functions and directly invoke functions.

28. **Web Workers**  
   - Separate threads for complex calculations to improve performance.  
