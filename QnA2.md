
# 1
Here is the grouping of your questions based on the topics you provided:

### **1) HTML**  
- **JSX - Understand by browser?** → No, Babel  

### **2) CSS**  
(No questions related to CSS were mentioned.)  

### **3) Redux, Redux Toolkit**  
- **Middleware, logger?** → Middleware solves the problem of asynchronous calls in Redux. It intercepts actions before they reach the reducer.  
- **I want to dispatch the action and also hit API; once data is retrieved, I want to send this data along with dispatch.**  

### **4) JavaScript, TypeScript**  
- `"A" - "B" = NaN`  
- `"2" - "2" = 0`  
- `"2" + 2 = "22"`  
- **Event loop?** → Call stack, callback queue, Microtask queue (priority-based), provided by browser runtime/Node runtime.  
- **Promise & setTimeout: Which one executes first?** → Promise, because it runs on the Microtask queue.  
- **Prototypes?** → Default constructor, default object created, prototype chain leads to `null`.  
- **`this` keyword?** → Behaves differently in function/global scope, arrow function points to the parent object, strict mode refers to `undefined`, event refers to the element.  

### **5) React.js**  
- **Higher-Order Component (HOC)?** → Returns a function, accepts a function (e.g., `map`, `filter`, `reduce`).  
- **Advantages & disadvantages of React?** → Virtual DOM, fast, easy to debug. Disadvantages: Library (only handles view layer), requires router for routing, Redux for state management.  
- **Can a component re-render without `setState` or without updating?** → Yes, in cases like:  
  1. Parent component re-renders  
  2. Context changes  
  3. Force update  
  4. React Hook dependency changes  
  - List elements: If we pass a `key` attribute, React remembers which keys were deleted, updated, or added for efficient re-rendering.  
- **Lifecycle methods in function components?** → Use `useEffect` (handles side effects and dependencies).  

### **6) Node.js**  
(No specific Node.js-related questions were mentioned.)  

Let me know if you'd like any changes or further grouping! 🚀
# 2
Here is the updated grouping of your questions based on the topics you provided:

---

### **1) HTML**  
- **HTML?** → Layout of web pages.  
- **HTML Layout?** → Header, footer, head, title.  
- **Tags in HTML?** → Determine the content structure (`h1` is highest, `h6` is lowest).  

---

### **2) CSS**  
- **Strong vs Bold?** → `strong` emphasizes importance, `bold` is for highlighting.  
- **Types of CSS?** → External, inline, internal.  

---

### **3) Redux, Redux Toolkit**  
- **Redux flow orally?** → Store → Component → Container (`mapStateToProps` & `mapDispatchToProps`) → Dispatch action → Reducer updates state.  

---

### **4) JavaScript, TypeScript**  
- **JS?** → Used for creating interactive UI applications.  
- **`map` vs `forEach`?** → Both iterate over an array, but `map` creates a new array while `forEach` does not.  
- **`map`, `filter`, `find`?** →  
  - `map`: Transforms elements (e.g., square each number).  
  - `filter`: Returns elements that meet a condition (e.g., find odd numbers).  
  - `find`: Returns the first element that satisfies a condition.  

---

### **5) React.js**  
- **Hooks?** → Lifecycle management, features like `useEffect` (for fetching data & side effects), `useRef`, `useMemo`.  
- **Features of React?** → JSX, one-way data binding, Virtual DOM.  
- **JSX?** → JavaScript XML, allows writing HTML-like syntax in React.  
- **Component?** → Reusable piece of code that can be used anywhere.  
- **Props?** → Pass data from parent to child component.  
- **State vs Props?** →  
  - `state`: Internal data storage (class components).  
  - `props`: Passed from parent to child component.  
- **Real DOM vs Virtual DOM?** → Virtual DOM is a copy of the Real DOM; updates are processed efficiently instead of modifying the entire structure.  
- **React Router?** → Handles navigation between different pages in a React application.  

---

Let me know if this categorization works for you or if you'd like any modifications! 🚀

# 3
Here’s the updated grouping of your questions based on the topics you provided:  

---

### **1) HTML**  
(No new questions related to HTML were mentioned.)  

---

### **2) CSS**  
(No new questions related to CSS were mentioned.)  

---

### **3) Redux, Redux Toolkit**  
- **Redux?** (Mentioned without details, assuming it needs explanation.)  

---

### **4) JavaScript, TypeScript**  
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

---

### **5) React.js**  
- **What is React.js?** → Library for UI development.  
- **State & Props?** →  
  - `state`: Manages component data (`this.state`, `setState`).  
  - `props`: Passes data from **parent to child**.  
- **How to pass data from child to parent?** → Using **callback functions**.  
- **Lifecycle Methods (Class Components)?**  
  - `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`.  
- **`useEffect` Behavior?**  
  - If no second argument (`[]`), runs on every render.  
  - If second argument is `null` or `undefined`, behaves similarly (runs on every render).  

---

### **6) Node.js**  
(No new questions related to Node.js were mentioned.)  

---

This grouping should help you locate topics easily. Let me know if you need any changes! 🚀
# 4
Here's the updated grouping of your questions based on the topics you provided:  

---

### **1) HTML**  
(No new questions related to HTML were mentioned.)  

---

### **2) CSS**  
- **Position attributes?**  
  - `absolute`: Position relative to the nearest positioned (non-static) ancestor.  
  - `fixed`: Stays fixed relative to the viewport.  
  - `relative`: Moves based on its normal document flow.  
- **Flexbox?** → Helps make pages responsive.  
- **`display: none` vs `visibility: hidden`?**  
  - `display: none`: Removes the element from the DOM.  
  - `visibility: hidden`: Hides the element but keeps its space.  

---

### **3) Redux, Redux Toolkit**  
- **Redux & Context API?** → Used for state management.  
- **Middleware - Thunk?** → Intercepts an action before reaching the reducer.  
- **`useSelector` Hook?** → Accesses Redux state. Example:  
  ```js
  import { useSelector } from 'react-redux';
  function MyComponent() {
      const counter = useSelector(state => state.counter);
      return <h1>Counter: {counter}</h1>;
  }
  ```  

---

### **4) JavaScript, TypeScript**  
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

---

### **5) React.js**  
- **Hooks?** → `useState`, `useEffect`, `useReducer`, `useSelector`, `useMemo`, `useCallback`.  
- **`useMemo` vs `useCallback`?**  
  - `useMemo`: Caches **expensive calculations**.  
  - `useCallback`: Caches **functions** to prevent unnecessary re-renders.  
- **Lifecycle Methods?**  
  - `getDerivedStateFromProps` → Called **before render**.  
  - First lifecycle method called? → **Constructor**.  
- **Pure Component?** → Optimizes performance by rendering only when **state or props change**.  
- **Higher Order Component (HOC)?**  
  - A function that **accepts** a component and **returns** a new component. Example:  
  ```js
  const withLogger = (Component) => (props) => {
      console.log("Logging props:", props);
      return <Component {...props} />;
  };
  ```  

---

### **6) Node.js**  
(No new questions related to Node.js were mentioned.)  

---

This refined categorization should help! Let me know if you need any changes. 🚀
# 5
Here’s how your new questions are grouped into the existing categories:

---

### **1) HTML**  
(No new questions related to HTML.)  

---

### **2) CSS**  
(No new questions related to CSS.)  

---

### **3) Redux, Redux Toolkit**  
- **Redux vs `useContext`?**  
  - `useContext` is simpler for small applications.  
  - Redux is **better for complex apps** with multiple data sources and frequent state updates.  

---

### **4) JavaScript, TypeScript**  
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

---

### **5) React.js**  
- **Controlled vs Uncontrolled Components?**  
  - **Controlled**: React manages form state (`useState`).  
  - **Uncontrolled**: DOM manages form state (`useRef`).  

- **Advantages of React Hooks?**  
  - Simplifies lifecycle management.  
  - Reduces boilerplate code.  

- **JSX?**  
  - JavaScript syntax that allows writing HTML-like code inside React.  

- **State vs Props?**  
  - `state`: Internal to a component, can be updated.  
  - `props`: Passed from parent to child, read-only.  

- **Keys in React.js?**  
  - **Helps React identify which items have changed.**  
  - **Incorrect Usage:** Using index as a key (`key={index}`).  
  - **Correct Usage:**  
    ```js
    const list = items.map((item) => <li key={item}>{item}</li>);
    ```  

- **Higher Order Components (HOC)?**  
  - A function that **takes a component** and **returns a new component** with additional features.  
  ```js
  const withLogger = (Component) => (props) => {
      console.log("Logging props:", props);
      return <Component {...props} />;
  };
  ```  

- **Real DOM vs Virtual DOM?**  
  - **Real DOM:** Updates every node → slow.  
  - **Virtual DOM:** Updates only changed elements → fast.  

- **`useMemo`?**  
  - **Prevents unnecessary re-renders.**  
  - **Caches expensive computations.**  
  ```js
  const expensiveCalculation = useMemo(() => {
      return heavyComputation(value);
  }, [value]);
  ```  

- **`useContext`?**  
  - **Global state management without Redux.**  
  - Useful for **small apps** instead of Redux.  

---

### **6) Node.js**  
(No new questions related to Node.js.)  

---

Let me know if you need any refinements! 🚀


# 6 
Here’s how these new questions fit into the existing categories:

---

### **1) HTML**  
(No new questions related to HTML.)  

---

### **2) CSS**  
(No new questions related to CSS.)  

---

### **3) Redux, Redux Toolkit**  
- **What is Redux Thunk?**  
  - A **middleware** that enables handling **asynchronous actions** in Redux.  
  - Example:  
    ```js
    const fetchData = () => {
      return async (dispatch) => {
        const response = await fetch("/api/data");
        const data = await response.json();
        dispatch({ type: "FETCH_SUCCESS", payload: data });
      };
    };
    ```
  - **Why?** Redux’s actions are **synchronous by default**.  

---

### **4) JavaScript, TypeScript**  
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

---

### **5) React.js**  
- **Class Components vs Functional Components?**  
  | Feature | Class Components | Functional Components |
  |---------|-----------------|-----------------------|
  | Syntax | `class Component extends React.Component` | Regular function |
  | State Management | Uses `this.state` | Uses `useState` hook |
  | Lifecycle Methods | `componentDidMount()`, `componentDidUpdate()` | `useEffect()` |
  | Performance | Can be slower due to unnecessary re-renders | Faster, optimized re-renders |
  | Testing | Can be complex due to `this` binding | Easier, behaves like a JS function |

- **When to Use Which?**  
  - **Use Class Components** → When dealing with **complex state logic**.  
  - **Use Functional Components** → When **performance and simplicity** matter.  

- **React Hooks?**  
  - `useEffect` → Handles **side effects & lifecycle management**.  
  - `useState` → Manages **component state**.  
  - `useMemo` → **Optimizes heavy calculations**.  
  - `useRef` → **Access DOM elements and persist values without re-rendering**.  

---

### **6) Node.js**  
(No new questions related to Node.js.)  

---
# 7
Here’s how your new questions fit into the existing categories:

---

### **1) React.js**  
- **Features of React:**  
  - Virtual DOM (Efficient updates, faster UI rendering).  
  - Component-based architecture (Reusable UI).  
  - One-way data binding (Unidirectional data flow).  
  - JSX (Write HTML-like syntax in JavaScript).  
  - High performance (Optimized re-rendering).  

- **One-way data binding:**  
  - Data flows **from state → UI** (not UI → state).  
  - Prevents unintended UI modifications.  

- **Use of Babel:**  
  - **Transpiler** that converts **JSX → JavaScript**.  
  - Helps React run in older browsers.  

- **React: Library vs. Framework?**  
  - React is a **library** (focuses on the **view layer**).  
  - Unlike Angular (a full **framework**), React needs external tools for state management, routing, etc.  

- **Why is function-based React preferred over class components?**  
  - React Hooks (introduced in **v16.8**) made function components more powerful.  
  - **Advantages of function components:**  
    - **Less code** (No `this`, `constructor`, `bind`).  
    - **Better performance** (No unnecessary re-renders).  
    - **Easier state management** (`useState`, `useReducer`).  

- **useState Hook**  
  ```js
  const [state, setState] = useState(initialValue);
  ```

- **Controlled vs. Uncontrolled Components**  
  | Controlled Component | Uncontrolled Component |
  |----------------------|-----------------------|
  | React handles form data | DOM handles form data |
  | Uses `useState()` | Uses `ref` |
  | Example: `<input value={state} onChange={(e) => setState(e.target.value)} />` | Example: `<input ref={inputRef} />` |

- **Prop Drilling?**  
  - When **data is passed down multiple levels** (`A → B → C → D`).  
  - **Issue?** Components **not using the prop** still receive it.  
  - **Solution:** Use **Context API** or **Redux**.  

- **Can we create custom Hooks?**  
  - Yes, **custom Hooks** help reuse logic.  
  - Example:  
    ```js
    function useFetch(url) {
      const [data, setData] = useState(null);
      useEffect(() => {
        fetch(url).then(res => res.json()).then(setData);
      }, [url]);
      return data;
    }
    ```
  
- **React.StrictMode?**  
  - Highlights **deprecated lifecycle methods**.  
  - Warns about **potential issues in components**.  
  - Used **only in development mode**.  
  - Example:  
    ```jsx
    <React.StrictMode>
      <App />
    </React.StrictMode>
    ```  

- **How to pass data between components?**  
  - **Props** (Parent → Child).  
  - **Callback function** (Child → Parent).  
  - **Context API** (Avoid prop drilling).  
  - **Redux** (Global state management).  
  - **Which one is better?**  
    - **Redux** for **large applications**.  
    - **Context API** for **smaller projects**.  

- **Is Redux a caching server?**  
  - No, Redux is a **state management library**, not a caching server.  
  - **For caching, use:**  
    - React Query  
    - Apollo Client (for GraphQL)  
    - Service workers  

- **How does React Router work?**  
  ```jsx
  <BrowserRouter>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
      <Route path="*" element={<NotFound />} /> // Handles unmatched routes
    </Routes>
  </BrowserRouter>
  ```

---

### **2) JavaScript**  
- **Use of ES6 in React?**  
  - `let` & `const` (Block-scoped variables).  
  - Arrow functions (`() => {}` syntax).  
  - Destructuring (`const {name} = user`).  
  - Promises (`fetch(url).then(res => res.json())`).  
  - Callback functions (`setTimeout(() => {...}, 1000)`).  

---

### **3) Database & Node.js**  
- **What is a LEFT JOIN?**  
  - Returns **all records from the left table**, and **matching records from the right table**.  
  - **Example:**  
    ```sql
    SELECT customers.name, orders.order_id
    FROM customers
    LEFT JOIN orders ON customers.id = orders.customer_id;
    ```
  - If a **customer has no orders**, they will still appear in the result with `NULL` values for orders.  

---

Let me know if you need more explanations or examples! 🚀
# 8
Here’s a structured explanation of your topics:  

---

### **1) HTML**  
- **What is `<!DOCTYPE>`?**  
  - It tells the **browser** what version of HTML to expect.  
  - Modern HTML uses:  
    ```html
    <!DOCTYPE html>
    ```
  - **Older versions:**  
    - HTML 4.01 Transitional:  
      ```html
      <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
      ```
    - HTML5 is more **flexible** and does not require a strict DOCTYPE declaration.  

---

### **2) CSS**  
- **CSS vs. CSS3**  
  | Feature | CSS | CSS3 |
  |---------|-----|------|
  | **Modularization** | Single large specification | Split into **modules** for better organization |
  | **Animations** | No built-in animation support | `@keyframes`, `animation` property |
  | **Selectors** | Basic selectors | New selectors: `:nth-child()`, `:not()`, etc. |
  | **Box Model** | Basic box model | `box-sizing: border-box;` to include padding and border |

- **Box Sizing in CSS**  
  - Controls **how width & height are calculated**:  
    ```css
    box-sizing: border-box; /* Includes padding and border inside the element size */
    ```

---

### **3) JavaScript (JS) & ECMAScript (ES6)**  
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

---

Let me know if you need further clarification! 🚀
# 9
Here are your questions grouped by topic:

### **1) HTML**  
- No questions related to HTML in this set.

### **2) CSS**  
- **How to add CSS and JavaScript globally in React JS?**  
  - Using the public folder (`styles.css` in the CSS directory and `app.js` in the JS directory).  
  - Importing CSS inside `index.html` (`<link>` in `<head>`) or via `import * ./src/styles/global.css`.  
  - Importing JavaScript using `<script>` inside `index.html` or using `react-script-tag`.

### **3) Redux, Redux Toolkit**  
- **Redux vs Hooks?**  
  - When to use Redux for state management vs using React Hooks (`useState`, `useReducer`, `useContext`).

### **4) JavaScript, TypeScript**  
- **Sort an object array in ascending order**  
  - Using `.sort()` to compare object properties (`objArray.sort((a, b) => {...})`).  
- **Extracting parts and query params from a URL (`www.google.com/45/?id=89`)**  
  - Using `URL`, `URLSearchParams`, and `useSearchParams()`.  

### **5) React JS**  
- **Creating a button using `createElement` in React**  
  - Example of using `React.createElement()` vs JSX.  
- **Extracting query parameters in React Router**  
  - Using `useSearchParams()` or `URLSearchParams()`.  

### **6) Node JS**  
- No questions related to Node.js in this set.  

Let me know if you need further refinements! 🚀

# 10
Understood! I'll group your questions exactly as they are, without any modifications. Let me reorganize them according to your topics:

### 1. **JavaScript/TypeScript**
- Regular function vs arrow function: bind, simple ES6.
- Callback function: pass a function as an argument and return a value.
- Recursive function: function calling itself—for example, summing numbers recursively.

### 2. **React JS**
- Functional vs class-based components: similarities in lifecycle.
- Call API on mount & unmount:
  - Link: [Handling async React component effects](https://www.benmvp.com/blog/handling-async-react-component-effects-after-unmount/)
  - Link: [Understanding React useEffect cleanup](https://blog.logrocket.com/understanding-react-useeffect-cleanup-function/)
- useRef.
- Routing techniques:
  - Link: [React Router tutorial](https://www.w3schools.com/react/react_router.asp)
  - Example: `BrowserRouter` storing current location & navigating history stack.

### 3. **Node JS**
- Handling crashes:
  - Class: `ErrorBoundary` (componentDidCatch).
  - Function: `useErrorBoundary`.
- Slow internet handling with `registerServiceWorker`.

### 4. **HTML/CSS**
(No specific questions typed yet.)

### 5. **Redux/Redux Toolkit**
(No specific questions typed yet.)

I haven’t changed anything! Let me know if there’s more to add. 😊

# 11
Here’s your updated grouping based on the specified topics. I’ve kept your questions unmodified, as requested:

---

### **JavaScript/TypeScript**
1. What is EventBubbling and EventLooping in JavaScript?
   - EventLoop: Handles asynchronous data.
   - EventBubbling: When there is an event triggered, nested elements are handled by the parent DOM.  
     - Tries to handle by `EVENTHANDLES`, then bubbles to the parent element & continues till it reaches the root.  
     - Use `event.stopPropagation`.  
     - Example: When you try to hit a button, there are multiple events defined on the same button.
6. Closure: Hiding your code data security.  
7. Var vs Let: Hoisting.  

---

### **CSS**
2. Semantic tag in HTML: Have meaningful names and easily readable, e.g., `header`, `footer`, `vertical`.  
3. BOX model: How elements on the webpage can be rendered & calculated (content, padding, border, margin [MBPC]).  
   - Increase space between two elements: Margin.  
   - Content of an element with a border: Padding.  
4. Flexbox: Making the page responsive.  
5. Pseudo classes (`:first-child`, `:hover`) and Pseudo elements (`<p>::first-letter`).  
   - [Documentation Link](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements).  
   - Pseudo classes: Specific to state.  
   - Pseudo elements: Add new HTML elements.

---

### **React JS**
8. Change button color of input onChange event in class-based component.  
9. For every change in the textbox, render triggers—how to prevent that?  
   - Debouncing is commonly used for scenarios like search input fields (wait for the user to finish typing before triggering a search request).  
   - Throttling is used for scenarios like handling scroll events (limit the frequency of function invocations to avoid performance issues).  
   - PreventDefault().  
   - [YouTube Link](https://www.youtube.com/watch?v=h4QOOvzk0UM).  
1. Virtual DOM.  
2. JavaScript engine differences (Chrome V8, SpiderMonkey-Mozilla, Chakra-Microsoft):  
   - Open source and performance differences.  
   - Code parsed—broken into tokens, moved for Interpreter-JIT (Just-In-Time compiler), optimization, and garbage collector.  
3. `setState`: Why we can’t do it directly?  
4. Set default props: If the property is not provided in the parent class, it can fail for null values.  
5. Redux `mapStateToProps`, `mapDispatchToProps`:  
   - Where is your reducer inside? Store.  
   - `mapDispatchToProps`: Dispatch functions go for actions.  
6. Multiple reducer components: How your component identifies which reducer is called?  
   - Use `combineReducers` with key-value pairs.  
   - While accessing state, mention the corresponding key as state inside `mapStateToProps`.  
7. Closure: Data hiding.  
8. Flux: ?  

---

### **Redux/Redux Toolkit**
(No specific questions typed under this topic yet.)

---

### **Node JS**
9. How to increase the performance of your application?  
10. Deployment.  
11. Code quality: How to check if it is high quality—Lighthouse.  
    - Unit testing.  
    - Performance testing.  
    - Jest testing: `toMatchSnapshot` rendering and code coverage.  

Let me know if anything else needs sorting or clarification! 😊
# 12
Here’s how your additional questions align with the specified topics, grouped exactly as provided:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
4. Lifecycle methods—how to convert class-based components into functional components.  
5. Where to call API in Redux—`componentDidMount` or `ACTION`.  
6. Why we need middleware in Redux—to intercept actions:
   - Modifying action payloads, analytics and tracking, error handling, logging and debugging, authentication, and authorization-token refresh.  
7. Differences between React and Next.js:
   - Server-side rendering (SSR), ability to create our API, and fixed rendering.  
9. Testing:
   - Unit testing with tools like Jest and Enzyme.
   - Snapshot testing for all components.
   - Strategies for determining which components go for unit testing.

---

### **CSS**
8. Styling approaches:
   - Using Bootstrap, CSS, Sass, Less, and Material UI.

---

### **Redux/Redux Toolkit**
(No specific questions yet.)

---

### **Node JS**
(No specific questions yet.)

---

### **Other Topics**
10. Requirement for multilingual support (English and Hindi)—globalization libraries like `ES Intlization`.  
11. How to retrieve and display data for individuals whose age is greater than 40.

Let me know if you’d like further clarification or have more questions to add! 😊

# 13
Here's your latest set of questions grouped under appropriate topics, exactly as provided:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
9. Parent-Child JSX example:
   - Parent component:
     ```javascript
     const [state1, setState1] = useState(0);
     const [state2, setState2] = useState(0);
     return <Props state={state1} />;
     ```
   - Child component:
     ```javascript
     return <div>{props.state}</div>;
     ```
   Explanation:
   - If `state1` changes, it will trigger re-rendering for both parent and child components.
   - If `state2` changes, the child component will not re-render.

---

Let me know if you'd like me to expand or reorganize further! 😊
# 14
Here’s your latest set of questions grouped appropriately based on the specified topics. I’ve kept the content unchanged, as requested:

---

### **React JS**
1. Higher-Order Component (HOC)—how it helps and what problem it solves.  
2. Managing data in projects:  
   - Function-based: `useState()`.  
   - Class-based: `setState`.  
   - Using Redux.  
5. Error Boundaries using `componentDidCatch`.  
6. Code splitting—lazy loading.  
7. Custom code to retrieve data and implement error and loading logic using `dummyJson`.  
8. How the code executes within `useEffect()`.

---

### **Redux/Redux Toolkit**
3. Middleware—Redux Thunk.

---

### **Build Tools**
4. Webpack configuration file:  
   - Entry Point: Specifies where webpack starts bundling the application.  
   - Output: Defines the output path and naming pattern for bundled files.  
   - Loaders: Transform different file types during bundling (e.g., Babel for JavaScript, SCSS to CSS). Configured via `module.rules`.  
   - Plugins: Provide additional functionalities like code optimization, minification, environment variables injection, etc. Configured via `plugins`.  
   - Mode: Determines build mode (`development`, `production`, or `none`).  
   - Dev Server: Runs the application locally during development.  
   - Resolve: Specifies how webpack resolves module imports (e.g., aliases, file extensions).  

   Links for reference:  
   - [LogRocket Blog](https://blog.logrocket.com/versatile-webpack-configurations-react-application/)  
   - [Gist on Webpack Configuration](https://gist.github.com/iamshaunjp/a1c8fb653ddd5d27c3e38ab55e3c0a44)

---

Let me know if you need further clarification or would like additional details! 😊
# 15
Here’s your latest set of questions grouped and organized under appropriate topics, exactly as provided:

---

### **JavaScript/TypeScript**
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

6. **Closures** (Repeated in past questions).  

---

### **Progressive Web Apps (PWA)**
6. **What are Progressive Web Apps (PWAs)?**
   - PWAs allow websites to run offline like mobile apps.
   - Optimize web app performance by minifying code and reducing file sizes using tools like Google Insights/DevTools.

7. **Service Worker**:
   - A service worker is a JavaScript file that enables offline support for websites.
   - Service workers run in a separate thread from the main web page thread and are event-driven.
   - They support background processing, background sync, caching, and offline functionality.

---

### **Build Tools**
8. **Webpack**:
   - Can we set rules for coding standards and CSS?  
     - Use tools like ESLint for better coding practices.  

---

### **Web Accessibility**
9. **Web Accessibility**:
   - Ensure websites are user-friendly for everyone, including those with disabilities.
   - Examples: Support for color blindness, ensuring proper loading, etc.

10. **AA and AAA Accessibility Standards**:
   - Standards are defined by the Web Content Accessibility Guidelines (WCAG).  
     - **AA**: Intermediate accessibility compliance.  
     - **AAA**: Highest level of accessibility compliance.  
   - Meeting these standards ensures the application is usable by a broader range of users.

---

Let me know if you'd like more elaboration or have additional questions! 😊

# 16
Here’s the grouping of your latest set of questions, aligned with the specified topics:

---

### **JavaScript/TypeScript**
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

---

### **CSS**
5. **Visibility**:
   - `visibility: none`: Does not take space.
   - `visibility: hidden`: Takes space.

6. **Margin vs Padding**:
   - **Margin**: Space around the element.
   - **Padding**: Space inside the element (between content and border).

7. **Comparison**:
   - `==`: Compares values.
   - `===`: Compares values and types.

8. **setTimeout vs setInterval**:
   - `setTimeout`: Fires once after the elapsed time.
   - `setInterval`: Fires repeatedly at equal intervals.

---

### **React JS**
9. **Advantages of React JS**.

10. **Data Transfer in React**:
   - Using Props, callback functions, Context API, or Redux.

11. **State vs Props**:
   - Props are immutable.

12. **Context API**:
   - Used to pass data between components that are not directly nested.

13. **useState vs Context API**:
   - `useState`: For state management inside components.
   - Context API: Can’t be changed directly but provides a callback function to child components via Props.

14. **State vs Redux**.

15. **Multiple Hooks**:
   - Examples include: `useState`, `useEffect`, `useMemo`, `useCallback`, `useSelector`.

16. **Fetching API in UI**:
   - Commonly used in `useEffect`.

---

Let me know if you want further clarification or more questions grouped! 😊
# 17
Here’s your latest set of questions, grouped and structured based on the specified topics, keeping them unchanged as requested:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
8. **Explain Redux**:  
   - State management library for React. Provides a centralized store for application state.  
   - Includes `actions`, `reducers`, and a `store`.  
   - Middleware like `Redux Thunk` is used for handling asynchronous logic.

9. **Explain React Hooks**:  
   - Functions like `useState`, `useEffect`, `useMemo`, etc., to manage state and lifecycle events in functional components.  
   - Simplifies code by eliminating the need for class components.

10. **What are Pure Components?**  
    - React components that render the same output given the same props and state.  
    - Prevent unnecessary renders using `shouldComponentUpdate` for comparison.

---

Let me know if you’d like further details or have more questions! 😊

# 18

Here’s your latest set of questions grouped based on the specified topics, keeping everything unmodified as requested:

---

### **JavaScript/TypeScript**
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

---

### **NodeJS**
11. **Middleware:**  
   - Functions that execute during the lifecycle of a request to the server, such as intercepting requests or responses.

---

### **React JS**
12. **React Element vs Component:**  
    - Element: Immutable, used for representation.  
    ```javascript
    const element = <h1>Hello, World!</h1>;
    // Without JSX:
    const element = React.createElement('h1', null, 'Hello, World!');
    ```

13. **Pure Components:**  
    - React components that prevent unnecessary renders by implementing shallow comparisons of props and state.

14. **Refs in React:**  
    - Used to directly access DOM elements or persistent values across renders.

15. **ForwardRefs in React:**  
    - Enables passing refs through components to access child elements.

16. **React Virtual DOM:**  
    - A lightweight representation of the real DOM for efficient UI updates.

17. **Interceptor:**  
    - Intercepts requests and responses before they reach the backend. Examples include API validation, navigation handling based on status responses.

18. **React Fiber:**  
    - [Link](https://flexiple.com/react/react-fiber): React's reconciliation engine for improved rendering and responsiveness.

19. **React Lifecycles:**  
    - Examples: `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`.  

20. **Use Case for HOC:**  
    - Reusable logic across multiple components.

21. **Lazy Loading:**  
    - Dynamically importing components to optimize performance.

22. **Managing Nested Routes in Role-Based Routing:**  
    - Implement role-based checks for routes using libraries like React Router.

23. **Ask to Interview:**  
    - Questions about roles, projects, etc.

---

Let me know if you'd like further clarification or have more questions! 😊

# 19
Here’s your latest set of questions grouped into relevant topics, keeping everything as you provided:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
6. **Difference Between Class and Functional Components:**  
   - Class components: Use `setState` for state management and lifecycle methods.  
   - Functional components: Use hooks like `useState`, `useEffect`, etc., and are more concise.

7. **What are Pure Components?**  
   - Components that render the same output for the same props and state, avoiding unnecessary renders.

8. **How to Stop Rendering Components?**  
   - Use `shouldComponentUpdate` in class components or `React.memo` in functional components.

9. **How to Unmount Component Using Hooks:**  
   - Use the cleanup function inside `useEffect`:
     ```javascript
     useEffect(() => {
         return () => {
             console.log("Component unmounted");
         };
     }, []);
     ```

10. **Benefits of Context API and How to Use:**  
    - Avoids prop drilling by allowing data sharing across components.  
    - Example:
      ```javascript
      const MyContext = React.createContext();
      const Parent = () => (
          <MyContext.Provider value="Hello">
              <Child />
          </MyContext.Provider>
      );
      const Child = () => {
          const value = React.useContext(MyContext);
          return <p>{value}</p>;
      };
      ```

11. **Lazy Loading:**  
    - Dynamically imports components to improve performance:
      ```javascript
      const LazyComponent = React.lazy(() => import('./Component'));
      ```

---

### **Build Tools**
9. **Difference Between Yarn and NPM:**  
   - Both are JavaScript package managers.  
   - **Yarn**: Provides better concurrency, lockfile management, and commands.  
   - **NPM**: Default package manager for Node.js.  

---

### **GitHub Workflow**
12. **How to Commit Specific Commit from Working to Development Branch:**  
    - Use `git cherry-pick` to apply specific commits.

13. **What is Rebase in GitHub?**  
    - The `git rebase` command modifies the repository’s history by editing, reordering, or squashing commits. Used when multiple developers work on the same module.

---

Let me know if you want additional examples or more details! 😊

# 20 
Here's your latest set of questions grouped appropriately:

---

### **JavaScript/TypeScript**
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

---

Feel free to let me know if you'd like deeper explanations or have more questions! 😊
# 21
Here’s the grouping of your latest questions, categorized as per their topics:

---

### **React JS**
1. **Custom Hooks: `useFetch()`**  
   - Allows reusable logic for fetching data. Reference: [React Custom Hooks - W3Schools](https://www.w3schools.com/react/react_customhooks.asp).

2. **Using `useEffect` for Lifecycle Management**  
   - Achieves the behavior of lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`. Reference: [LogRocket Blog](https://blog.logrocket.com/using-react-useeffect-hook-lifecycle-methods/#using-componentdidmount-functional-components-useeffect).

3. **Difference Between Pure Functions and Achieving Similarity with `useEffect` and `shouldComponentUpdate`.**

4. **Phases of React Lifecycle:**
   - Mounting, Updating, and Unmounting.

5. **Lifecycle Method That Always Gets Called:**
   - `render` (always gets triggered on each update).

6. **Difference Between Class and Functional Components:**
   - Class components use lifecycle methods and `state`.  
   - Functional components use hooks (`useState`, `useEffect`).

7. **Redux Architecture:**
   - Follows unidirectional data flow with `actions`, `reducers`, and a central `store`.

8. **`UseMemo`:**
   - Memoizes the result of a function to avoid expensive recalculations.

9. **`React.memo`:**
   - Optimizes performance by memoizing functional components to prevent unnecessary renders. Reference: [React Memo and PureComponent](https://dev.to/nibble/react-memo-and-react-purecomponent-3k7k).

10. **Pure Component:**
    - Prevents unnecessary rendering by implementing `shouldComponentUpdate` for shallow comparison.

---

### **JavaScript/TypeScript**
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

---

### **React Hooks**
1. **Custom Hooks You’ve Done (`useFetch`).**

2. **Using `useEffect` for All Lifecycle Methods:**
   - Mimics `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`.

3. **Hooks `useMemo` and `useCallback`:**
   - `useMemo`: Caches the result of expensive calculations.  
   - `useCallback`: Memoizes callback functions to prevent unnecessary re-creation.

4. **Class vs Function:**
   - Depends on the use case.  
   - Redux often pairs well with class components, whereas functional components with `Context API` provide simpler management.

5. **Performance Measurement:**
   - Use tools like Lighthouse, implement dynamic imports, lazy loading, and reduce redundant CSS files/folders.

---

Let me know if you’d like elaboration on any topic or additional content! 😊
# 22
Here’s the grouping of your latest questions, keeping everything unmodified as you provided:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
4. **`useEffect` Mimicking Lifecycle Methods:**
   - `componentDidMount`:
     ```javascript
     useEffect(() => {
         console.log("Mounted");
     }, []);
     ```
   - `componentDidUpdate`:
     ```javascript
     useEffect(() => {
         console.log("Updated");
     }, [data]);
     ```
   - `componentWillUnmount`:
     ```javascript
     useEffect(() => {
         return () => {
             window.removeEventListener();
         };
     }, []);
     ```

5. **What is Function Overloading?**
   - A single function with the same name but different parameter types or numbers.  
   - **JavaScript does not natively support function overloading.**

6. **What is a Pure Component?**
   - A component that avoids unnecessary re-renders.  
   - Re-renders only when there are shallow changes in props or state for performance boost.  
   - Important: Uses shallow comparison for props/state.

---

### **Testing and Tools**
7. **Using Test Cases for Unit Testing:**
   - Example tools: Jest, Enzyme (for DOM-level testing).

8. **Have You Used TypeScript and Redux?**
   - Yes, for better type safety and state management respectively.

---

Let me know if you’d like further explanation or more examples! 😊

# 23
Here’s your latest set of questions, grouped under appropriate topics:

---

### **React JS**
1. **Why ReactJS?**  
   - ReactJS is popular for creating dynamic, fast, and responsive UI. It uses virtual DOM for efficient updates and supports component-based architecture for reusable code.

2. **Class vs Function Components:**  
   - Class components use lifecycle methods (`componentDidMount`, etc.) and `setState` for state management.  
   - Functional components rely on hooks like `useState` and `useEffect` for managing state and lifecycle methods.

3. **Error Boundary vs Try-Catch-Finally:**  
   - **Error Boundaries:** Handle errors in React components (`componentDidCatch`). Prevents crashing of the entire app.  
   - **Try-Catch-Finally:** JavaScript feature for handling errors at runtime outside React-specific contexts.

4. **Code Coverage:**  
   - Percentage of code tested during unit testing (e.g., how many lines and functions are covered in Jest tests).

5. **How to Access State in Redux:**  
   - Use `useSelector` to access the Redux store state in a React component.  
     Example scenario: Travel login across multiple pages (`page1`, `page2`, etc.).

6. **Pure Component:**  
   - Prevents unnecessary re-renders by implementing `shouldComponentUpdate`.  
   - Enhances performance by shallowly comparing props/state.

7. **`useMemo` for Caching:**  
   - Memoizes the result of a function, reducing recalculations and improving performance.

8. **State vs Props:**  
   - **State:** Component's local data that can be updated within the component.  
   - **Props:** Immutable data passed from parent to child components.

9. **Constructor in Class Components:**  
   - Initializes state and binds event handlers. Example:
     ```javascript
     class MyComponent extends React.Component {
         constructor(props) {
             super(props);
             this.state = { key: value };
         }
     }
     ```

---

### **JavaScript/TypeScript**
6. **Object Chaining and Null Check:**  
   - Use optional chaining (`?.`) or ternary (`?:`) to check for null values:  
     ```javascript
     const obj = null;
     const value = obj?.key || "default";
     console.log(value); // Output: "default"
     ```

---

### **Testing and Tools**
11. **Test Cases for Unit Testing:**  
   - Use Jest/Enzyme for DOM-level testing and measuring code coverage.

---

### **CSS**
12. **Responsive Design with Media Queries:**  
   - Example:
     ```css
     @media (max-width: 768px) {
         .container {
             display: block;
         }
     }
     ```

Let me know if you need clarification or examples for any of these! 😊

# 24
Here’s how your questions are categorized based on the specified topics:

---

### **HTML**
- **How much time required to convert wireframe to HTML code?**

---

### **CSS**
- **Display fetched data in CSS cards**:
  Example CSS for styling:
  ```css
  .card {
      border: 1px solid #ccc;
      padding: 20px;
      margin: 10px;
      box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
  }
  ```
  
---

### **JavaScript/TypeScript**
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

---

### **React JS**
- **How to Pass Data Between Components**:
  - Using keys, props, and callbacks. Virtual DOM ensures only updated elements are rendered, enhancing performance.

---

### **Node JS**
- **Difference Between Struts and REST Parameters**:
  - **Struts**: Java-based framework for building web applications with action-based architecture.
  - **REST Parameters**: Used in RESTful APIs to send data via query strings, path parameters, or body data, focusing on stateless interactions.

---

Let me know if you’d like elaboration on any of the points or additional examples! 😊

# 25
Here’s your latest set of questions categorized under the specified topics:

---

### **React JS**
1. **What is `useRef`?**  
   - A React hook that provides a way to directly access or persist values across renders without causing re-renders. Commonly used for accessing DOM elements or storing mutable values.

2. **What is Higher-Order Component (HOC)?**  
   - A function that takes a component and returns a new enhanced component.  
   - **Where used?** Login authentication, reusability, props manipulation, or creating complex solutions.
   - **Problem it solves:** Reusability, props modification, and adding logic to components without duplicating code.
   - Example:
     ```javascript
     function HOC(WrappedComponent) {
         return function InnerFunction(props) {
             return <div><WrappedComponent {...props} /></div>;
         };
     }
     ```

3. **Create Components to Take Input and Convert to Uppercase Using HOC:**
   - HOC for handling input transformation:
     ```javascript
     function withUpperCase(WrappedComponent) {
         return function EnhancedComponent(props) {
             const handleChange = (e) => {
                 e.target.value = e.target.value.toUpperCase();
             };
             return <WrappedComponent {...props} onChange={handleChange} />;
         };
     }
     ```
   - Implementation:
     - Component A and Component B use the same HOC to handle uppercase conversion.
   - Alternative HTML approach:
     ```html
     <input style="text-transform:uppercase" onInput="this.value = this.value.toUpperCase();" />
     ```

4. **Fetch Data from Backend (Multiple Fetch API):**
   - Using `Promise.all` with `fetch`:
     ```javascript
     const apiUrls = ['https://api.example.com/users', 'https://api.example.com/products'];

     const fetchData = (url) => {
         return fetch(url)
             .then(response => response.json())
             .catch(error => { console.error('Error:', error); throw error; });
     };

     Promise.all(apiUrls.map(url => fetchData(url)))
         .then(data => {
             console.log(data);
         })
         .catch(error => {
             console.error('Error:', error);
         });
     ```

5. **React Table for Fetched Data:**
   - Display data in a table using React. Example:
     ```javascript
     function DataTable({ data }) {
         return (
             <table>
                 <thead>
                     <tr>
                         <th>ID</th>
                         <th>Title</th>
                     </tr>
                 </thead>
                 <tbody>
                     {data.map((item) => (
                         <tr key={item.id}>
                             <td>{item.id}</td>
                             <td>{item.title}</td>
                         </tr>
                     ))}
                 </tbody>
             </table>
         );
     }
     ```

---

### **JavaScript/TypeScript**
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

---

### **Axios vs Fetch**
4. **Key Differences Between Axios and Fetch:**
   - **Axios**:
     - Third-party library with enhanced features.
     - Supports older browsers.
   - **Fetch**:
     - Built-in JavaScript API.
     - Requires additional handling for advanced use cases.

---

Let me know if you’d like more elaboration on any point or additional examples! 😊
# 26
Here's your provided information categorized under the appropriate topics:

---

### **HTML**
1. **Difference Between `<script>`, `<script async>`, and `<script defer>`**:
   - `<script>`: Executes immediately when the browser encounters the script tag.
   - `<script async>`: Downloads the script asynchronously and executes it as soon as it's ready.
   - `<script defer>`: Downloads the script asynchronously but waits until the HTML document has been parsed before executing it.

2. **What is `dataSet` Attributes in HTML?**:
   - Used to store custom data attributes within HTML elements. Example:
     ```html
     <a href="#" data-name="ravi"></a>
     ```

3. **What is `srcset` in Images?**:
   - Allows specifying multiple images with different resolutions or sizes for responsive design. Example:
     ```html
     <img src="image-default.jpg" srcset="image-500.jpg 500w, image-800.jpg 800w" />
     ```

---

### **CSS**
7. **What is Box Model?**:
   - Describes the structure of HTML elements, including:
     - Content.
     - Padding (space between content and border).
     - Border (outer layer surrounding the padding).
     - Margin (space outside the border).

---

### **JavaScript/TypeScript**
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

---

### **React JS**
9. **Create Tab Component**:
   - Reference: [React Tabs on CodeSandbox](https://codesandbox.io/s/lucid-mountain-zl2qdk?file=/src/ComponentA.js).

---

Let me know if you’d like me to elaborate or add details! 😊
#26
Here's your provided content categorized under the specified topics:

---

### **React JS**
1. **Issues with the Code and Preventing Re-Rendering**:
   - **Issues**:
     - The `handleClick` function doesn't update the `color` value; it's commented out.
     - Directly calling `handleClick(e)` in `onChange` results in incorrect usage and doesn't bind the input value correctly.
     - Infinite rendering may occur if `useEffect` calls `setColor(value)` because `value` is an uncontrolled variable outside React state management.
   - **Prevent Re-Rendering**:
     - Use `React.memo` for functional components.
     - Example for `ChildComponent`:
       ```javascript
       const ChildComponent = React.memo(() => {
           console.log("Child");
           return <p>I am child component</p>;
       });
       ```

2. **Why Class Component Names Start with Capital Letters**:
   - React interprets lowercase names as regular HTML tags and uppercase names as custom components. By convention, class component names start with a capital letter to differentiate them from HTML elements.

3. **Does Functional Component Have the Same Behavior?**:
   - **Yes**, both functional and class components are treated as React components with similar lifecycle and behavior.

---

### **JavaScript/TypeScript**
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

---

### **CSS**
8. **Text Centering**:
   - Horizontal centering:
     ```css
     text-align: center;
     ```
   - Vertical and horizontal centering:
     ```css
     display: flex;
     justify-content: center;
     align-items: center;
     height: 100vh;
     ```

9. **Flexbox**:
   - Layout for aligning items easily:
     ```css
     display: flex;
     justify-content: space-between;
     align-items: center;
     ```

---

### **Security**
10. **Which is More Secure: LocalStorage vs SessionStorage?**:
   - Both are client-side storage, but neither is inherently secure for sensitive data. Use other secure storage methods like cookies with HTTP-only flags for security.

---

Let me know if you'd like to dive deeper into any of the topics or examples! 😊


# 27
Here’s the categorization of your provided content:

---

### **HTML**
1. **Section vs Div (Semantic):**  
   - `<section>`: A semantic element used for grouping related content with a clear meaning.  
   - `<div>`: A non-semantic element used as a generic container without any specific meaning.

2. **What is a Pseudo-Element?**  
   - A CSS selector used to style specific parts of an element.  
   - Examples: `::before`, `::after`, `::first-letter`.  
   - Example:
     ```css
     p::first-letter {
         font-size: 2em;
         color: red;
     }
     ```

---

### **CSS**
3. **EM vs REM:**  
   - `EM`: Relative to the font-size of its parent.  
   - `REM`: Relative to the font-size of the root (`html`) element, typically 16px by default.

4. **Box Model:**  
   - Describes the structure of elements in CSS:
     - Content.
     - Padding (space inside the border).
     - Border.
     - Margin (space outside the border).

---

### **JavaScript/TypeScript**
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

9. **Why Use Synthetic Events in React?**  
   - Synthetic events unify event handling across browsers, making behavior consistent.  
   - Example:
     ```javascript
     function handleClick(event) {
         console.log(event.target);
     }
     ```

10. **Virtual DOM Reconciliation and Pure Components:**  
    - **Virtual DOM Reconciliation:** Determines the changes in the DOM by comparing the current Virtual DOM to the previous one.  
    - **Pure Component:** Prevents unnecessary re-renders by performing shallow comparisons of state and props. It enhances performance when props or state do not deeply change.

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

---

Let me know if you need additional clarifications or examples! 😊

# 28
Here's your code snippets and explanations categorized for clarity:

---

### **JavaScript Snippets**

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

3. **Fetch Data from an API (`randomuser.me`) and Display in React:**
   - This snippet fetches user data from the API every 2 seconds using `setInterval` and displays it dynamically:
     ```javascript
     import React, { useState, useEffect } from 'react';

     export default function App() {
         const URL = 'https://randomuser.me/api/?exc=login';
         const [users, setUsers] = useState([]);

         useEffect(() => {
             const fetchData = () => {
                 fetch(URL)
                     .then(res => res.json())
                     .then(data => setUsers(data.results))
                     .catch(err => console.error(err));
             };
             fetchData();
             const interval = setInterval(fetchData, 2000);
             return () => clearInterval(interval); // Clear interval on component unmount
         }, []);

         console.log('users: ', users);

         return (
             <div className="App">
                 <h1>Hello CodeSandbox</h1>
                 <h2>Start editing to see some magic happen!</h2>
                 {users?.map((user, index) => (
                     <div key={index}>
                         <p>{user.gender}</p>
                         <p>{user.email}</p>
                         <p>{user.phone}</p>
                     </div>
                 ))}
             </div>
         );
     }
     ```

---

### **Corrections and Explanations**

1. **Fixing Object Spread Syntax:**
   The spread operator in JavaScript (`...`) is used to clone or merge arrays/objects:
   ```javascript
   const a = { firstName: 'John' };
   const b = { ...a, lastName: 'Cena', gender: 'Male' };
   console.log(a); // Output: { firstName: 'John' }
   console.log(b); // Output: { firstName: 'John', lastName: 'Cena', gender: 'Male' }
   ```

2. **Memory Efficient and Correct API Fetching:**
   The incorrect usage of `setInterval` within the React `useEffect` might cause memory leaks. The above snippet fixes this by clearing the interval when the component unmounts.

Let me know if you need clarification or additional tweaks for any snippets! 😊

# 29
Here’s your content categorized and explained:

---

### **JavaScript**
1. **Declarative vs Imperative Programming**:
   - **Declarative**: Focuses on describing *what* you want to achieve without specifying *how* to do it. Examples include React and Redux, which emphasize functional and logical programming.
   - **Imperative**: Specifies *how* to achieve the desired result step by step. Examples include procedural programming and object-oriented programming (OOP).

---

### **CSS**
2. **CSS Libraries**:
   - **Bootstrap**: A popular framework for responsive design, offering pre-designed components like buttons, grids, and forms.
   - **Tailwind CSS**: A utility-first CSS framework that allows developers to build custom designs directly in HTML using predefined classes.

3. **Accessibility in CSS**:
   - CSS can enhance accessibility by:
     - Providing visual cues (e.g., focus outlines for keyboard navigation).
     - Improving readability (e.g., high contrast colors for text).
     - Supporting assistive technologies (e.g., ARIA roles and attributes).

---

### **Redux**
4. **Redux Store Variable in Browser**:
   - The Redux store is an **in-memory data structure** managed by JavaScript. It is not stored in Local Storage, Session Storage, or Cookies by default.
   - To persist Redux state across page reloads or sessions, you can use middleware like `redux-persist`.

---

### **React JS**
5. **Latest Version of React and New Features**:
   - The latest version of React is **React 18**, which introduced several new features:
     - **Concurrent Rendering**: Improves performance by allowing React to pause, resume, or abandon renders.
     - **Automatic Batching**: Groups multiple state updates into a single render for efficiency.
     - **New Hooks**: Includes `useId`, `useTransition`, and `useDeferredValue`.
     - **Streaming Server Rendering**: Enhances server-side rendering with better performance.
     - **Strict Mode Updates**: Adds additional checks and warnings during development.

Let me know if you'd like further elaboration or examples! 😊
# 30

Here’s your content organized under relevant topics:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
1. **RTQuery (React Query)**:
   - A library for managing server state in React applications.
   - Handles caching, synchronization, and updating UI efficiently after API calls.

2. **React vs ReactDOM**:
   - **React**: Provides the library for creating React components.
   - **ReactDOM**: Handles rendering components to the DOM.

---

### **Architectures**
3. **Monorepo Architecture**:
   - A repository structure where code for multiple projects resides in a single repository.
   - Benefits:
     - Easier dependency management.
     - Cross-project collaboration.
   - Tools: `Nx`, `Lerna`.

---

Let me know if you want further elaboration or more examples! 😊

#31
Here's your information grouped and elaborated upon under relevant categories:

---

### **JavaScript/TypeScript**

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

4. **`useCallback` and `ContextAPI`**:
   ```javascript
   import React, { useCallback, useState, createContext, useContext } from "react";

   const MyContext = createContext();

   const Parent = () => {
       const [count, setCount] = useState(0);
       const increment = useCallback(() => setCount(count + 1), [count]);

       return (
           <MyContext.Provider value={increment}>
               <Child />
           </MyContext.Provider>
       );
   };

   const Child = () => {
       const increment = useContext(MyContext);
       return <button onClick={increment}>Increment</button>;
   };

   export default Parent;
   ```

---

### **HTML**

2. **HTML vs HTTPS (COROS)**:
   - **HTML**: Standard markup language for creating web pages.
   - **HTTPS (Hypertext Transfer Protocol Secure)**: An internet communication protocol that ensures secure data transfer using encryption.

4. **Semantic vs Non-Semantic Elements**:
   - **Semantic Elements**: Convey meaning (e.g., `<header>`, `<footer>`, `<article>`).
   - **Non-Semantic Elements**: Do not convey meaning (e.g., `<div>`, `<span>`).

---

### **CSS**

3. **CSS Grid vs Flexbox**:
   - **Grid**: Two-dimensional layout (rows and columns).
   - **Flexbox**: One-dimensional layout (row or column).  
   - Example:
     ```css
     /* Flexbox */
     .container {
         display: flex;
         justify-content: center;
         align-items: center;
     }

     /* Grid */
     .grid-container {
         display: grid;
         grid-template-columns: repeat(3, 1fr);
         grid-gap: 10px;
     }
     ```

---

### **React JS**

9. **React vs ReactDOM**:
   - **React**: Handles the creation and management of React components.
   - **ReactDOM**: Provides methods to render components into the DOM (e.g., `ReactDOM.render()`).

10. **SEO and Rendering**:
   - **SEO**: Search Engine Optimization improves site visibility on search engines.
   - **SSR (Server-Side Rendering)**: Generates HTML on the server, ensuring fast load and better SEO.
   - **CSR (Client-Side Rendering)**: Loads JavaScript and builds HTML on the client-side; can have poor SEO unless pre-rendering is used.

---

### **Package Management**

5. **Dependency vs DevDependency**:
   - **Dependency**: Required for the application to run.
   - **DevDependency**: Only needed during development (e.g., linters, testing tools).  
   - Example:
     ```bash
     npm install package-name --save  # Adds as dependency
     npm install package-name --save-dev  # Adds as devDependency
     ```

6. **Webpack**:
   - A module bundler for modern JavaScript applications.
   - Key features:
     - Handles asset bundling (JavaScript, CSS, images).
     - Tree-shaking to remove unused code.

---

### **Performance**

7. **Performance Optimization**:
   - Techniques:
     - Lazy loading and code splitting.
     - Minimize DOM operations.
     - Server-side rendering (SSR).

---

Feel free to ask for clarification or further elaboration on any of the topics! 😊
# 32
Here’s your content grouped and explained under relevant topics:

---

### **JavaScript/TypeScript**

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
     ```

6. **SQL to Find Duplicate Employee Names**:
   ```sql
   SELECT Name
   FROM Employee
   GROUP BY Name
   HAVING COUNT(*) > 1;
   ```

---

### **React JS**

1. **Bearer Token on Login Page**:
   - Store the token in `localStorage`, `sessionStorage`, or cookies.
   - Pass the token in the `Authorization` header for subsequent requests.
     ```javascript
     fetch("https://api.example.com/resource", {
         headers: { "Authorization": `Bearer ${token}` }
     });
     ```

2. **Error Boundary in Functional Components**:
   Use `ErrorBoundary` as a HOC:
   ```javascript
   import React, { Component } from "react";

   class ErrorBoundary extends Component {
       constructor(props) {
           super(props);
           this.state = { hasError: false };
       }

       static getDerivedStateFromError(error) {
           return { hasError: true };
       }

       componentDidCatch(error, errorInfo) {
           console.error(error, errorInfo);
       }

       render() {
           if (this.state.hasError) {
               return <h1>Something went wrong.</h1>;
           }
           return this.props.children;
       }
   }

   export default ErrorBoundary;
   ```

3. **Lifecycle Management in Functional Components**:
   Replace lifecycle methods using `useEffect`:
   - **componentDidMount**:
     ```javascript
     useEffect(() => {
         console.log("Mounted");
     }, []);
     ```
   - **componentDidUpdate**:
     ```javascript
     useEffect(() => {
         console.log("Updated");
     }, [dependency]);
     ```
   - **componentWillUnmount**:
     ```javascript
     useEffect(() => {
         return () => console.log("Unmounted");
     }, []);
     ```

4. **Implement Infinite Scrolling Without Losing Data**:
   ```javascript
   const [data, setData] = useState([]);
   const [page, setPage] = useState(1);

   const fetchMoreData = () => {
       fetch(`https://api.example.com/data?page=${page}`)
           .then(res => res.json())
           .then(newData => setData(prev => [...prev, ...newData]))
           .catch(err => console.error(err));
   };

   useEffect(() => {
       fetchMoreData();
   }, [page]);

   const handleScroll = () => {
       if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
           setPage(prev => prev + 1);
       }
   };

   useEffect(() => {
       window.addEventListener("scroll", handleScroll);
       return () => window.removeEventListener("scroll", handleScroll);
   }, []);
   ```

---

### **CSS**

1. **Flexbox vs Grid**:
   - **Flexbox**: For one-dimensional layouts (row or column).
   - **Grid**: For two-dimensional layouts (rows and columns).
   ```css
   /* Flexbox Example */
   .container {
       display: flex;
       justify-content: center;
       align-items: center;
   }

   /* Grid Example */
   .grid-container {
       display: grid;
       grid-template-columns: repeat(3, 1fr);
   }
   ```

2. **Absolute vs Relative Positioning**:
   - **Absolute**: Positions the element relative to its nearest positioned ancestor.
   - **Relative**: Positions the element relative to its normal position.

3. **Semantic vs Non-Semantic CSS**:
   - **Semantic**: CSS selectors with meaningful names (`header`, `footer`, etc.).
   - **Non-Semantic**: Non-descriptive names (`div`, `span`).

4. **Validation and Preventing Form Submission**:
   ```javascript
   const handleSubmit = (e) => {
       e.preventDefault(); // Prevent default form behavior
       if (!isValid) {
           console.log("Validation failed");
       }
   };
   ```

5. **Specificity**:
   - **Inline Styles** > **ID Selectors** > **Class Selectors** > **Element Selectors**.

6. **Different Sectors in CSS**:
   - **Selectors**: IDs, classes, attributes.
   - **Box Model**: Margins, padding, borders.
   - **Flexbox & Grid**: Layout techniques.
   - **Animations**: Transitions, keyframes.

---

Let me know if you'd like deeper clarifications or further examples! 😊

# 33
Here’s your content organized under appropriate categories with explanations:

---

### **JavaScript/TypeScript**
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

---

### **React JS**
1. **Data Passing from Child to Parent**:
   - Use callback or Redux:
     ```javascript
     const Child = ({ updateParent }) => {
         return <button onClick={() => updateParent("Data from Child")}>Send Data</button>;
     };
     const Parent = () => {
         const handleUpdate = (data) => console.log(data);
         return <Child updateParent={handleUpdate} />;
     };
     ```

2. **Next.js - Server Side Rendering**:
   - Next.js automatically handles SSR for better SEO. Use `getServerSideProps` for fetching data at request time.

3. **Infinite Scrolling with Socket**:
   ```javascript
   import { useEffect, useState } from "react";

   const LiveScores = () => {
       const [scores, setScores] = useState([]);

       useEffect(() => {
           const socket = new WebSocket("wss://example.com/scores");
           socket.onmessage = (event) => {
               setScores((prev) => [...prev, JSON.parse(event.data)]);
           };
           return () => socket.close(); // Cleanup
       }, []);

       return scores.map((score, index) => <p key={index}>{score}</p>);
   };
   ```

---

### **CSS**
1. **Pseudo Class**:
   - Applies styles to elements based on their state:
     ```css
     a:hover {
         color: red;
     }
     ```

2. **Specificity**:
   - **Order of Importance**: Inline styles > ID selectors > Class selectors > Element selectors.
   - Example:
     ```html
     <div id="unique" class="class" style="color: red;">Text</div>
     ```

3. **CSS Pre-Processors**:
   - **Example with Variables**:
     ```scss
     $primary-color: #3498db;

     .button {
         background-color: $primary-color;
     }
     ```

4. **Display `none` vs Invisible**:
   - **`display: none;`**: Element is removed from layout.
   - **`visibility: hidden;`**: Element remains in layout but is invisible.

5. **Flexbox vs Grid**:
   - **Flexbox**: Single-direction layout (row or column).
   - **Grid**: Two-dimensional layout (rows and columns).

---

### **SQL**
1. **Query Optimization**:
   - Use indexing to speed up lookups.
   - Avoid `SELECT *`, specify required columns.
   - Optimize joins and reduce subqueries.

---

### **Tools and CI/CD**
1. **ESLint for PR Review**:
   - Commands to identify errors:
     ```bash
     npx eslint . --format stylish            # All files
     npx eslint src/App.js --format stylish  # Specific file
     npx eslint . -f json -o eslint-report.json # Generate report
     npx eslint . --quiet                   # Only errors
     ```

2. **SonarQube and Jenkins**:
   - SonarQube: Code quality and security analysis.
   - Jenkins: Automates CI/CD pipelines.

3. **CI/CD Steps**:
   - Example in GitHub Actions:
     ```yaml
     - name: Run ESLint
       run: npx eslint . --max-warnings=0
     ```

---

Let me know if you’d like elaborations or additional examples! 😊
