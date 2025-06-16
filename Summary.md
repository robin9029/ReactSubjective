# EP1- INCEPTION
## CDN Links for React
````
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
````

## Q: html how to put h1 in root tag
1) JAVSCRIPT
 
```
<div id="root">     
    </div>
    <script>
        const h1tag = document.createElement("h1")
        h1tag.innerHTML= "Hello World ";
        const root =document.getElementById("root")
        root.append(h1tag)
    </script>
```
2) React
Same thing can be do via React 
 ```
<div id="root">
      <h1>This is Ravi here </h1>.  
							                      
    </div>
// html load this message and once react render it will replace it
// react can work only on particular root and rest it will amends 
```
```
<div id =‘NewRoot’>
  <h1>This is new Ravi here </h1> 
    </div>
// react can work only on particular root and rest it will apends that’s why its library  
```
```
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script>
      const ele = React.createElement("h1", {}, "Hello world Program");   //Object 
      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(ele);
    </script>
```
#### React.createElement("h1", {}, "Hello world Program");   //it create Object
####  root.render(ele) : take react element/which is Object (h1). 
Convert it into h1 tag  which understand by Browser and
put it into the ROOT  

# EP2,3

## Q:npm init - initialises ?
 name, author, project name, test, licence etc 
#### Package.json - is configuration for NPM , keeps track of package we are using`(Approx)`
#### Package-lock.json- keeps lock of track of `(exact) version` is installed 
 
#### Package-lock.json
```
"integrity": "sha512-FLNI5OrZxymGf/Yln0E/kjnGn5sdkQAxW7pQVdtuM+5VeN75yibJRjsSGv88PvJ+KvpD2ANgiIJo1RufmoPcww==",
````
So my code is working local but not Prod because of versions , So integrity hash value to use 

if you have both these package - you can recreate all the node modules since it has all the details of all the packages 
So if you push code to gitlab, just do npm install it will provide you with the dependency of Package in node_modules 

## Q: `npm install -D parcel`- D is DEV
## Q: Versions 
`”^2.13.3"` automatically upgrade to minor - its advisable `[caret]`

`“~2.13.3" ` automatically upgrade to major update not advisable`[tilda]` 

## Q:`node_modules`:- DB which has so many packages
## Q: `Parcel` : https://parceljs.org/

- Creates build 
- Local server 
- HMR - Automatically refreshing HMR = Hot Module Replacement - exchanges, adds, or removes modules while an application is running, without a full reload
and some of more cool features of Parcel are:
- File Watching Algorithm - written in C++ keep tracks of File
- Faster build because of caches 
- Image optimisation 
- Magnification - bundling 
- Compress 
- Consistent hasing 
- Code splitting 
- Differential bundling : provide different bundling to support different browser - chrome/firefox explorer older version of Browser
- Diagnostic - on error 
- Error handling - provide suggestion 
- https 
- Tree shaking ALGO - remove unused code for you - eg from module you are using only very few functionality , parcel remove unused code tree shaking 
- Different Dev and prod Bundlers 
- So parcel is hosting our app and on port 1234

`npx parcel index.html` npx- is to execute the package 

This will build the Development and put your code in Dist folder 

`Whenever changes it will come from - Dist to UI`

Parcel will HMR (Hot modules refresh ) Automatically refreshing , minify and put into the Dist

#### Production Build `npx parcel build index.html` 

## Q:type="module"  will include modules from node modules 

  ```
<script type="module" src="./App.js">
```
## Q:browserslist: https://browserslist.dev/
allows to configure our APP which	 will support what all version of Browser will support inside package.json 

## Q:Babel- transpiler, compiler  https://babeljs.io/

- JSX- is not html inside javascript, its like html/xml `its different syntax`
- JSX - is transpiler before it reaches the JS ,who does ? `-Parcel-> Babel` 
- JSX => React.createElement => ReactElement-`JS Object` => HTMLElement(render) 
- Javascript = can be written in `{}`


- Both below are same 
```
const xmlHeading = <h1 className="heading" > Namsate Dev 2</h1> 
```

```
const xmlHeading2 = (<h1 className="heading" >
                     Namsate Dev 2
                     </h1> )
```

- JSX - prevent cross site attack and it sentizes 
You JSX is after all Javascript 

## Q: Component - functional 
- starts with Capital letter 
- Javascript function which returns a JSX or ReactElement 
```
root.render(xmlHeading);
root.render(<h1 id="heading" > Namsate Dev 3</h1>);
```

how to pass functional component in render using wrapper </>
```
root.render(<HeadingComponent/>)
```

## Q:  component composition 
- Once component is called inside another and then render
## Q: how to pass React Element in Functional component 
- using '{}'
- You can use or write complete javascript code inside {}

  ![download1](https://github.com/user-attachments/assets/49cc38df-9523-47bd-9412-1a1dca7bb0a5)

# EP4 -key,config driven UI,MAP,function,Props

## Q.you can provide inline style in JSX using  javascript object {}
```
const styleComponent= {
  backgroundColor:'#f0f0f0'
}
const RestaurantCard = () => {
  return (<div className="res-card" style={styleComponent}>
    <h3> Meghna Foods</h3></div>)  ;
};
```
## Q: Config Driven UI- controlling your Ui using Data 
- Ui is driven by `Config like Data`, you change the place all the display are same like eg-  `AMAZON-UK,India,US`
- Swiggy - for Delhi offers are different than Bangalore than Sahibganj- no offer (so if Data is comes where it doest allow offer for Sahibganj )
- If you want to display Delhi- red,Bangalore- Brown, Sahibganj-Green just pass colour based on location -
- Restaurent - provide VEG,Non-VEG
- UI Layer, Data Layer  `what data is coming based on that we build UI' - This is called Config Driven UI
 
## Q:props ?
- are argument to function 
- Props is properties 
- Props are javascript Object 

## Q: what happens if you don’t provide key to map/LOOP/ListItem what happens ?
- If new element/restaurant card came react re-render all 
- if you give Unique key , reacts knows what keys new element comes and only re render only new one - improves performance 
- REACT uniquely identifies new element 
```
<div className="res-container">
       {resList.map(restaurant =>(<RestaurantCard key ={restaurant.data.id} resData ={restaurant}/> ))}
      </div>
```
- Its ok to use Index but its not recommended 
```
{resList.map((restaurant, index) =>(<RestaurantCard key ={index} resData ={restaurant}/> ))}
```

# EP5 hook, file structure, Import/export 

## Q. When data changes my UI layer not changed why ? DOM manipulation not happening 
- Updating DOM or DOM manipulation or changes in Data my UI also changes , efficient DOM manipulation 
- As soon as my state Variable  of data changes using SetState my UI  - react will re-render the Components
Means you changed the data - `it refresh page - re-render` (refresh page again )
- Render: calling module/component 
- Whenever state variable changes - React triggers reconciliation process and re-render 

## Q. Hooks ?
- it is normal javascript function with inbuilt utility features provided by React
- It keeps your data Layer and UI layer in synch
- JS Utility function 

- Eg. `USESTATE`: it is used to create localSTATE inside your Function 

```
const [listOfResturant] = useState([]). Define variable it return array 
const [listOfResturant, useListOfResturant] = useState(data) 
```

- Or 
```
Const are =useState(data). //it return array 
const [listOfResturant, useListOfResturant] = arr. //array Structure 
```
- example filtering based on rating
- Before
  ![Screenshot 2025-02-07 at 2 49 07 PM1](https://github.com/user-attachments/assets/e96c0778-0378-4603-88e9-2facb577d4c8)
- AFTER filtering from 3 to 2
- ![Screenshot 2025-02-07 at 2 49 15 PM2](https://github.com/user-attachments/assets/4269489a-abe0-4718-996f-4658f9e4de1e)

```
<button
          className="filter-btn"
          onClick={() => {  
            const listOfResturantUpdated= listOfResturant.filter(res=> res.data.avgRating>4)
            useListOfResturant(listOfResturantUpdated)}>
          Top Rated Resturant
        </button>
```
- The Moments you call useListOfResturant, you are updating the listOfResturant(State ) , React Re-render (Refresh page )
#### when you call useListOfResturant to update 
 const listOfResturant  , React  changes to `new variable listOfResturant` as `undefined`  &  update value useListOfResturant(listOfResturantUpdated)
## Q: Rule for HOOKS ?
- Hooks can only be called inside React function components(1)
- Hooks can only be called at the top level of a component(2)
- Hooks cannot be conditional(3)
```
const [listOfResturant, useListOfResturant] = useState([]); // (1) Not allowed before function Body
const Body= () => {
    
    const [listOfResturant, useListOfResturant] = useState([]); // (2) allowed 

if(Condition ){
    const [listOfResturant, useListOfResturant] = useState([]);  //(3) not allowed
}
    return (
        <div> THIS is HOOK</div>
    )
}
```
## Q. What is Virtual DOM & Reconciallation or React Fibre (after REACT16)
- Virtual DOM: is replica of DOM
- its an ReactElement or
- its `Javascript representation of HTML` as  `Object` or OBJECT representation oF UI 
- Eg nested DIV 

## Q: Reconciallation Algo/ Process ? 
- Suppose starting we have 7-RestaurantCard, same in Virtual DOM
- Now once you filter based on rating>4  we have 4-RestaurantCard
- Algo compares `Previous_Virtual_DOM`(Previous_OBJECT) & `current_Virtual_DOM`(Current_OBJECT) 
- If finds changes then update DOM 
- Actually React doesn’t work on Html - DIV its finds better way like `Javascript Object` and see the changes in Object which makes 
Manipulation fast 
- It does not touches DOM
- ![Screenshot 2025-02-07 at 2 47 35 PM2](https://github.com/user-attachments/assets/d178bd53-6087-40e7-a226-2a719604d505)


## Q: Why react is FAST ?
- Efficient DOM manipulation ,it is Virtual DOM, `it can find out the DIV and updates`
- ACDlite GitHub react Fiber  : https://github.com/acdlite/react-fiber-architecture


# EP6 -API call,UseEffect
## Q. monolithic vs microservices 
microservices
	Single responsibility principle 
	Seperation of concern 

## Q. API calls
- 1st Approach `Load->API call(wait till receive data) -> render`
- 2nd Load->Render(Skeleton ) -> API call -> Re-render(with data)

##### React approach - because it will give better user experience : 2 render is ok since render mechanism is fast 

## Q: what is shemer uI- till the data fetch you show fake cards
## Q: fetch api - browser api 
```
fetch('url') // api for the get request
    .then(response => response.json())
    .then(data => console.log(data));
```
OR
```
 async function getRestaurant to fetch Swiggy API data
  async function getRestaurants() {
    const data = await fetch(
      "Swiggy_API_URL"
    );
    const json = await data.json();
    // we get the Swiggy API data in json format
    console.log(json);
  }
 ```
## Q:  useEffect ? - it will be called always in 1st Render 
- It  calls on every component renders
- If dependency array [EMPTY] called once- render only once
- If dependency array [DATA] called once when dependency is changes

# EP7
## Q: Routing ? createBrowserRouter, routerProvider, Outlet
- createBrowserRouter: List of configuration path, what happens when we click on the path
- routerProvider: is a component and will provide the app router configuration
- Outlet: will be filled with children routes adding ‘/’ main page + Body or according to Routes
- Link:
```
  import { Link } from "react-router-dom";
	  <Link to="/about" key={key}> About us </Link>
```
- useRouteError: is utility JS function which return Object with details about status

```
import { useRouteError } from "react-router-dom";
	 const errorMsg= useRouteError();
	h3> {errorMsg.status}: {errorMsg.statusText}</h3>
```
## Q: useParam will provide the resID from URL
- Routing
  ```
  {path:"/resturants/:resId", element: <ResturantMenu/>}
  ```
- Main component 
``` 
import { useParams } from "react-router-dom";
const ResturantMenu = () => {
  const [resInfo, setResInfo] = useState(null);
  const {resId} =useParams()
   const fetchMenu = async () => {
    const data = await fetch('URL'+resId);
    const json = await data.json();
    setResInfo(json.data);
  };
```  
- when called from : 
```
http://localhost:1234/resturants/251194
const {resId} =useParams()
resId=251194
```  
 ## Q: can we use <a href='/'> </a> in place of Link and what is Link ?
- never use <a> tag for navigating 
- Not to use since it reload the page which is not required in Place use Link component works similarly as <a>
- Link is a `wrapper over anchor tag`
 ![Screenshot 2025-02-07 at 1 36 39 2PM](https://github.com/user-attachments/assets/cb3f2e5e-3cdc-4cab-9dd8-a319944d2299)

- When you make a link <HOME>- React router Dom keeps a track of <HOME> with anchor tag and don’t refresh it 
& Doesn’t refresh 
## Q: routing with example 

```javascript
import { createBrowserRouter, RouterProvider, Outlet } from "react-router-dom";

const App = () => {

  return (
    <div className="app">
      <Header />
      <Outlet />                          // will be filled with children routes
    </div>
  )};

const appRouter = createBrowserRouter([    //create Router config 
  {
    path: "/",
    element: <App />,
    children: [
      { path: "/", element: <Body /> },
      { path: "/about", element: <About /> },
      { path: "/contact", element: <Contact /> },
      {path:"/resturants/:resId", element: <ResturantMenu/>}
    ],
    errorElement: <Error />,
  },
]);

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<RouterProvider router={appRouter} />);  //provide Router config 
```
# EP8 CLASS vs Function 
## Q.Class Phases 
So react life cycle Happens in two phase 
- 1)render phase 
- UPDATE DOM then 
- Part B: 2)commit phase

In general term - When `class is called` - it `instantiated` or created new instance 
`Constructor is called` - Then `render` is called
`when Dom is on the UI` - Then ComponentDIDmount 

#### Explation here 
Part A ----- Mounting CYCLE -----
-  Constructor (dummy)
-  Render (dummy)
  ```
  <HTML Dummy></HTML>
```
-     Component Did Mount
```
    <API Call>
    <this.setState> - State variable is updated
```
Part B----- UPDATE CYCLE -----
- render(API data)
```
  <HTML (new API data)>
```
-  Component Did Update
-   Component Will Unmount
![Screenshot 2025-02-07 at 4 05 10A PM](https://github.com/user-attachments/assets/d0cf4dc0-bd6a-43e1-9cc9-8d0808f8471d)

## Q.Component DID mount is used ?
- used to make an api call , why it is made ? becuase it follows approach
- Load->Render(Skeleton ) -> API call(ComponentDIDmount) -> Re-render(with API data)

## Q. ComponentDidUpdate when it is called ? - when state changed VS Functional
```
this.setState({
      count1: count1+1,   
      count2: count2+1,  
    });
```
- count1 and count2 changed
```
componentDidUpdate() {
    console.log('Component Did Update');
         if (prevState.count1 !== this.state.count1) {
        // Means your count1 got changed do the operation 
    }
    if (prevState.count2 !== this.state.count2) {
        // Means your count2 got changed do the operation 
    }}
```
- Functional
```
  useEffect(
  ()=>{},
  [count1,count2])
```
## Q. componentWillUnmount when it is called ? changing component VS Functional
```
ComponentDidMount(){
this.timer = setIntervel(()=>{console.log(‘’PRINT HITS’)},1000)
}

componentWillUnmount(){
Clear.Interval(this.timer)}
```
Eg- once we go away current component to new Component `not page` because its SPA
- BAD thing ABOUT SPA you dont change the Page:So if some setInterval is coded and when you are changing your component its not reloading your page 
- it just changing the component and React is reconciling it
- Functional
  
```
useEffect (()=>{setIntervel(()=>{console.log(‘’PRINT HITS’)},1000)
 // how to stop this
Return () => {}  // this is stop when moving from current component
},[])
```
## Q. In CC can we call setState inside Constructor? and BIND
- Setstate: cannot be called inside constructor because - when object created Constructor fired automatically
- inside useState can we call API ? yes but its performance issue
- BIND: data is not used outside the constructor so if you want to use it then Bind this parameter inside constructor

# EP9 Optimizing APP
### 1)Single responsibility component
- Modular - Testable, Maintainable ,reusable , Abstract
- Testing will be easy each component Distributing your code into small pieces
```
Eg
Resturent card- will display only the Resturent
Header.js- only display Header component 
```
### 2)Custom Hooks: readable,modular,reusable, `to make module Single responsibility component`
- For eg. Resturent card- will display only the Resturent but fetch you can create UseFecth customHook
- you don’t need manage state inside ResturentCard display
- useComponent prefix tells reader its customHook where react logic written 

### 3)Make system green or red on online or offline 
### 4)Bundeling: Dynamic Bundeling ,code splitting, lazy loading, chunking , On Demand Loading 
- Bundeling - when you build the app all your code bundles to one -JS file, 1- CSS file, 1-HTML file
- All your application bundled to 1 JS file inside DS once you build but as size grows its time taking to load application 
`So you need to bundle it based on logic`
```
Eg MakemYtrip
1 Bundle- Logical bundle - has all flight  JS
1 Bundle- Logical bundle - has all Hotel  JS
1 Bundle- Logical bundle - has all Train  JS
1 Bundle- Logical bundle - has all BUS  JS
```
```
Const Hotel= lazy(()=>import(‘ ../Hotel’))
This will create separate Logical bundle - has all Hotel  JS in DIS folder once you click on hotel
```
- Lazy loding : Route based 
```javascript
import { Suspense, lazy } from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

const Login = lazy(() => import('./Login'));
const Dashboard = lazy(() => import('./Dashboard'));

const App = () => (
  <Router>
    <Suspense>
      <Routes>
        <Route path="/" element={<Login />} />
        <Route path="/about" element={<Dashboard />} />
      </Routes>
    </Suspense>
  </Router>
);
```
- Code Splitting : webpack.config.js supports code splitting 
```javascript
   module.exports = {
     optimization: {
       splitChunks: {
         chunks: 'all', // or 'async', 'initial'
         cacheGroups: {
           vendor: {
             test: /[\\/]node_modules[\\/]/,
             name: 'vendor',
             chunks: 'all',
           },
         },
       },
     },
   };
```
```link
https://www.linkedin.com/pulse/optimizing-react-performance-lazy-loading-code-splitting-alex-lomia/
```

### 4)Suspence 
```
Once you click on Hotel this code is not available 
It renders but since code is not available it will render and throw error 
You can wrap you component to <Suspence><Hotel/><Suspence/> 
 OR
<Suspence fallback={<h1>Loading…. </h1>}><Hotel/><Suspence/>
```
```
 {
        path: '/grocery',
        element: (
          <Suspense fallback={<h1>Loading...</h1>}>
            <Grocery />
          </Suspense>
        ),
      },
```
![Screenshot 2025-03-10 at 4 58 27 PM](https://github.com/user-attachments/assets/319eb10c-ab21-4baf-a5f0-5a0e7e0dbcad)


## Q. Babel ?
- Babel: toolchain - ECMA 2015 convert backward compatible version of JS in current or Older version browser 
Compatibility between different javascript 
- Transform syntex, polyfil- means if code not available then generate code and make available 

- JSX code to simplify complexity in code - js+ html but React compiler does not understand	JSX 
- Babel converts JSX to react js compiler compatibility by Transform syntax 
- Polyfil if code does not able to transform  in that case it takes out compatible code patches and covert eg. map function 

# EP-N Hooks: 
### Q1. useContext ?  many nested components. The component at the top and bottom of the stack need access to the state.
- It Solve  need to pass the state as "props" through each nested component ` "prop drilling".`
```javascript
import { useState, createContext, useContext } from "react";
const UserContext = createContext();

function Component1() {
  const [user, setUser] = useState("Jesse Hall");

  return (
    <UserContext.Provider value={user}>
      <h1>{`Hello ${user}!`}</h1>
      <Component2 />
    </UserContext.Provider>  );
}

function Component2() {
  return (
      <h1>Component 2</h1>
      <Component3 />  );}

function Component3() {
  return (
      <h1>Component 3</h1>
      <Component4 />);}

function Component4() {
  return (
      <h1>Component 4</h1>
      <Component5 />);}

function Component5() {
  const user = useContext(UserContext);

  return (
      <h1>Component 5</h1>
      <h2>{`Hello ${user} again!`}</h2>);
}
```


### Q2. useRef : persist values between renders
- Does Not Cause Re-renders, can be used for storing previous state value 
- Tracking State Changes
- Accessing DOM Elements directly - focus
```javascript
import React, { useRef, useEffect } from "react";

function MyComponent() {
  const checkboxRef = useRef(null);

  const handleButtonClick = () => {
    if (checkboxRef.current) {
      // Access and modify the DOM directly (less recommended) - TOGGLE
      checkboxRef.current.checked = !checkboxRef.current.checked;

      // You can also access other properties:
      console.log("Checked state:",checkboxRef.current.checked,"Checkbox element:",checkboxRef.current
      );}};

  return (
    <div>
      <input type="checkbox" ref={checkboxRef} />
      <button onClick={handleButtonClick}>Toggle Checkbox</button>
    </div>
  );
}

export default MyComponent;

```
```javascript
function App() {
  const inputElement = useRef();

  const focusInput = () => {
    inputElement.current.focus();};

  return (
      <input type="text" ref={inputElement} />
      <button onClick={focusInput}>Focus Input</button>)}
```

### Q3.useCallback- eg. dynamic filed addition with other operation 
-useMemo returns a memoized value and useCallback returns a memoized function.
```javascript
import { useState, useCallback } from "react";
import Todos from "./Todos";

const App = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState([]);

  const increment = () => {setCount((c) => c + 1);};

  const addTodo = useCallback(() => {
    setTodos((t) => [...t, "New Todo"]);
  }, [todos]);

  return (
    <>
      <Todos todos={todos} addTodo={addTodo} />
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
      </div>
    </>
  );
};
```

```javascript
//Todo.js
import { memo } from "react";

const Todos = ({ todos, addTodo }) => {
  console.log("child render");
  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => {
        return <p key={index}>{todo}</p>;
      })}
      <button onClick={addTodo}>Add Todo</button>
    </>
  );
};

export default memo(Todos)
```
### Q4. useMemo
```javascript
import { useState, useMemo } from "react";

const App = () => {
  const [count, setCount] = useState(0);
  const calculation = useMemo(() => expensiveCalculation(count), [count]);

  const increment = () => {    setCount((c) => c + 1);};
  return (
    <div>
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
        <h2>Expensive Calculation</h2>
        {calculation}
      </div>
    </div>
  );
};
```
```javascript
const expensiveCalculation = (num) => {
  console.log("Calculating...");
  for (let i = 0; i < 1000000000; i++) {
    num += 1;
  }
  return num;
};
```
### Q5. customFetch: component logic that needs to be used by multiple components
```javascript
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);

  return [data];
};

export default useFetch;
```
```javascript
call in your component
const Home = () => {
  const [data] = useFetch("https://jsonplaceholder.typicode.com/todos");}
```
