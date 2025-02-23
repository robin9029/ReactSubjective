JOb

### HTML 
- eventListner 
- Placeholder 
#### JS 
- https://github.com/sudheerj/javascript-interview-questions

### youtube
```
https://www.youtube.com/@DevAditya/
https://www.youtube.com/@reactdeveloperinterviewseries
https://www.youtube.com/watch?v=uknTKIsptGM
https://www.youtube.com/@interviewguideformnc/videos
https://www.reddit.com/r/webdev/comments/t9gdrx/developers_who_work_100_remotely_how_did_you_get/
```
### 5 Project to revise :
```
Callback:  https://stackblitz.com/edit/react-ts-sgesnf?file=App.tsx,ComponentB.js,ComponentA.js,index.html
card: https://codesandbox.io/s/nervous-night-2unonk?file=/src/CardList.css:80-84
Table: https://codesandbox.io/s/laughing-johnson-cvv16k?file=/src/App.js
Form Validation:https://codesandbox.io/s/amazing-dhawan-9eeeky
Route https://codesandbox.io/s/r0wxp0njw?file=/index.js
Test: https://codesandbox.io/p/sandbox/confident-frost-cbcd6o?file=%2Fsrc%2Findex.js
https://codesandbox.io/p/sandbox/intelligent-grass-p43q9y
https://stackblitz.com/edit/react-5pmxbh?file=src%2FApp.js,src%2FEventHandler.js,src%2FApp1.js,src%2FHeader.js,src%2FDimExample.js,src%2FParent.js
https://github.com/srwaditya/Javascript_Tutorial/blob/main/Nagaaro%20Interview%20Question
https://www.youtube.com/watch?v=gaFA9gOore0
https://www.educative.io/blog/react-router-tutorial
Test css: https://www.javatpoint.com/css-mcq
Test html : https://www.javatpoint.com/html-mcq
```

1) Terms: to translate screen mockups from design team into pixel perfect Web app screens including animations 
2) Responsive UI
3) Performance/optimization : Lighthouse - https://techblog.geekyants.com/improve-web-app-performance-using-lighthouse
4) Testing : jest,engyme 

Keyword: 
GraphQL

https://www.servicenow.com/community/now-platform-forum/when-to-use-stringify-and-when-to-use-parse/m-p/1107046

### JSON OBJECT
- To convert JSON data/String --> JavaScript object using the built-in JSON.parse() function. For example,
- Receive = parse  
```
// json object
const jsonData = '{ "name": "John", "age": 22 }';

// converting to JavaScript object
const obj = JSON.parse(jsonData);
{ "name": "John", "age": 22 };
```
-  To convert JavaScript objects --> JSON format/Data(JSON data can also be referred to as JSON String) using the JavaScript built-in JSON.stringify() function. For example,
- Bhejne waqt STRINGYFY - JSON OBJEct 
```
// JavaScript object
const jsonData = { "name": "John", "age": 22 };

// converting to JSON
const obj = JSON.stringify(jsonData);

// accessing the data
console.log(obj); // "{"name":"John","age":22}"
```


# 1 Others Interview 1
```
1 O/p 

“A”-“B” = NAN
“2”-“2”. = 0
"2"+2.  = ’22’
2 Event loop ? - call stack, callback queue , MicroTask queue has proiority these has been provided by browser runtime/node runtime 
				Event checks- call stack empty 
			promise & setimeout ? Which one executed ? Promise because promise runs on Microtask queue

3 HOC ? Return function ,accept function eg. map, filter reduce 
4 prototypes: default constructor - default object is created - will point to null, 
			everything point to Prototypes - object.prototype-> keep going down it will be NULL
			javaScript engine looks for it in the object's prototype chain.
5 this keyword ? Behave different - function/by default global scope , arrow function : point to parent object    
		Function strict mode: refers to undefined 
		Event refers to : element
6 JSX- understand by browser? : no Babel 
7 Middlewhere, logger ? - middle where solve the problems of asynchronous call of Redux,
		 so it intercept between action before it reaches to reducer
	I want to dispatch the action- and also hit api and once retrieval of data I want to send this data along with dispatch
8 Adv and disadv of React ?- Virtual DOM , fast ,easy to debug - disadvantage - its library only view layer, routing it need router, redux for state management 
9 Can our component re-render without setState or without	updating  ? rendering list element we pass  Keys attribute to list element,
				react remember which keys deleted , updated , added - rendering fast, if we pass data as props and if key got changed it will re renders
				- 1. Parent Component Re-Renders 
				2. Context Changes
				3. Force Update
				4. React hook dependency changes 

11 Lifecycle methods how to implement in function ? useEffect(side effect, dependency )
```
# 2 Others Interview 2
```
1 Hooks ? - lifecycle management	,features - useeffect(lifecycle management, fetching data,),useref,useMemo
2 Features of react- jsx,one way data binding, Virtual DOM
3 Jsx- javascript xml, helps developer  to write html in react 
4 Component: resuseable peace of code , anywhere we can use 
5 Real dom VS Virtual DOM: copy of real dome , if any changes - VDOM process only chain line of code - inlace of processing complete line by line code 
6 Redux flow orally: store -> component-> container(map state and dispacth)-> once action performed it will dispacth action to reducer to update state 
7  JS: creating interactive UI application 
8  map - transformation (for every square of each element  )& filter->(filter and find if odd numbers ), find - return the first element which staisfy the testing condition 
9  map vs foreach: both used for perform	, map creates new array 
		https://stackoverflow.com/questions/34426458/javascript-difference-between-foreach-and-map
forEach()	map()	
Functionality	Performs given operation on each element of the array	Performs given "transformation" on a "copy" of each element
Return value	Returns undefined	Returns new array with transformed elements, leaving back original array unchanged.
Preferrable usage scenario and example	Performing non-tranformation like processing on each element.

For example, saving all elements in the database.	Obtaining array containing output of some processing done on each element of the array.

For example, obtaining array of lengths of each string in the array
If you want to do MAP, foreach and store in variable - map return value but Foreach return undefined  
10 props: property	basically pass the data from parent component to child
11 state vs props: class component , store data inside component 
12 reactRoute: route to different page, move different page
13 html:  is layout on web pages 
14 html layout: header, footer, head, title,
15 tags in html: determine what element containg h1- highest, h6-last, how the element should be seen to the user 
Css 
16 strong type VS bold type: strong - how important the content is & bold- for highlighting 
17 external css, inline  : types of css- internal 
```

# 3 Others Interview 3

```
1 difference between let and const and var scope - var support hosting - undefined used  before declared , for let & const - reference error 
		- move top of scope 
		- const has block scope - reference is constant , for object/array we can update	
2 spread operator : update object
	const student = { name: 'ravi',place:'Sahibganj',age:33}
	let StudentOne = {...student,name:'Kumar'}
	
3 javscript is Single threaded or multithreaded - single , then how it performs	Asynchronous -
	-Single threaded:  FIFO 
	- for Asynchronous- we have promise and callback 
4 what is EventLOOP- moving execution context from call stack to call stack , keep looking on call stack if it is empty provide with the execution context
			- Microtask queue (fetch api)- provide more priority than callback queue (setTimeout)
5 closure ?-  child function declared inside parent function  - child function will have the access to parent function variable 
function x(){
    let a =10;
    function y(){
        console.log(a)
    }
    return y()
}
Var z= x
z() // 10
6 function currying  function :can to transformed - taking value and returning function  ..keep doing 
https://stackoverflow.com/questions/36314/what-is-currying
Event curry 
var x= (a) =>(b)=>{ return a*b}

console.log(x(2)(3))
here a function with multiple arguments is transformed into a series of functions, each taking a single argument.
Instead of taking all arguments at once, the curried function takes the first argument, returns a new function that takes the next argument, and so on until all arguments are provided. The final function then returns the result.


7 what is react js, state , props -pass data from parent to child
	- class we can update setState(name:”xyz”), this.state{}
8 how to pass child to parent : using callback 
9 lifecycle methods in class- componentdidmount,componetdidupdate,componentwillUnmount 
10 useEffect   What happens for an useEffect with no second argument or one equal to null or undefined ?
		no second argument or one equal to undefined or null, yes the callback will get executed on every render
12 redux 
13 //number =5431 = 5+4+3+1 =13 = 1+3 = 4

function convertSingleDigit(n){
    //let str = `${n}`
    let arr = [...`${n}`].map(Number)            let arr = `${n}`.split('').map(Number)
    //console.log(typeof arr,arr)
    let sum = 0	
    for(let i =0; i<arr.length;i++){
        sum = sum+ arr[i]
         console.log(sum)
    }
    if (sum > 9) return convertSingleDigit(sum)
    // console.log(typeof str)
    return sum
}
convertSingleDigit(5431)
```

# 4  Others Interview 4 : https://www.youtube.com/watch?v=9cQsv91zBsc&t=838s
```
1 Precedence in eventLoop- setTimeout and promise which ? Promise because microTask Queue
2  setTimeout  VS setInterval : setTimeout (executes only once, after timer expired 	)and setInterval (runs on every interval what time you have mentioned)
	-HOW TO STOP: using clearInterval(null)
3 ES6 features: let const,arrow function ,spread operator, rest operator, Template Literal, promise 
4 rest operator  where we are using : function parameters  (name, age,…rest )
5 palindrome abcba how to check - reverse function 
6 reverse function in javascript: reverse any element inside it 
7 what is difference between shallow copy and deep copy : [deep means new copy][shallow means reference ]
		deep means simple copy & forget owner , copy to another storage and forget or disconnected from owner [NEW]
		shallow copy: = copy , reference copy address[SAME]
		
8  what is closure:
 a variable declared outside function - while that be closure to this function : NO 

function sayHello() {
  var say = function() { console.log(hello); }
  // Local variable that ends up within the closure 
  var hello = 'Hello, world!';
  return say;
}
var sayHelloClosure = sayHello(); 
sayHelloClosure(); // ‘Hello, world!’

9 map vs reduce : map : square of all number, reduce : add all number - parameter accumulator, current value or index and value 
10 promise vs callback: 
	- enhancement of callback 
	- 3 state - pending , successed, reject
css
11 position attribute used: absolute, fixed: if any element is position fixed it will be fixed to that element   
				position	absolute: parent, child element - if put position absolute on child then it will relative on parent 
							it will be relative to the container/body/parent 
				position relative : relative to the  normal flow of document / moving based on where it was kept DOM
				
12 flex box- it can been used to make our page responsive 
13 display none : completely removes the element 
	visibility hidden : it keeps the element position and only  hide 

React : 
14 hooks : function useState,useEffect, useReducer,useSelector,useMemo,useCallback
	useCallback: used 
		useSelector: access to redux state 
		import { useSelector } from 'react-redux';

		function MyComponent() {
	  const counter = useSelector(state => state.counter);
	  // use counter value in component
	return (    <div>      <h1>Counter: {counter}</h1>    </div>  );}

15 useMemo and callback: both used for unnecessary renders, improve performance  
	useMemo used for basically remembering heavy calculation-  1 lac loop - just remembers it: copy the calculation : remember- cache result
	callback: for others state changed it also re render causing bad performance 
			-eg we have 2 function - once counter increment, 2 - we have TODO
			- want to remove List item data, so logic passed into the remove function cause rerender  : remember- function 
16 life cycle methods - getDerivedstatefromProps - when called : before render
17 what is the first lifecycle got called - constructor 
18 Pure component : improve performance, only render when props & state changed 
				- implement shouldComponentUpdate
19 HOC- accept function and return function eg- MAP,reducer, js -curring closure 
20 Redux ,contextAPI
21 middle where - thunk : intercept the action 
```
# 5 Other interview : 5
```
1 controlled VS uncontrolled ? Controlled component- form data is handled by React component, uncontrolled : form data is handled by DOM
2 Adv of React hooks?: simple implementation- life cycle methods, simple 
3 JSX? - java script which provide write HTML in react
4 state vs props ? State: use to store info in Component- internal to component, props to pass the data to Parent component to Child
5 keys in Reactjs? It will help to manage/identified - what item added/remove 
		const items = ['apple', 'banana', 'cherry', 'date'];
		const updatedItems = items.filter((item, index) => index !== 1);   //key=index , remove element @banana

		const list = updatedItems.map((item, index) => (
			  <li key={index}>{item}</li>));             :// correct approach is   <li key={item}>{item}</li>));

		return <ul>{list}</ul>;
Incorrect Use of Keys (Index as Key): Using the array index as a key is not ideal when the list can change (e.g., items are added, removed, or reordered). It can lead to incorrect re-renders.
6 HOC: accepts fun and return function - maps, OR accepts component in arg and return new component - with additional features /resue 
		button click 
7 Real DOM vs Virtual DOM ? Real DOM :Processing will done on every line of code -slow
				Virtual DOM: if anything changed it will process that line of code 
8 useMemo- -imporve performance by not unnecessary re-render, only re-render when its props or sate got changed 
			save heavy calculation wrap the component , it memoize the component 
9 useContext - state Management - state can be managed globally 
10 Redux vs UseContext: for larger 
		For simpler applications with basic state management needs, useContext may be a good option to consider. 
                 On the other hand, for more complex applications with multiple data sources and complex state updates, 
		Redux may provide a more efficient and scalable solution.
11 function fun1(){
    setTimeout(() => {console.log(x);
        console.log(y)
    },3000) ;
    var x=2;
    let y=7;
}
 
fun1()
o/p2,7
 
11) 
let x ={},y={name:"Ronny" },z={name:"Jhon"}
 
x[y] = {name:"Vivek"}
x[z] = {name:"Akki"}
console.log(x[y])
console.log(x[z])
console.log(x)
 
o/p
{name: 'Akki'}
{name: 'Akki'}
{[object Object]: {name: 'Akki'}}
```

# 6 Other interview : 6
```
1 Class Vs function ? Class - keywords, extends from React.Component, constructor( super/this.state/bind} lifecycle management 
				 function- keywords -life cycle management- use effect, NO Random methods, Easier to test - simply JS function 
2 which one to use ? - Class for more complex- data management and state management 
3 Redux thunk: 
￼

Middleware Thunk : used to handle action which might be not be synchronous - 
				if we use AXIOS -its asyncronous	
				redux-thunk allow -dispatch function asynchronously  and resolve the promise 

4 hooks- useEffect,useState, useMemo,useref
5 control.log in project why do you used? For testing purpose what data is arriving 
	import { ErrorHandler} from 'universal-react-logger'; wrap component to APP

6 if big project - if lot of console log it will create huge log - how to resolve - how to switch on control or switch off control: 
	Since log is part of the window object, you can simply access the window object and disable it
```

# 7 Others Interview 7
```
1 Features of React: Virtual DOM, View layer, fast, one way data binding, JSX-write HTML, component- reuse
2 One way data binding ? - data flows in one direction 
3 use of babel: compiler converts JSX- into Javascript OBJECT
4 Virtual DOM vs real dom 
5 React is framework vs library: js library
6 use of ES6: provide features: let,const,arrow,destructure, promises, callback, 
7 Different part of component in React js: function/class- which is best ? - HOOKS -16.8 function
								- no render function , return uses, less line of code - due to hooks 
								- it depends on project
8 useState- const [state,SetState] = useState(initialValue ) 
9 controlled:form handled react Vs Uncontrolled:Form handled by DOM 
10 prop drilling : moving one component A(data)->B(data)->C(data)->D(data), cannot got from a to b
11 can we create custom Hooks
12 React.strictmode :unsafe use of lifecycle, warning about something deprecated, detecting legacy, suggestion 
https://legacy.reactjs.org/docs/strict-mode.html
13 pass the data between component: callback function , props, context api, redux
				which one is better : redux,
14 Redux is cashing server : 3rd party ?
15 Router- how router work in react how it is used  : 
	import { Switch, Router, Route } from 'react-router'
	import { withRouter } from 'react-router-dom'
	import { Route } from 'react-router-dom'

<BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} />.         //Index.js means HOMEPAGE
          <Route exact path="blogs" element={<Blogs />} />.  //exact means - exact path 
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />.   //Not Found
        </Route>
      </Routes>
    </BrowserRouter>
16 DB/NODEJS- Joins left joins -all record of left side and 
```

# 8 Others Interview 8
```
HTML
1 !DOCTYPE: information to browser what document type is expected 
		<!DOCTYPE html>
Older version: <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"> what version of HTML 
2 CSS3 vs CSS ?  CSS3 makes the Web Pages more attractive.
					css can be splitted into Modules ,faster ,latest version
3 BOX sizing in css: allows include the padding and border in an element's total width and height

JS
1 ECMAscript? Standrad for Scripting language -web application 
2 let vs const vs var: var: hoisting: declare before use , function scope, let & const is - block scope 
					const: can’t be declare without initialisation 
					let can be declared without initilazion 
3 global key- payment keys/ gateway keys- these are common and can’t be changed 
			- store in CONST : block
			- store in VAR: GLOBAL
What is difference and how this will impact code/speed: VAR,GLOBAL- increase the speed - we can’t	be used for const

4 Spread operator: example : a[1,2], b[3,4]. = c= […a,…b]
5 arrow function : does’t use Function keyword, return keyword only used inside {} eg 
		let numbers = [4, 2, 6];
                  numbers.sort((a, b) => return (b - a));  // wrong 
6 Typescript-OUT of Syllabus
7 SetTimeout: runs after timer  ends-no repeat vs SETINterval : unlimited time keep fire 
		set interval - how to stop for certain interval 
		use clearInterval(NULL)
8 const arr = [1,1,2,3,1,4]- highest occurrence in array & how many times it occurred 
const arr = [1,1,2,3,1,4]
const count ={};
for (const element of arr){
    if(count[element]) {     count[element] +=1;}
    else {        count[element] =1;    }
}

console.log(count)

{ '1': 3, '2': 1, '3': 1, '4': 1 }
```

# 9 Others Interview 9 ******

```
1 Redux vs Hooks
2how to add css and javascript globally in react js
	public folder : styles.css in the css directory and app.js in the js directory.
 In the public directory, open the index.html file.- inside HEAD tag
	<link rel="stylesheet" type="text/css" href="%PUBLIC_URL%/css/styles.css">
  body tag 
        <script type="text/javascript" src="%PUBLIC_URL%/js/app.js"></script>

OR: CSS-> import * ./src/styles/global.css
	js-> import scriptTag rom react-script-tag
react-script-tag is a React component that allows you to add external script tags to your React application

3 sort object array in ascending order:
objArrary = {name:”rahul”,name:”pinki”,name:””basheer”}
https://www.w3schools.com/js/js_array_sort.asp

objArray.sort(function(a,b){
	let x= a.name.toUpperCase()
	let y= b.name.toUpperCase()
	if (x<y) return -1;
	if (x>y) return 1;
return 0; 

})
4 this is the domain and we have a query & parms in it www.google.com/45/?id=89 
Write a function to get parts and query: SEARCH: trying to find id=89
https://reactrouter.com/en/main/hooks/use-search-params
https://nextjs.org/docs/app/api-reference/functions/use-search-params

 useEffect(() => {
    const url = new URL("http://www.google.com/45/?id=89");
    const params = new URLSearchParams(url.search);
    
    const id = params.get('id'); // get value of id PARMS
    console.log(id);
    
    const query = url.pathname.split('/')[1]; // get the query string after the domain
    console.log(query);
  }, []);

OR : https://medium.com/@bobjunior542/how-to-use-usesearchparams-in-react-router-6-for-url-search-parameters-c35b5d1ac01c

Const [searchParms, setSearchParms,] = useSearchParams(). 
		// you to access and manipulate the query parameters in the URL
		//useSearchParams hook returns an array with two elements: the current search parameters and a function
// www.google.com/45/?id=89 
const q = searchParams.get(‘id’);   // this will Provide ID=89

Const [query.setQuery] = useState(searchParams.get(query))

5 create button createElement[’Tag’, function , display]
  <button className=“my-button" onClick={() => console('clicked')}> click me <button >

const buttonElement = React.createElement(.              //createElement can be replaced by JSX
	  'button',
  	{
    		className: 'my-button',
   		 onClick: () => console.log('Button clicked')
  		},
 	 'Click me'
);

function MyComponent() {
  return (
    <div>
      {buttonElement}
    </div>
  );
}
```

# 10 Other Interview 10

```
Q what is optional chaning ? Trying to access nested object if it doesn’t exist give error 

const obj = {
  prop1: {
    prop2: {
      prop3: "Hello world"
    }
  }
};

console.log(obj.prop1.prop2.prop3); // prints "Hello world"

console.log(obj.prop1.prop2.prop3.prop4); // Uncaught TypeError: Cannot read property 'prop4' of undefined
To resolve this
const obj = {
  prop1: {
    prop2: {
      prop3: "Hello world"
    }
  }
};

console.log(obj.prop1?.prop2?.prop3); // prints "Hello world"

console.log(obj.prop1?.prop2?.prop3?.prop4); // undefined

// trying to access prop4 does not exist - no error 
```

# 11 Other Interview 11
```
1 regular fun VS  arrow Function : bind , simple es6 

Regular function:This Binding: this within a general function is determined by how the function is called.
const obj = {
    name: 'John',
    greet: function() {
        console.log('Hello, ' + this.name); 
    }
};
obj.greet(); // Output: "Hello, John"

Feature	General Function	Arrow Function
this Binding	Dynamically determined	Lexically bound
Hoisting	Hoisted	Not hoisted
Syntax	More verbose	More concise
Flexibility	More flexible this	Less flexible this

Arrow: 
This Binding:
* this within an arrow function is lexically bound to the surrounding context (the this of the enclosing function or the global object if not within a function).
const obj = {
    name: 'John',
    greet: () => {
        console.log('Hello, ' + this.name); 
    }
};
obj.greet(); // Output: "Hello, undefined" (or the global object's `name`)


2 callback function : we can pass a function as argument and return and value 
	function callback(x) { return x>0 } 

	var   arr = [1,2,3,-6,8]
	function removeNeg( arr,callback){
    			for(const i of arr){
			       if(callback(i)){
				           console.log(i)} }}

removeNeg(arr,callback)
OR removeNeg(arr,(x)=>{return x>0})
VM745:4 1
VM745:4 2
VM745:4 3
VM745:4 8

3 Recursive function : function calling itself  - if number given 3 o/p 1+2+3

 function RecursiveFun(n){
   if (n>0) return n + RecursiveFun(n-1)
   else return n;
}
console.log(RecursiveFun(9))
4 Functional VS class based : similarities -lifecycle 

5 call api on Mount & unmount  https://www.benmvp.com/blog/handling-async-react-component-effects-after-unmount/
Or: https://blog.logrocket.com/understanding-react-useeffect-cleanup-function/

import { useState, useEffect } from 'react'

const Results = () => {
  const [items, setItems] = useState([])

  useEffect(() => {
    let mounted = true
    fetchItems().then((newItems) => {
      if (mounted) {
        setItems(newItems)
      }
    })

    return () => {  mounted = false}
  }, [])

  // render UI
}
4 useRef 
5 Routing Technique : https://www.w3schools.com/react/react_router.asp
BrowserRouter: will stores the current location  & navigate using but in history stack
 <Routes> will match a set of child routes from the current location 


Import {BrowserRouter,Routes,Route} from ‘react’-router-dom

Function Home(){
Return {
<h1>  Welcome to Home page </h1>}}

<BrowserRouter>
	<Routes>
			<Route Path=‘/’ index element ={<Home/>}/>
			<Route Path=‘blogs’ element={<Blogs/>}/>
			<Route Path=‘*’ element={<NotFound/>}/>
	</Routes>
</BrowserRouter>
6 if any thing crashes how to handling ? 
Class:	ErrorBoundry - componentDidCatch 
Function: 	useErrorBoundary
registerServiceWorker - for slow Internet 
7 lazy loading : 
		const OtherComponent =React.lazy() => import (‘’./OtherComponent’)
		function Mycomponent(){
		return (
			<div>OtherComponent</div>) }
```
# 12 Other Interview 12: CTS: https://www.youtube.com/watch?v=mgibv2rXiEU
```
1 what is EventBubbling and eventLooping in Javascript
	EventLoop: handles asynchronous data 
	EventBubbling: when there is event Trigger nested of Element handled by Parent DOM 
				- tries to handle by EVENTHANDLES Then BUBLES to Parent element & continues happen till it reaches root 
				-event.stop Propagarion 
				-eg- when you tries to hit button there are multiple event defined on same button 
CSS
2 Semantic tag in HTML -have some meaningful name and easly readable   header/footer/vertical 
3 BOX model: how element on webpage can be render & calculate : content, padding ,border, margin  [MBPC]
		how to increase the space between Two element : Margin 
		content of element with Border : Padding
4 flex box: making page responsive 
5 Psudo classes (:first-child, hover )and Psedu element  (<P>::first-letter)
	https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements
	Psudo classes : specific to state 
	Psudo Element: add new HTML element 
	
JS
6 Closure : Hiding your code data scurity 
7 Var vs Let - Hoisting 
React 
8 change buttonColor of Input onChange event in classBased Component 
9 for every change in textbook will trigger the Render how to prevent that 
	Debouncing is commonly used for scenarios like search input fields, where you want to wait for the user to finish typing before triggering a search request.
	Throttling is commonly used for scenarios like handling scroll events, where you want to limit the frequency of function invocations to avoid performance issues.
	PreventDefault()
Part 2: https://www.youtube.com/watch?v=h4QOOvzk0UM

1 Virtual DOM 
2 JS engine differs Chrome V8, spiderMonkey-Mozilla,Chakra - Microsoft : due to Open Scource , performance wise , what also need to be removed 
	code parsed -broken into token- moved for Intreprator-JIT(just In time compiler )- optimisation and garbage collector 
3 setState : why we can’t do it directly - 
4 Set default props : if the properties is not provided in parent class we can for Null it will not work
5 Redux mapStateToProps,mapDispatchToProps
		where is your reducer inside ? Store 
		mapDispatchToProps- what dispatch function is- go for action 
6 Multiple reducer component how your component will identifier which reducer called  
		- combineReducers we can use key Value pairs 
		- while accessing state we have to mentioned the corresponding ‘key’ as state inside MapStateToProps
7 closure : Data hiding 
8 Flux: ?
9 Node js : how to Increase performance of your application 
10 Deployment 
11 Code qualityL how you check is high quality -light house
	-Unit testing, 
	- Performance testing 
	- Jest testin - toMatchSnapshot render code coverage 
 ```

# 13 Other Interview 13
```
1) function x(){
        setTimeout(() => {
      console.log(i);
    }, 1000)
        var i=10}
x() //10
2 
setTimeout(() => {      console.log(2);    }, 1000)
setTimeout(() => {      console.log(1);    }, 1)
O/p -1,2
3 if nested object how to store in array: recursive function 
4 Lifecycle Methods - how to convert class to Functional 
5 where to call api in redux- componentDidMount -ACTION 
6 Why we need middle where in Redux- intercept action 
	-Modifying Action Payloads,Analytics and Tracking,Error Handling,Logging and Debugging,Authentication and Authorization-token refresh
7 different between reacts Next js - ssr,make our API,fixed rendering
8 styling -bootstrap,css ,saas,less,Material UI
9 testing -unit testing -jest,engyme - what is strategy -which component go for unit testing - snapshot for all the component 
10 requirement - support eng & Hindi - globalisation we can use many library - es Intlization ,
11 how to retrieve data and display whose age > 40 
```
# 14 Other Interview 14
```
1) 
<body>
    <h1 class='heading'>hello </h1>
    </body>
h1{color:blue}
h1{color:red}
2) what is class in javascript in ES6 ? Before es6 class was existed in form of Function 
3)  constructor function in JS  and how to create new object 
	function person(name,age){ 	this.name=name;
	this.age =age
	}
Var person1 = new Person(‘Ravi’,23) how this work in function 
4 )what is closure 
5) find the unique data in arraylist ?
 Const input = [2,3,5,6,7,3,4,5,3] 
Const unique = […new Set(input)]
OR 
const uniqueArray = [];

for (let i = 0; i < input.length; i++) {
  if (!uniqueArray.includes(input[i])) {
    uniqueArray.push(input[i]);
  }
}
6) let a = {
    name:"test"
}
let b ={...a}				//DEEP copy 
b.name='test2'
//a =test
//b=test2
7) 
let a = {
    name:"test",
    add: {code:1}
}
let b={…a}
b.add.code=2
// a & b will be same  : Because Deep copy b={…a} but a.add.code is not DEEP COPY is an object which refer to same address 

8)Polyfill of promiseall
9) parent JSX

Const [state1,setState1] =useState(0)
Const [state2,setState2] =useState(0)

Return <props state={state1}>

Child jsx
Return <div>{props.state}</div>
1)If Change in state1 will pre-render parent as well as child 
2) If change State2 will not rerender child component 
```

# 15  Other Interview 15 LTI https://www.youtube.com/watch?v=BG1fDZbrBDU
```
1) HOC how it will help ? What it is going to solve problem
2) how do you manage data in Project ? Function based -useState(), class based setState - Redux 
3) Middlewhere -Redux Thunk 
4 Build tools ?  web pack 
What is there in web pack configuration file ? Entry point, output,Loaders,Plugin,mode,devserver,resolve 
```
```
https://blog.logrocket.com/versatile-webpack-configurations-react-application/
https://gist.github.com/iamshaunjp/a1c8fb653ddd5d27c3e38ab55e3c0a44

1. Entry Point: webpack starts bundling the application. 
2. Output: output path and the name pattern for the bundled files 
3. Loaders: Loaders are used to transform different types of files during the bundling process. For example, you may use loaders to transpile JavaScript with Babel, compile SCSS to CSS, or process image files. Loaders are configured using the module.rules property.
4. Plugins: Plugins provide additional functionality to webpack. They can be used for tasks such as code optimization, minification, environment variables injection, or generating HTML files. Plugins are configured using the plugins property.
5. Mode: The mode determines the webpack build mode, which can be either "development", "production", or "none". 
6. Dev Server: The webpack dev server allows you to run the application locally during development. 
7. Resolve: The resolve configuration is used to specify how webpack resolves module imports. You can configure custom alias mappings, file extensions, and module directories.
These are just a few examples of what you may find in a webpack configuration file. The actual configuration can vary depending on the specific requirements of your React JS project. It's common to have more advanced configurations for code splitting, optimization, and handling different environments.
Webpack is a powerful bundler that allows you to customize and fine-tune the build process to meet your project's needs. The webpack configuration file is where you define these customizations.
```
```
5)Error Boundaries ComponentDidcatch  6) code splitting - lazy loading 
7) Write a custom code to retrieve data & put error and loading logic from dummyJson 
8)  how the code will executes useEffect()
```

# 15 Part2  LTI https://www.youtube.com/watch?v=ssRvlc57CCk&t=222
```
1 Json data try print based on age in HTML 

const element =[{name: 'ravi',age:30},{name: 'avi',age:20},{name: 'vi',age:25},{name: 'iravi',age:35},]

const container =document.getElementById('myelement')

const res = element.filter(item => item.age<26)
console.log(res)

res.map(item => {
	const p =document.createElement('p')
	p.textContent = `Name : ${item.name} ===> Age: ${item.age} `
	container.appendChild(p)	
})



2 what is onBlur function :  if you have input textbox & typing something - then between you clicked somewhere it got called 
3)How to write Console.log()using Document 
Const container =
3 prototype Output
 
EmployeeName.prototype={
    names: [],
    showNames: function () {
        return this.names 
    }} 
var e1 = new EmployeeName();
e1.names.push("foo")        //foo
console.log(e1.showNames())

var e2 = new EmployeeName();
e2.names.push("bar")        //foo bar  when e2 Object created it access e1 names[foo]
console.log(e2.showNames())

4 write a promise which resolve if number less than 4 else reject 

 const myPromise= new Promise((resolve,reject) => {
    let value=6;							//change vale to see resolve 
    if(value<4) resolve("Value is less than 4")
    else        reject("value greater than 4")
        
})

myPromise
    .then(res=> console.log("resolved: ",res))
    .catch(err => console.log("error on rejection: ",err))

// error on rejection:  value greater than 4

5 closures 
6 Progressive Web App (PWA): Make our website run offline, like mobile app-we do not need any browser , set Friendly 
				how you will make your web app light weight minifying our code and reduce - google Insight/devtool
7 service worker : is JS-FILE, used to make our website run offline - to implement we have to register our application 
			 Service workers are event-driven and run in a separate thread from the main web page thread
			Back Ground Processing ,Background Sync,Caching and Offline Support
8 web pack - can we set any rules for setting css or better coding : esLINT
9 web accessibility : friendly for every one & loaded in correct manner - colour blindness, disability  
10 have worked on - AA,AAA standard 
			standards defined by the Web Content Accessibility Guidelines (WCAG).
			AA is the intermediate level of accessibility compliance
			AA is the highest level of accessibility compliance
		AA or AAA standards, web developers can ensure that their applications are usable by a wider range of users, including those with disabilities
```
#### 15  Part2-2  LTI 
```
https://www.youtube.com/watch?v=jBlRkN67h9A&t=194s
```

# 15 Other Interview 16: 
```
1 var a =10;
{
    var a = -10
}
let b =a
{
    let b = -20
}
console.log(b). //-10

2) c =25;
var c; console.log(c) //25
3) OOBJ - Polymorphism, -different form, abstraction:hide ,encapsulation:follow process -Petrol car put petrol ,inheritance- feature parent in child component super
4) tell me what are properties of class,- do a function can be properties of  
class Example { // Instance field name = "Instance Field"; 
			  // Static property static staticName = "Static Field";
			 // Instance method sayHello() { console.log("Hello!"); } 
			// Arrow function as a class property arrowFunction = () => { console.log("Bound to instance automatically"); }; 
			// Static method static staticMethod() { console.log("I am a static method"); } }
Function :Use methods for defining behavior and properties for storing data or references. Arrow functions as properties are often used to avoid binding issues.
```
### css
```
5 Visibility = none: does not take space VS viability= hidden : take space
6 Margin vs Padding : Padding : diff between content and broader    padding-space inside element , margin -space around element 
7) == VS === : == (Value),===(value & TypeOF)
8)SetTimeOut VS setInterval: SetTimeOut- fire once on time Elapsed, setInterval: fire on every equal interval/repeat
9) Var- global, const & let- local/function scope
10)Adv -react js
11) Data transfer data - Props /callback/context API/redux
12)State vs Props immutable : props are immutable 
13) pass data between component and they are not nested  : context api 
14) useState vs Using Context api can be changed : useState: inside component , Context api: can’t change but we can provide callback function to child component to change ti with props
15)State vs Redux 
16) Multiple Hooks- user,useState,useEffect,useMemo,useCallback,useSelector 
17)fecthapi -used in UI UseEffect 
```

# 17 Other Interview 17
```
1. Explain var, let and constant with respect to Hoisting
2. What is the output?

obj1 = {a: 10};
const obj2 = obj1;
obj2.a=20;
console.log(obj1);
console.log(obj2);
let obj1;
Uncaught ReferenceError: Cannot access 'obj1' before initialization

3. What is deep copy and shallow copy? 
4. What is the output?
let o1 = {a:1}
let o2 = {...o1}
o1==o2; // false
o1===o2; // false
his is indeed a shallow copy. The spread operator creates a new object o2 with a copy of the a property from o1. However, since a is a primitive value (a number), it is copied by value, not by reference. Therefore, o1 and o2 are two different objects, each with its own copy of the a property. This is why both o1 == o2 and o1 === o2 evaluate to false


5. null == undefined ?
- true, as it allows coercion, type conversion, but in === its false
- Remember falsy values, false 0 -0 0n "" '' `` null undefined NaN 
6. Write a multiply function with currying
let mul = a => b => c => a * b * c;

function mul(a){
    return function(b){
        return function(c){
            return a*b*c;
        }
    }
}
7. Question regarding map, reduce and filter
8. Explain Redux
9. Explain React Hooks.
10. What are Pure Components?
```
# 18  Other Interview 18
```
Q1. Difference between let, var and const.
Q2. // Get output 1,2 without using let.
for(var i=0; i<=2; i++){
    setTimeout(function(){console.log(i)}, 1000);
}
Answer::
function print(i){
    setTimeout(function(){console.log(i)}, 1000)
}
for(var i=0; i<=2; i++){print(i)}

Q3. Types of copy (Shallow vs Deep)
Q4. map vs filter
Q5. Prototype and how it works?
Q6. Arrow function and advantages of arrow function
- Don't have this scope. Closer parent will have access. If no then target to global. No argument objects, use rest operator, Arrow functions are not hoisted. 
Q7. When we use bind VS call apply and bind
Q8. Difference between spread and rest operator.
Q9. //Get second last element from array. 

let arr = ["a", "b", "c", "d", "e", "f"];
output = "e"
console.log(arr[arr.length-2]);

Q10. Output?
console.log(3+"3")
//33
console.log(3-"3")
//0
Q11 NodeJS Middleware? 
Q12 React Element vs Component

const element = <h1>Hello, World!</h1>;     //React Element: immutable & used for representation 
Or without JSX: const element = React.createElement('h1', null, 'Hello, World!');

Q13 What are pure components? 
Q14 What are refs in React?
Q15 forwardRefs in React?
Q16 React Virtual DOM
Q17 Intereceptor :: Intercept request and response before going to backend. Eg, Strictly check API before going to backend. Part of middleware. Depends upon status responses we can do some navigation - eg when hit backend check with the status.ok ==200 
Q18 React fibre? https://flexiple.com/react/react-fiber/
Q19. React lifecycles? 
Q20 In which case you will use HOC? :: 
Q21 Lazy loading ?
Q22 How to manage nested routes in terms of role based routing?
Q23 Ask to interview :: What are roles, project etc.
Show less
```
# 19  Other interview	19
```
1)What is higher order functions,
2)Global execution,
3)Lexical scoping, 
4)Program to find the occurrence of array elements,
5)Program to create sub array of repeating elements of array,
6)Different between class and functional components,
7)What is pure components,
8)How to stop rendering of components,
9)Difference between yarn and npm,
Yarn and npm are both package managers for JavaScript: yarn- is more popular : concurrency 
Package Registry:/Concurrency/Lockfile/CLI and commands/Community and Ecosystem
10)How to unmount component using hooks,
11)Benefits of context api and how to use,
12)How to commit specific commit from working to development branch,
13)What is rebase in github, : two developer working on the same Module 
The git rebase command allows you to easily change a series of commits, modifying the history of your repository. You can reorder, edit, or squash commits together.
```

——————— 
# Interview :

1) Company info 
2) Hiring process 
3) CV hard copy prepare according to 
4) look confident : firm handshake, look into eye of person , smile - fake it 
5) know your CV: write project you have done,: challenges face, details of project , great thing about project 
6) tell me something about yourself Precise & concise -keep it short - don’t	go on on
			tell something which is in CV 
7) be listener : wait the interview to complete question 
		: don’t rush speak at your own speed 
8) paper give to solve puzzle 
		just be organised and don’t be messy , write bullet point , clean clear 
9)  if you don’t know: tell them I don’t know the answer , sorry 
10)  Prepare for real life example you have faced in previous project: recall the real life challenges 
		you should not think, you should be ready with solution 
11) Don’t beat around the bush : answer the question 
		sometime interviewer want you to to the point 
12) ask question job role /company/policy 
		are you hiring for project, bench
		what kind of role will I get 
		designation I get 
		what is the policy to promote employe
		salary increment 
13) Business language : English to express 
14)Never go to interview unprepared: mock interview 
15. For telephonic interview : no disturbance 

Q. What is your weakness ?
Weakness not related to job

Authentic & authenticity - weakness and thought process to overcoming 
So : I was unorganised earlier - due to which I have faced many issue with home and work desk also:
	not finding thing , paying electric bill on time - electricity got cut
	most of issue : 
	overcome by using took and course on udemy : be organised, use sticky notes, have table time of daily 
	morning - yoga& pranyam  for few talk a walk after dinner 
	follow gratitude    
Q. Why should they hire you ?
Connect your Skill experience with what they are looking for 
Storytelling : some story some critical event you handled 
I have qualities expertise to deliver and I am suitable for this position 
Backed was not ready : they ask me to deliver due to escalation I put night and day on creating new screen and delivery on time 
				their was a project where I have to develop a a screen, - I was started with analysis 
				along with the changes from backed need to develop API
				due to more discussion was happening for API creation from backed it got delayed and 
				manager came and asked me there will be escalation 
				so I took the challenge and in 1 day I developed screen & tested throughly once got api 
				and done multiple testing 

Escalation2: when HPS
		    they assigned few task where we require detail from client 
		    but with our multiple attempt and reminder we did not received any reply ; because Clent went on long holiday
		    INSPITE of multiple email this issue got escalated and we have to respond to the higher management from combine called
		     with wipro and client higher management  

Defact : 	

Q. Why do you want to leave your current job? 
Don’t mentions - salary low, boss toxic, timing 
Connect with why we hire you 
I am working in Wipro and  I have learned lot of thing and experience & now I want to get into thing which is more challenging ,more diverse 
Job description you have is very exciting I am looking forward that kind of role, growth in my carrier -
 
Q.What are your salary expectations?
I have done market research and found that this skill: company offering for this skill, location, expertise  20+ 30 9-10  yr 
Based on your budget 20-25
I am open to what is your budget 
Payscle in you company for this company range compansestion offering for this payscale,expertise   
I am looking from

Tellme About youself:
I am Ravi, Born in Jharkhand,
I have done my schooling from Jharkhand,
I have done my egg Dyandnda sagar college of egg
Over the period of 9 years - I have majory work with company like HCL AND wipro
Into majorly on Domain Banking side -, 3 years on healthcare 
I was most onto development , were Individual contributor ,team player and also work on leading the team 
Now I am looking to take my carrier ahed and that why I have applied for this opportunity 
This role will help advance my skill & My 9+ experience will help for challenging project```

### Project: 
```
1)
Banking: card: card generation -lost,broken,renew card 
	   banking and saving - added enhance funcality for login process 	   Loan(Credit Management)- PPI tom Onboarding 
	   Loan Migration:  posting loan credit to Zero
2) Health care : Exchange 
		: policy creation  		: operation : add dependent/ dob change/ new born baby/ welcome letter / smoking /disease 
		: BR rules 
3)  data transfer :
		API consumption: Developed screen for api consumption 
			Click Button - AXIOS: call for backend with Param & callback function 
					      - if success return with AXIOS promise- with data
					     - returned data can be used for view 
					   - if error Dispatch for ACTION 
					  - based on action Update State in REDUCER  
		Create form for registration	: domain/company/data transfer methods/jobs/frequncy  		subscription: allow user to create  subscription/ username/available services /
		form : data lineage : while providing userid,Query detail and other info provides with the how frequently data has been send if record avialbel 

4 Documentation : for Every code changes we made 
				we prepare a Document : Impact analysis / Design Document /Actual component changes 
				UTR: negative testing ,Unit Testing,
				Prepare document: how to install Project setup document -npm,node js, Server UP
5) Security: if asked - added login page to UI
	https://blog.logrocket.com/adding-login-authentication-secure-react-apps/#react-authentication-http-cookies
	1) user login userid/password sent to backend api
	2) if success allow user to view  	3) Backed create readcookie/ for every navigation
			o’clock we hit backed - now backend search for Cookietoken
	4) htmlOnly will create cookie token- saved in UI
		lifecycle -check ComponentDidMount and -readCookie
	5) for logout or timeout it delete the cookie 

```
### pixel perfect responsive website : CSS- Css
```
Animation :
1) CSS method (18)
	OnClick nabber close/open 
	wrapper.classList.Toggle(is_nav_open)	
2) BootStrap 
    BootStrapTable - dynamic data display /MultiGrid
    Enable checkbox 
    enable button 
	onClick expand and collapse: expandRow
3) React Transation group : allow user keep adding new row on every onclick 
    React-transition-group 
4 React animation : animation key From and bounce 
	https://medium.com/hackernoon/5-ways-to-animate-a-reactjs-app-in-2019-56eb9af6e3bf
```


# 1 Self Q & A: HDFC
```
Js 
1. Arr1 = [1,2[3,4],[4,5[7,8]]]
Make it simple Arr1 =[1,2,3,4,5,7,8]

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
//Recursion and let creates new copy

1. Diff between promise and async and await  & how calling happens : async/await uses promise to resolve the issue- is latest version asynchronous call, in promise you can implement callback inside then 
2. HOISTING : JS before  execution it skims code allocate memory for variable=undefined and function = function , 2nd part is execution , laxical scope , global scope 
3. For var i = 0,I<i++
     { Console.log(" ", i) 
Settimeout (console.log("inside”),i))}.    | o/p https://onecompiler.com/javascript/3z6wwawhq
SetTimeout(callback, timer ,[argument to callback])
setTimeout() is an asynchronous function, means timer will not pause for other application to run  ,
4. Call stack  How function get call what happened next : memory/code execution - Global scope, lexical scope 
5. What happens with asyc call stack
6 how to reverse string str=“”hello world”. In normal way 

1. CUSTOM HOOKS: useFetch() :https://www.w3schools.com/react/react_customhooks.asp
2. Useeffect how to achive life cycle management
https://blog.logrocket.com/using-react-useeffect-hook-lifecycle-methods/#using-componentdidmount-functional-components-useeffect
3. Difference between  Pure function & how to achive using useEffect Should component ? 
4. DIFFERENT phase of Lifecycle 
5 which lifecycle always get called
6 difference between class & function component 
7 Redux Architecture 
8  UseMemo 
9 React.memo Memozie (reduce time ) in class component when wraps: https://dev.to/nibble/react-memo-and-react-purecomponent-3k7k
10 pure component 
```

# 2 Self HCL :
```
1 Fibonacci series
2 design pattern  in js

1 What all custom hooks you have done - useFetch()
2 how useEffect will get all lifecycle medthods- componentDidMount(),componentDidUpdate(),componentWillUnmount
3 hooks useCommand and useCallBack ?
4 which is good class or function : it depends  - Redux vs Context api 
5 how to measure the performance : light house, dynamic import, lazy loading , reduce unnecessary folders in css
```

# 3 Self Cybage Software
```
JS: 
1 const arr=[1,2,3];
console.log(arr);
arr.push(4);
console.log(arr);
 O/p : [1,2,3,4] because its reference constant 

2. 
for(var i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
} 
O/p 6,6,6,6,6,6,6
If we need o/p: 0,1,2,3,4,5,   define I as LET

3. Spread operator 
arr =[1,2,3]
arr2 = [3,4,5]

// arr3 = arr+arr2

// arr3 = [...arr,...arr2]

arr3=[1,2,3,...arr,7,9,10,...arr2]
console.log(arr3)

//When pass argument as spread operator 
<FunctionA value= {}>

function getSum(...nums): Object

4.
useEffect(callbackFun,dependecy )
componentDidMount()
useEffect(()=>{ 
console.log("hi")
})
ComponentDidUpdate()
useEffect(()=>{ 
console.log("hi")
},[data])
componentWillUnmount 
useEffect(()=>{ 
return window.removeEventLister()
},[])
5 what is function overloading ? Did java support function overloading ? NO -single function with different name,
6 What is pure component  ? If state changed will it render Child component ? Render function is pure component - no modification during running 
Pure component will only re- render when its props/state changed : avoids unnecessary re-render , performance boost
When using pure components, it's important to keep in mind that they only do a shallow comparison of props and state to determine whether to re-render
7 are you using test cases for unit testing -Jest/engyme- for DOM level
8 Have you used TypeScript ? Redux 
```
# 4 Self TCS:
```
Sdlc vs Agile?
SDLC - software lifecycle development methods-
		 1. requirement gathering - BA & Tech Architect 
		 2. Alignment resource allocation , timeline 
		 3. Software requirement document - System Design - previous and current with changes 
		 Function requirement - Functionality we want to add
			use cases - Description / condition /basic steps involved/ diagram/ Exception Condition /Business valiation rules / post Condition 
		Non-Functional requirement -performance,scalibility,availability,auditing,logging 
		open issue 
		4 Design Prototyping 
			- High level design - Architect- Design/Database use /data flow /Entire system	
			- Low level design - actual Logic 		
			- DB/UI prototype 
		5 Software Development : coding based on SRS document/ design pattern/ Peer Review/Follow code Guidelines
		6 Testing phase QA- function testing/Integration testing /performance Testing /Load testing 	
		8 UAT - Business user check for the 
		9  ci/cd pipelines -devOPS team /change Management team RFC- Backup plan 
		10 test final and get sign off 
		11 Maintenance & update phase 
	Models: 
	(Predictive MODELS)
	waterFall- SDLC with every steps need to complete to move next steps
					- requirements are very clear and well documented : Government Project 
					- small application ,small project : big,complex application do not provide clarity of requirement 
					- No error tolerance : No bugs expected - epayment,flight control system , stock 
					- CONS - tracking project will be default, can’t view Project once completed , no scope adjustment  
	Incremental SDLC : similar to waterfall model- but have small features keep adding new Build in parts : but no feedback can be shown to customer 
					- need to wait for Project to complete to show to Clint
	(ADAPTIVE models)
	Agile : all models - requirement & planning changes can’t be accommodate in last of project 
				- no details planning happens 
				- feature driven development
				- feedback from CUStomer - keep getting interaction with review CUSTOMERS
				- any time customer comes and ask for change the project : no question asked 
				- small feature can be build in sprint 2/4 weeks - deployed and reviewed by Customer -QUALITY product DEVLOPEMENT 
				where to use: 
					- requirement is not fixed / ready to accept BUG & can be fixed in next sprint 
					- customer look product and change based on Market condition 
				Pros:
					- change requirement , faster ,Feedback driven , small team
				cons:
					-cost estimation is difficult 
					- no clarity
					- final product may be not what expected during planning 
AGILES: Teams is important, working software is more important than document, customer feedback,Responding to change 
Key concepts :
	User STORY: JIRA- 1story point 8 Hours -Subject - Description 
	MVP: Minimum Vible of Product must be available to 
	BurnDown Chat: 

SCRUM : what have you completed from last meeting ? What is obstacle ? What is your todays plan
Product Owner : 
	-product Backlog
	-Sprint Planning - which product backlog items 
				- teams identify which items need to be delivered 
				-sprint backlog items 
	-sprint 2 week
Handle by : Scrum master - understand work are done by team and help them how to achieve more efficient ways 
						- removing all obstacle 
						- he is responsible of how to items to be moved
		-Sprint review 
		- product incremental bias 

 	
```
```
Who was driving call agile call?
Agile Methodology 
For performance improvement what are the 10 thing you will Propose to code 
SDLC VS agile 
Process of AGLIE vs process of SDLC
Worked on CMS
How to requirement come ? -email
Have you used git?
Ci/cd pipeline 
Why should I hire you
Have you used tool like sonar
```
### Question 
```
1 Why Reactjs ?
2 Class vs Function :
3 Error Boundary VS try catch finally ? componentDidcatch
4 Code coverage - % percentage of code coverage 
5 How to access the state in redux- scenarios - page->page2-> page3->page4> travel login using guest how to access state: REDUX : useSelector 
6 Object Chaining ? How to check object is null - if null found what will happen - page halt- 
	inline operator / terciary operator 
7 Pure component ? shouldComponent Update, performance enhance 
8 useMemo? chache
9 state vs props? What is state 
10 constructor ?
11  test cases are you writing any test cases-Jest/engyme- for DOM level
12 responsive : mediaQuery 
```

# 5 Self accolitedigital
```
let res = str.replace(/hello/g,'hello Shaket') 

1 var str= "Welcome to Programiz!";
O/p         //"emocleW ot !zimargorP"   

function wordsReverser(str){

  return str.replace(/[a-zA-Z]+/gm, function(item) {    
        return item.split('').reverse().join('');
    });
}

console.log(wordsReverser("This is fun, hopefully."))

Reverse string :     const ReverseString = str => [...str].reverse().join('');      
			    console.log(ReverseString("Geeks for Geeks"))

			 function ReverseString(str) {
				    return str.split('').reverse().join('')
				    }

function ReverseFun(str){
    let str2= str.split(' ')
    let final= ""
    for (let i=0;i<str2.length;i++){
        final += str2[i].split('').reverse().join('') +" "
    }
    return final
}

console.log(ReverseFun(str))


function reverse(s) {
  var o = '';
  for (var i = s.length - 1; i >= 0; i--)
    o += s[i];
  return o;
}
console.log(reverse('Here are those implementation:'));


3 fetch data from url : https://jsonplaceholder.typicode.com/posts
And displays in css cards
https://www.w3schools.com/howto/howto_css_cards.asp
```

# 6 Self Internal :
```
Q. How to pass data : LIST -keys, props,Callback
		if the list updated it will not re-render complete list - Virtual DOM check for change and only update the DOM with new added element 
		
How much time required to convert wireframe to HTML code
What is difference between struts and rest PARAMETER
Internal: 
https://codesandbox.io/s/thirsty-field-ozekod?file=/src/App.tsx
https://codesandbox.io/s/confident-frost-cbcd6o?file=/src/App.tsx
```
# 7 Self CTS: 
```
1) What is useref
2 )what is HOC ? Where have you used it : login ? & what problem does it solve: reusability | props manipulation | design complex solution 

function HOC(WrappedComponent) {
  return function InnerFunction(props) {
    return <div><WrappedComponent {...props} /></div>;
  };
}
3 ) Create 2 component and then take input using textbook from both and make it uppercase  use HOC
https://stackblitz.com/edit/react-ts-sgesnf?file=App.tsx,ComponentB.js,ComponentA.js,index.html

document.querySelector("input").addEventListener("input", function(event) {
  event.target.value = event.target.value.toLocaleUpperCase()
})
style="text-transform:uppercase"

4) axios vs Fetch
Axis- 3rd party, old browser compatibility, also provides advanced features 
Fetch -JS, simple approach
5) How to fetch data from backend ? Multiple fetch api: Promise.all() and map()
onst apiUrls = ['https://api.example.com/users', 'https://api.example.com/products']; 
const fetchData = (url) => { 
	return fetch(url) 
	.then(response => response.json()) 
	.catch(error => { console.error('Error:', error); throw error; }); }; 

Promise.all(apiUrls.map(url => fetchData(url))) 
.then(data => { // Process the data from all API requests console.log(data); }) 
.catch(error => { // Handle any errors that occurred during the API requests console.error('Error:', error); });

By using Promise.all() and map(), we iterate over each URL in the apiUrls array and call fetchData() for each URL. This generates an array of promises. Promise.all() takes an array of promises as input and returns a new promise that resolves when all promises in the array have resolved.

6 )const a = {firstName: "John"}
const b = a;
b.lastName = 'Cena';
b.gender = 'Male';
console.log(a);
console.log(b);
Same O/p
7) null == undefined o/p true | Difference between these two 

‘’: Non empty string its a valid string - stores non empty
Null: non absence of object value - store null
Undefined value that has been not assigned : stores undefined 
ALL 3 takes memory storage & use === to check

9) useStrict in JS: Strict Syntax Checking, Restricts this Binding,Prevents Silent Errors
10) Object  find only nun null keys
const obj1 ={
    key1:'test1',
    key2: 'test2',
    key3:'test3',
    key4:'',
    key5:false
}

function findNonEmptyKeys(obj) {
  const nonEmptyKeys = [];
  for (let key in obj) {
    if (obj[key] !== '' && obj[key] !== null && obj[key] !== undefined) {
      nonEmptyKeys.push(key);
    }
  }
  return nonEmptyKeys;
}

for(const i in obj1)
{   if(obj1[i]!=''){
    console.log(`${i}`,`${obj1[i]}`)
}}

11 how to delete keys of object
delete Employee.firstname; delete object[key1];
12 Array usage : how data pushed- push stack from last 
	if we want in front - splice
	other ways - unshift
13 Fetch data and display in table 
“https://reqres.in/api/users?page=2"
https://codesandbox.io/s/laughing-johnson-cvv16k?file=/src/App.js
14 use of ‘this’ operator
```
# 8 Self CTS2 
```
// console.log("Welcome to Programiz!");

//Mounted
useEffect(() => {SampleFunction()},) 

//update
useEffect(()=> {sampleFunction()},[sate])

//unMounted
useEffect(()=>{
    let mounted =true;
    if(mounted){
    sampleFunction();
    }
    return ()=>{return mounted=false}
},[])


import {useMemo} from 'react'

function SampleFunction(props){
    var result=0;
    for(let i=0;i<props.n;i++)
    {
        retrun result+=props.n
    }
    
}

export default useMemo{SampleFunction}

// Parent component
SampleFunction(1000000)

store
reducer
action 
component 


import {useContext ,creatContext} 'react'


const contextAPI = creatContext()
const user='Ravi'

<contextAPI.provider value={user} >
<APP>

<contextAPI.provider />

ComponentA
ComponentB
ComponentC

ComponentD() {
    const userData = useContext(contextAPI)
    
}

// HOC what is solve: for example- pass calculate area,circumfrance,perimeter of arr[] 
//create function which accept arr & function and in return it calls logic to implement 
//
var arr =[1,2,3]
arr.map((x)=>z*2)

function HOC(WrappedComponent){
    //logic
    return SampleFunction (){
        return <WrappedComponent/>
    }
    
}

var x =HOC(sampleFunction)

closure 

function x(){
    var a=10;
    function y(){
        console.log(a)
    }
    return y
}

var z= x()
z()
data hiding 

deep copy
let a=10
let b={..a}
// splice, sort ,

//shallow same reference 
b=a
Nested Object //
const nestedObject = {
  "name": "John Doe",
  "age": 30,
  "address": {
    "street": "123 Main Street",
    "city": "Anytown",
    "state": "CA",
    "zip": "12345"
  }
};

const deepCopy = JSON.parse(JSON.stringify(nestedObject));

console.log(deepCopy);
Creates new copy


let object ={
    name:'ravi',
    age: '30'
}

let object2 = {() => {console.log()}

object2.Prototype.__proto__ =object
```
# 9 Self Media.net 
```
HTML
1 ) Difference between  <script>, <script async>, <script defer>
2) What is dataSet attributes in HTML
3) <a href="#" data-name="ravi" />
4) What is srcset in Image ? Array of Image 
	<img src="" srcset="" />
5) Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5.
for (let i=1; i<100;i++){
    if(i%15 == 0 ){console.log('fizzbuzz')}
    else{
    if(i%3 == 0){console.log('fizz')}
    else if(i%5 == 0 ){  console.log('buzz')}
    
    else {
    console.log(i) }
}}
6)https://codepen.io/ameyagd/pen/wvPvMgP
 
<h2>Display the number of characters a user has typed into the textarea in real time as they type.</h2>
<label for="text">Enter your text below.</label>
    <textarea id="text"></textarea>
<p>You've written <strong><span id="character-count">0</span> characters</strong>.</p>

On textBox provide data & return count 
CSS 7) what is box Model
7) Event Delegation 
8) Promise Vs Callback
9) create tab into Reactjs
https://codesandbox.io/s/lucid-mountain-zl2qdk?file=/src/ComponentA.js
10) Difference between Local and session storage 
``` 

#  10 Self CTS 3:
```
import "./styles.css";
import {useEffect} from 'react'

export default function App() {

  let time = window.currentDate;

  const updateFunction =(time) => {
    time = window.currentDate
  }
  useEffect(
  setInterval(time=>{updateFunction(time),1000})
  ,)

  useEffect(sideeffect,[])//
  //component Did Mount 
  useEffect(() =>{})

   //component Did Update
   useEffect(() =>{},[state])

   //component will unmOunt 
   useEffect(() =>{
     let mounted =true ;
     fetch('example.com')
     .then(res=> res.json())
     .then(data=> data)
     .catch(err =>  console.log(err))

     return ()=>{mounted=false}
   } ,[])


  console.log(time)
  return (
    <div className="App">
      <h1>Hello CodeSandbox</h1>
      <h2>Start editing to see some magic happen!</h2>
      <h3>{time}</h3>
    </div>
  );
}

// Online Javascript Editor for free
// Write, Edit and Run your Javascript code using JS Online Compiler

console.log("Welcome to Programiz!");

// Prime Number 0-10

// function PrimeNum(n){
//     for(let i=1; i<n; i++){
//         // if(i%2 != 0 || i%3 != 0 || i%5 != 0 || i%7 != 0){
//           if(i%(i/2) == 0){
//             console.log(i)
//         }
//     }
//     console.log(n)
// }

// PrimeNum(10)

// const str ='Welcome';

// function reverseFun(str){
// let reverse=[]
// for(let i=str.length; i>=0 ; i--){
//     console.log(str[i])
//     reverse.push(str[i])
// }

// console.log(reverse.join(''))
// }

```
# 11 self 
```
const fruits = ["apple", "orange", "grapes", "pineapple"];
using destructuring create vaiables a and b.  a should contain apple b should contain rest of the elements from fruits

interceptor

CRUD operations --------------- Create two route and show menu 1. Add User(Show user form, validate and send it to API) 2. List User(Pull previously added users and list them in table format) use https://crudcrud.com/ for REST API calls
//const fruits = ["apple", "orange", "grapes", "pineapple"];
 
//using destructuring create vaiables a and b. 
//a should contain apple
//b should contain rest of the elements from fruits
//const {a,...b} = fruits

const vagitable = ['potato','tomato']

const thirdArr = [...fruits,...vagitable]

thirdArr=[["apple", "orange", "grapes", "pineapple"],['potato','tomato'] ]

//fruits.map(item => console.log(item))

function HOC(radius,logic){

	return  function (logic){
  	return logic(radius)
  }

}

function circumfarance(r){
		return 2* Math.PI * r
}

function Area(r){ 
return Math.PI*r*r
}

HOC(2,Area)
HOC(2,circumfarance)

useState()
useEffect()
useMemo()
useCallback()

child->parent : callback
parent->child : props

redux

store -state
```
```
1. // Form validation
// -----------------
// name - text (minimum 4 chars)
// qualification - dropdown
// gender - radio
// skills - check box(must select more than one)
// Note: All are mandatory fields

2) CRUD operations --------------- Create two route and show menu 
1. Add User(Show user form, validate and send it to API)
 2. List User(Pull previously added users and list them in table format) use https://crudcrud.com/ for REST API calls
```

# 12 self Telstra :
```
Q. What is wrong with code 
How to stop re rendering Parent/child 


import { createContext, useContext, useEffect, useState } from 'react';
 
export default function App() {
    console.log("Parent");
  let [color, setColor] = useState('red');
  let  value = ''
  const handleClick =(e) => 
  {
    e.preventDefault();
  //  value = e.target.value
  //  console.log(value)
    
  }
  // useEffect( () => {setColor(value)},[]

  // )
  

  return (
    <div>
      <input value={color} onChange={(e) => setColor(e.target.value))} />
   <input value={color} onChange={(e) => setColor(handleClick(e))} />
      
      <p style={{ color }}>Hello, world!</p>
      <ChildComponent />
    </div>
  );
}
 
function ChildComponent() {
    console.log("Child");
  return <p>I am child component</p>;
}



Q.2 var value = "Global";
 
const obj = {
    value : "Inner",
    normal : function(){
        console.log(this.value);
    },
    arrow: () => {
        console.log(this.value);
    }
}
 
obj.normal(); - inner 
obj.arrow(); - undefined
he this keyword inside the arrow function does not refer to the obj object. Instead, it refers to the global object. Therefore, the output of obj.arrow() is undefined.


Q.3 function function1() {
    var a = 2;   //LET A= 2  // VAR 
    {
        var a = 4; //LET
        console.log(a);
    }
    console.log(a);
}
Q. Memory leakage
Memory leakage in JavaScript refers to a situation where the memory allocated for objects or data is not properly released or freed up when it is no longer needed. This can lead to an accumulation of memory usage over time, resulting in decreased performance and potential crashes.
Create a closure and after that use 
closure = null;

Q. Text centre
Q. Flex box 
Q event loop
Q which is more secure ?- localstrorage 
Q why class component Name start with CAPITAL letter 
The reason behind starting component class names with a capital letter is due to the way React treats JSX. When JSX is transpiled, it converts elements with lowercase names into regular HTML tags. Elements with uppercase or capital letters are treated as custom components.
By convention, starting component class names with a capital letter helps differentiate them from regular HTML elements. It allows React to recognize and treat them as components, triggering the appropriate rendering and lifecycle methods

Q. Does functional component has same YES
Q.what is difference between foreach and map in javascript
Foreach: -iteration, such as updating the DOM, logging values, or modifying the existing array
Map: iteration with return new array with result, It is used when you want to transform each element of an array and create a new array with the transformed values.
Example: var arr =[1,2,3,4]  ; arr.forEach(item=> item*2) 
```
# 13 self Nagarro
```
1)Section and div : semantic
2)eventPropa gation vs immediate propagation  
 immediate propagation  : propagating to parent elements but also prevents any other event handlers on the same element from executing. It effectively stops both the bubbling phase and the execution of any remaining event handlers on the current element.
3)Em vs REM ?  REM: RootNode- 16px, em- parent 
4)psudo element ? 
5)BrowserObjectModel ? BOM
6)MapObject vs Object ?
```
```
1. Object:
    * Object is a built-in data type in JavaScript used to represent a collection of key-value pairs.
    * Objects are unordered and use string keys to access values.
    * The keys in an object must be unique.
    * Objects are commonly used for creating complex data structures and defining the properties and methods of an object.
2. Example: javascript  Copy codeconst person = { name: 'John', age: 30, address: { street: '123 Main St', city: 'New York' } };   
3. Map:
    * Map is a built-in data structure in JavaScript introduced in ECMAScript 2015 (ES6).
    * Map is an ordered collection of key-value pairs where any value can be used as the key.
    * Keys in a Map can be of any data type (primitive or object) and maintain their insertion order.
    * Unlike objects, Map provides built-in methods for operations like adding, removing, and iterating over entries.
4. Example: javascript  Copy codeconst myMap = new Map(); myMap.set('name', 'John'); myMap.set(1, 'one'); myMap.set({ key: 'value' }, 'object'); console.log(myMap.get('name')); // Output: 'John' console.log(myMap.get(1)); // Output: 'one' console.log(myMap.get({ key: 'value' })); // Output: 'object'
```
```
7)For in vs For of when to use in ?
Feature	for...in -keys	for...of -value 
Iterates over	Enumerable properties	Values
Loop variable type	String (property name)	Any (value)
Use cases	Accessing property names, modifying object properties	Iterating over arrays, strings, sets, maps, and other iterable objects
const obj = { a: 1, b: 2, c: 3 };

for (const property in obj) {.  //modify properties 
  obj[property] *= 2; // Multiply each property value by 2
}

8)Event curry what is the usage why we use it -readable/reusable/prevent errors 
9)Pure component ?
10)Virtual DOM Reconselleation ? If Reconselleation process is already there then why we need Pure component
Pure component do the shallow check, but let say if any changes in deep copy of pure component there - then 
Reconselleation alr eady will detects the changes then what is need of Pure component 
11)var x =21
function xyz(){
    console.log(x)
    var x=20
}
xyz() - undefined 
12)Why we use synthetic event in React ? What is synthetic event? We already have event handling why react use it 
Since native event does it already: is behaves same in different browsers 
13 Session broker: works on without internet  vs web broker: Multi thread works in background 
```
# 13 self Mphasis:
```
Qprepare a snippet that covers below cases and returns 1 output green -> Keep Moving yellow -> get ready to Move, need to wait for few secs red -> Not Allowed to Move, stay behind the cross line
input will be :: decisionMaker('red')
function TrafficLight(input){
    
    if(input === 'red') {
        console.log('Not Allowed to Move, stay behind the cross line')
    }
    else if(input ==='green') {
        console.log('Keep Moving')
    }
    else if(input ==='yellow' ){
        console.log('get ready to Move, need to wait for few secs')
        setTimeout(()=>{console.log('keep moving')},2000)
    }
}
TrafficLight('yellow')

Q const str= 'get ready to Move'
//'evoM ot ydaer teg'
console.log(str.split('').reverse('').join(''))
for (let i =str.length-1; i<0;i++  )

https://randomuser.me/api/?exc=login
let a =1;
leb b ={ ..a}

let b ={ ..a}
export default function App() {
  const URL ='https://randomuser.me/api/?exc=login'
  const [users,setUsers]  = useState([])

  setInterval(useEffect(
    ()=>{
      fetch(URL)
      .then(res=>res.json())
      .then(data =>setUsers(data.results) )
      .catch(err=> console.log(err))
    }
    ,[]),2000)
  
    console.log("users: ",users)
  return (
    <div className="App">
      <h1>Hello CodeSandbox</h1>
      <h2>Start editing to see some magic happen!</h2>
      { users?.map((user) => (
      <div >
          <p>{user.gender}</p>
          <p>{user.email}</p>
          <p>{user.phone}</p>

        </div>
      ))}
    </div>
  );
}
Q Difference between block elements and inline elements
Q Memory leakage  ? how to check is your code is Memory leakage  proof ? in javascript
```
* Use the Chrome DevTools Memory tab. This tab will show you a live view of your application's memory usage. If you see the memory usage increasing over time, it is likely that you have a memory leak.
* Use the debugger statement. This statement will pause your code execution, so you can inspect the memory usage at a specific point in your code.
* Use a memory profiler. There are a number of memory profilers available, such as the V8 Heap Profiler and the Chrome Memory Profiler. These tools can help you to identify memory leaks in your code.
Here are some of the most common causes of memory leaks in JavaScript:
* Objects that are not garbage collected. When an object is no longer needed, it should be garbage collected. However, if an object is not garbage collected, it will continue to take up memory.
* Objects that are created in loops. If you create objects in a loop, and the objects are not garbage collected, the memory usage will increase over time.
* Objects that are stored in global variables. Objects that are stored in global variables are not garbage collected until the page is unloaded. This can lead to memory leaks if the objects are not properly cleaned up.
Here are some tips to help you avoid memory leaks in JavaScript:
* Use the gc() function to manually garbage collect objects. This can help to prevent memory leaks from occurring.
* Use the weakref() function to create weak references to objects. Weak references will be garbage collected when the object is no longer needed.
* Avoid creating objects in loops. If you must create objects in a loop, make sure to garbage collect the objects that are no longer needed.
* Avoid storing objects in global variables. If you must store objects in global variables, make sure to clean them up when they are no longer needed.```
  
# 14 self Mphasis: 2
```
Q delcaritve and imperative : JS is both 
 
  Declarative (Functional ) React/Redux: what you want without how to code  -functional/logical 
  Imperative programming, on the other hand, focuses on explicitly specifying each step and detail of the program's execution-  imperative(Procedural, OOPS)
Q Css library : bootstrap,tailwind 
Q Redux store variable in browser where ? 
* The Redux store is not stored directly in any of these browser storage mechanisms (Local Storage, Session Storage, or Cookies).
* Redux store is an in-memory data structure managed by the Redux library in JavaScript.
* By default, the Redux store does not persist across page reloads or browser sessions.
Q Accessibility 
Accessibility in CSS refers to designing and developing CSS styles in a way that ensures web content is accessible to all users, including those with disabilities. CSS can play a significant role in improving the accessibility of a website by providing visual cues, enhancing readability, and enabling assistive technologies to interpret and present content effectively.
Q what are new version of react and new thing implemented
```

# 15 self UST Product Engineering
```
a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}]
// output [{c: 0}, {a: 1}, {b: 2}]
Sort based on values and remove duplicates on key

const a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}];

const sortedAndDistinct = [...new Map(a.map(item => [JSON.stringify(item), item]))
  .values()] .sort((obj1, obj2) => Object.values(obj1)[0] - Object.values(obj2)[0]);

console.log(sortedAndDistinct);
```
# 16 self HCL2
```
Q. How to check given number is  integer without using inbuilt typeOF- Math.floor
 ```

# 17 self  Virtusa
```
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
// bar
Bar
Undefined 
Bar

Zenser Tech
1 Class vs interface
Feature	Class	Interface
Purpose	Blueprint for objects	Shape of an object
Instantiation	Can be instantiated	Cannot be instantiated
Inheritance	Can inherit from other classes	Cannot inherit from other classes
Implementation	Provides implementation for properties and methods	Does not provide implementation for properties and methods
Use cases	Creating objects with state and behavior, inheriting from existing classes, providing a concrete implementation of a set of properties and methods	Specifying the shape of an object, defining a common set of properties and methods that will be shared by multiple classes, using type safety to ensure that objects meet certain criteria
2 Type: generic- reusability 
function getArray<T>(items: T[]): T[] {
  const result = [];
  for (const item of items) {
    result.push(item);
  }
  return result;
}

const numbers = getArray<number>([1, 2, 3, 4, 5]);
const strings = getArray<string>(['hello', 'world', 'foo', 'bar']);
3 MonoRepo Architecture
4 Flatten array 
5 RTQuery
6 React vs ReactDom
Feature	React	ReactDOM
Purpose	Creating UI components	Rendering UI components to the DOM
Library or package	Library	Package
Dependency	Not required	Required
Use cases	Creating interactive web UIs	Rendering React components to the DOM
```
# 17 self  EPAM: *****
```
1) Define Apply with real life example
// let name = 'ravi'

// String.prototype.myFun = (name,city)=>{
//     console.log("name "+name  + "city"  +city  )
    
// }
// name.apply(myFun,['Bangalore'])
2)html vs htmls - ? COROS ?
3)Typescript,material ui,CSS,Responsive UI
4) Semantic and non semantic - difference 
5) Dependency vs devDependency
devDependencies: Dependencies listed under the devDependencies field are the packages that are only required for development purposes. These packages are not necessary for the production build of the application. They typically include tools, libraries, or testing frameworks used during development, such as transpilers, linters, testing frameworks, etc.
npm install package-name --save-dev
6)web pack
7)performance 
9) React vs ReactDom
10)SEO,SSR CSR, drawbacks with SEO -CSR 
```
# 17 self Synechron
```
1.Display keys of object not using for loop, find null keys(for (let I in Object))
let user ={
    name : "Balaji",
    age : 23,
    greet : () => "Hello",
};  
let keys = Object.keys(user);
keys; //["name", "age", "greet"]
2 object.assign- shallow/deep- shallow copy
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };
const returnedTarget = Object.assign(target, source);

3)Write program useCallback,Contextapi 
4)Difference between Grid vs flexbox
The best choice for you will depend on your specific needs. If you need a two-dimensional layout, then CSS Grid is the better choice. If you need a one-dimensional layout and you're a beginner, then Flexbox is a good option.
```

# 17 self  Altimatrix:
```
constChild=(props)=>{
letcount=1;
// const [callback] = ;
constchnageonClick=()=>{
props.callback(count);
} ;
 
return(
<>
<inputtype="submit"onchange={ chnageonClick} />
</>
);
} ;
 
exportdefaultChild;

var input= 'ravi'
//output= true
//ramya
//output =2

// a,e,i,o,u 
//how many vowels 

function CheckVoweles(input){
    
    let vowels= ['a','e','i','o','u'] 
    let count =0
    
    for(let i =0;i<input.length; i++){
        if(vowels.includes(input.charAt(i))){
            count ++
            
        }
    }
  return count  
}

console.log(CheckVoweles(input))

Infosys
1 Sort array
2 Login page how the bearer token will our page identifies, how it will know same user logged 
3 error boundary in functional component 
4 lifecycle managemnt  in Functional Component 
```

# 18 self Connectwise
```
1) pure function 
2)web pack- what happens once user hit the your app ? -  ip/port - bundle.js - dependency tree, output ,plugin 
3)deployment -
4)Wiggle short - /**
* Wiggle Sort
*
* Given an unsorted array nums, reorder it in-place such that nums[0] <= nums[1] >= nums[2] <= nums[3]....
*
* For example, given nums = [3, 5, 2, 1, 6, 4], one possible answer is [1, 6, 2, 5, 3, 4].
*/
/**
function wiggleSort(nums) {
  // Loop through the array
  for (let i = 0; i < nums.length - 1; i++) {
    // Check if the current element is greater than the next element
    if ((i % 2 === 0 && nums[i] > nums[i + 1]) ||
      (i % 2 === 1 && nums[i] < nums[i + 1])) {
      // Swap the elements
      [nums[i], nums[i + 1]] = [nums[i + 1], nums[i]];
    }
  }
}

const nums = [3, 5, 2, 1, 6, 4];
wiggleSort(nums);
console.log(nums); // Output: [1, 6, 2, 5, 3, 4]

5) function x() {
//     let a =10;   //let is already having lexical scope  use var 
//     return function y() {
//         console.log(a)
//     }
// }

// const z = x()
// z()
// z()
// Since var has function scope, the a variable will be shared between all instances of the y function. This means that each call to z will increment the same a variable.
6)const promise = new Promise((resolve, reject) => {
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
O/p 
1
2
4
timerStart
timerEnd
success
```

# 18 self  Admiral india
```
Closure 
Fetch vs axis  - how you call for POST method in Fetch 
Felxbox vs Grid
Absolute vs relative
Semantic vs no semantic - who do you mean by meaningful 
Even delegation , event propagation , immediate propagation etc 
How you write test cases in jest ? Why we use cucumber 
How you implement infinite scrolling how you can achieve ? Without loosing data ?
Call bind apply 
Specificity ?
How you stop form to send data - once submitted it automatically naviaged to next page ? Validation in css 
SQL : find all those employee names are duplicate 
	select Name from Employee group by name  having count(*) >1 
What are different sector in css ?
```



# Frequent Question & must

```
Splice, Reverse,split,replace,Object 
For Loop, In Loops
New array : Splice,map,sort,
Insert at specific location =splice
Insert at front: shift/unshift
Insert in stack: push, pop
Observe : more focus on  live coding & more writing examples 
```
```
1)Closures : data hiding 
function x(){
    var a =10
    function y()
    {
        console.log(a)
    }
    return y     //Function Name
}

var z =x()
console.log(z) //return function y
z() // runs y

2)HOC: taking function, modify it and then render:
Eg- calculate(logic,radiusArray) return calculated result

function HOC(WrappedComponent) {
  return function InnerFunction(props) {
    return <div><WrappedComponent {...props} /></div>;
  };
}

3)Difference between useMemo VS react.Memo vs Callback
useMemo: stores calculation -reCallback: remembers Functions
React.memo:  Shallow check, previous render data- Classbased

4 Thunk & middleware what is uses 
5)ContextAPi with implementation 
6)unMounted
useEffect(()=>{
    let mounted =true;
    if(mounted){
    sampleFunction();
    }
    return ()=>{return mounted=false}
},[])
7)Fetch data and display in table
8)Object traverse, occurrence & or Find maxOccurance 
9)Reverse String : str.split('').reverse().join('') 
10)Props and state Difference 
11) Testing-Jest,engymes 
12)Virtual DOM VS real Dom - how it is fast
13) Performance optimisation: css to internal css , react.memo, useMemo,HOC, pure component ,useCallback
14. Deep copy
a)spread operator : update object
	const student = { name: “ravi”,place:”Sahibganj”,age:33}
	let StudentOne = {…student,name=“Kumar”}
b)const deepCopy = JSON.parse(JSON.stringify(nestedObject));

15)Difference between Normal Function 
https://betterprogramming.pub/difference-between-regular-functions-and-arrow-functions-f65639aba256
Arrow function : no bind to argument,This points to parent Non-Arrow Function ,arrow function can’t be used as constructor - new parameter 
16) null == undefined o/p true | Difference between these two 

‘’: Non empty string its a valid string - stores non empty
Null: non absence of object value - store null
Undefined value that has been not assigned : stores undefined 
ALL 3 takes memory storage & use === to check
17)Difference between let, var and const- var with setTimeout - how to resolve- using let 
	if we don’t use let then- call setimout as function 
18)Synthetic Event: SyntheticEvent is a cross-browser wrapper around the browser's native event. It's API is same as the browser's native event, including stopPropagation() and preventDefault(), except the events work identically across all browsers
```

CSS:
```

0)Sematic tag: meaning full tag -section ,input, etc
search engine optimization (SEO), and maintainability of the HTML code. 
Semantic elements provide more context and clarity to both humans and machines, making it easier to understand and work with the content.
1)Position Relative & absolute Position 
position	relative	absolute
Overflow	Overflow of the element is calculated relative to its original position/Normal Position/DOM 	Overflow of the element is calculated relative to its new position/relative to parent 
Visibility	Visibility of the element is not affected	Visibility of the element is affected

2)BOX model: padding, margin, Border,content 
3)responsive: define class, in css - define media query for that class
Eg- @media (min-width: 768px) {
  .desktop-image {
    display: block;
  }
}
4)BLOCK: complete line - h1-h6 vs inline : takes how much required SPAN,img,label,BR 
https://www.geeksforgeeks.org/difference-between-block-elements-and-inline-elements/

```


# Extra:
```
1) Want to collapse/expand grid  -But not the inner grid section update : onClick = {e => {e.stopPropagation() }}
2) can we define constructor/this in function - no because stateless
3) Multiple link/url to get data at a time : Promise.all(URLArray.map(url=> fetch(url)))
On login call multiple api - how to handle 
const login = async (username, password) => {
  try {
    const api1Response = axios.post('/api/login', { username, password });
    const api2Response = axios.get('/api/user');
    const [loginResponse, userResponse] = await Promise.all([api1Response, api2Response]);
    
    // Process the responses
    const loginData = loginResponse.data;
    const userData = userResponse.data;
    
    // Return the combined data or perform other actions
    return { loginData, userData };
  }
(loginResponse.status and userResponse.status) to ensure they are both 200

OR ALSO can be done using chaining of loginResponse success then go for userResponse

const login = async (username, password) => {
  try {
    const loginResponse = await axios.post('/api/login', { username, password });

    // Check if login response is successful
    if (loginResponse.status === 200) {
      const userId = loginResponse.data.userId;

      // Chain the user API call
      const userResponse = await axios.get(`/api/user/${userId}`);

      // Check if user response is successful
      if (userResponse.status === 200) {
        const userData = userResponse.data;

        // Perform other actions or return the data
        return { loginData: loginResponse.data, userData };


4) difference between render & Component in Route 
In Route if Component passed- it will process all the lifecycle Methods for every hit on Click , back click
If Render props: means its function and will run as a function no lifecycle methods  
https://stackoverflow.com/questions/48150567/react-router-difference-between-component-and-render
5) performance - calling backed every time is not advisable 
- Sort at front end can be reduced 
- Internal css is increase performance sometimes
- Lazy loding 

6)how can call asynchronus call in inside redux other than react saga,thunk
axios 
Promise 
obserable 

7)when a function gone to infinite loop
Update inside UseEffect - how to prevent : do not update 
Incorrect dependencies useEffect
Unconditional state updates- without any check if updates can lead to infinite loop
Recursive component rendering:
```



# Redux:
1 Multiple reducer component how your component will identifier which reducer called  
combineReducers we can use key Value pairs 
2 useSelector to get data anytime 
3 where exactly the store data getting stored : browser/localstorege/session storage 


￼
￼

React js: Basic question MCQ
Predicting output
Lifecycle mangament 
Redux basic- dispatch and action 
Event delegation
2 technical - 15-20min - 15 Question - conceptual knowledge 
https://youtu.be/eQmvZLd-Lk0
https://www.youtube.com/watch?v=kIt1rtrmn3U

￼
￼
Code splitting VS Lazy loading VS Dynamic import 
Code splitting - dividing large bundle into small BUNDLE webpack and can be loaded during runtime 
A large e-commerce application : for every page has bundle and used when required -Home page, cart page, product page, etc 

const moduleA = 'Hello';
 export { moduleA }; 
App.js 
import React, { Component } from 'react'; 
class App extends Component { 
	handleClick = () => { import('./moduleA')               //PROMISE
					.then(({ moduleA }) => { // Use moduleA }) 
					.catch(err => { // Handle failure }); };
 render() { 
return (<button onClick={this.handleClick}>Load</button.   //load moduleA during click
); } } 
export default App;

Where the code splits actually: INSIDE CONFIG.JS.  
optimization: {
  splitChunks: {
    chunks: "all",
  },
},

Lazy loading : do not load unnecessary item during main application load 
A social media application could use lazy loading to load images and videos

const OtherComponent = React.lazy(() => import('./OtherComponen t')); 

function MyComponent() { 
	return ( <OtherComponent />);
	 }

Q. React router and why do we use it 
Routing
Single Page Applications
Component-Based Development
History Management:

Q. useErrorBoundry 
import useErrorBoundary from "use-error-boundary"

const MyComponent = () => {
  const { ErrorBoundary, didCatch, error } = useErrorBoundary()

  return (
    <>
      {didCatch ? (
        <p>An error has been caught: {error.message}</p>
      ) : (
        <ErrorBoundary>
          <JustRenderMe />
        </ErrorBoundary>
      )}
    </>
Q. What is generator function and why do we use it 
What will happen if no next is called ? on the iterator object, the generator function will not execute

A generator function is a special type of function in JavaScript that can be paused and resumed during its execution. It allows you to generate a sequence of values on-deman

function* fibonacci() {
  let a = 0;
  let b = 1;

  while (true) {
    yield a;
    [a, b] = [b, a + b];
  }
}

const fibSequence = fibonacci();

console.log(fibSequence.next().value); // 0
console.log(fibSequence.next().value); // 1
console.log(fibSequence.next().value); // 1
console.log(fibSequence.next().value); // 2
// ...

Q.in javascript how can you completely delete all the localstorage in one go?
localStorage.clear();

Q.Object creation different techniques ?
Object Assignation Method 


1 Object Literal: const obj = { key1: value1, key2: value2 };
2 Constructor Function:

function Person(name, age) {
  this.name = name;
  this.age = age;}

const person = new Person('John', 25);
3 Object.create
const protoObj = { key1: value1, key2: value2 };
const obj = Object.create(protoObj);
3.1)
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };
const returnedTarget = Object.assign(target, source);
4) Class 
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
const person = new Person('John', 25);

5) Object Constructor 

const obj = new Object();
obj.key1 = value1;
obj.key2 = value2;
6) Factory Methods: 
function createPerson(name, age) {
  return {
    name,
    age,
  };
}
const person = createPerson('John', 25);

Q.why do we prefer Object.create over others ?
1. Explicit Prototype Setting: Object.create() allows you to explicitly set the prototype of an object during its creation. This can be useful when you want to create an object with a specific prototype, rather than relying on the default prototype set by other object creation methods.
2. Object Composition: Object.create() enables prototypal inheritance and object composition. You can create new objects that inherit properties and methods from a shared prototype object, allowing for code reuse and creating object hierarchies.
3. Prototypal Inheritance: Object.create() provides a more direct and flexible way to establish prototypal inheritance. You can create an object that directly inherits from another object without the need for constructor functions or the new keyword.
4. Cloning Objects: Object.create() can be used to create a shallow copy of an existing object, where the new object inherits the properties of the original object. This can be useful for object cloning or creating variations of existing objects.
Creating a new object that inherits from an existing object



Q what are new features intoroduced into Bootstrap5
1. Smaller Bundle Size: Bootstrap 5 is designed to have a smaller bundle size compared to Bootstrap 4, making it faster to load and more efficient.
2. Switch to Vanilla JavaScript: Bootstrap 5 has reduced its dependency on jQuery and moved towards using vanilla JavaScript, resulting in a more lightweight and modern codebase.
3. Updated Utility Classes: The utility classes in Bootstrap 5 have been enhanced and expanded to provide more flexibility and control over the layout and styling of elements.
4. Improved Grid System: 
5. New CSS Custom Properties: CSS customisation 
6. Enhanced Form Controls: Bootstrap 5 includes improved form controls with updated styles, validation states, and custom form control styles.
7. Responsive Font Sizes: Bootstrap 5 introduces a new responsive font sizing feature, allowing developers to easily scale font sizes based on the viewport size.
8. New Components: Bootstrap 5 includes new and updated components, such as the Offcanvas component for creating off-canvas navigation, the Floating Labels component for form inputs, and the Accordion component for collapsible content.

Q.CSS  What is default positioning - static/relative/absoulte-parent: STATIC 
Q. in Css :before and :after psudo & why we call them psudo element
pseudo classes vs . What are pseudo classes and pseudo elements in CSS?
 ::before and ::after pseudo-elements allow you to insert content before and after an element's content, respectively
add decorative or additional elements to an HTML element without modifying its structure.


/* CSS */
.element::before {
  content: "Before";
  /* Other styles */
}

.element::after {
  content: "After";
  /* Other styles */
}

pseudo-element: The :before and :after are called pseudo-elements because they represent virtual elements that are inserted before and after the content of an element, respectively. They don't exist as actual elements in the HTML structure but can be styled and manipulated as if they were.
pseudo-classes like :hover, :focus, :active, etc., represent specific states of an element, such as when it is being hovered over, focused, or activated. Pseudo-classes allow you to apply styles to elements based on their current state or interaction with the user.






* Q1. Difference between display: inline, display: block and display: inline-block in CSS?
* Q2. What are pseudo classes and pseudo elements in CSS? growingwiththeweb.com/2012/08/pseudo-classes-vs-pseudo-elements.html
Class: state of element change HOVER,    Element: virtual element- Change colour of First line 
* Q3. What are the ways to create objects in JS?
* Q4. What are some of the string methods in JS? length,substr ,charAt, lastIndexOf,indexOf, replace,toUppercase,concat https://www.w3schools.com/js/js_string_methods.asp
* Q5. What are the new input types in HTML5? https://www.geeksforgeeks.org/explain-the-form-new-input-types-in-html5/
Color/data/time/date-time/datetime-local/
email/number/range/

* Q6. What are forwardRefs in React ? & ref: access the DOM element or component instance of a React component. This can be useful in cases where you need to do something with the DOM element, such as focus it, scroll it, or add an event listener to it.: Parent—> child
* This is useful in cases where you need to access the DOM element or component instance of the child component from the parent component.
* Q7. What is a z-index in CSS? The z-index property specifies the stack order of an element.- work with positioned element 
* Q8. What is function currying in JS?
* Q9. What is the difference between element and components in React?
* Q10. What are the type of functions in JS? : function Statement/Declaration, Anonymous,Named Function, function Expression, arrow function 
* Q11. What is a dynamic import in React? - 
* Q12. What is bubbling and capturing in JS?
* Q13. What is position: absolute vs position: relative in CSS?
* Q14. What is canvas and SVGs?
* Use SVG for:
    * Logos
    * Icons
    * Charts
    * Maps
    * Images that need to be scalable and accessible
* Use Canvas for:
    * Games
    * Animations
    * Interactive graphics
    * Images that need to be resolution-independent and dynamic
*  
* Accessibility: SVG graphics are more accessible than Canvas graphics, as they can be interpreted by screen readers.
* Performance: SVG graphics are typically faster to load than Canvas graphics.
* Support: SVG is supported by all major browsers, while Canvas is not supported by older browsers.








￼


Question CSS : 
1 html ? is layout on web pages 
2 html layout? header, footer, head, title,
3 tags in html? determine what element containg h1- highest, h6-last, how the element should be seen to the user 
Css 
4 strong type VS bold type ? strong - how important the content is & bold- for highlighting 
5 position attribute used ? absolute, fixed: if any element is position fixed it will be fixed to that element   
				position	absolute: parent, child element - if put position absolute on child then it will relative on parent 
							it will be relative to the container/body/parent 
				position relative : relative to the  normal flow of document / moving based on where it was kept DOM
				
6 flex box? it can been used to make our page responsive 
7 display none ? completely removes the element 
	visibility hidden?  : it keeps the element position and only  hide 
8 1 !DOCTYPE: information to browser what document type is expected 
		<!DOCTYPE html>
Older version: <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"> what version of HTML 
9 CSS3 vs CSS ?  CSS3 makes the Web Pages more attractive.
					css can be splitted into Modules ,faster ,latest version
10  what are css library? Bootstrap tailwind ,MUI 
11 how to add css and javascript globally in react js
	public folder : styles.css in the css directory and app.js in the js directory.
 In the public directory, open the index.html file.- inside HEAD tag
	<link rel="stylesheet" type="text/css" href="%PUBLIC_URL%/css/styles.css">
  body tag 
        <script type="text/javascript" src="%PUBLIC_URL%/js/app.js"></script>

OR: CSS-> import * ./src/styles/global.css
	js-> import scriptTag rom react-script-tag
react-script-tag is a React component that allows you to add external script tags to your React application
12 Json data try print based on age in HTML 

const element =[{name: 'ravi',age:30},{name: 'avi',age:20},{name: 'vi',age:25},{name: 'iravi',age:35},]

const container =document.getElementById('myelement')
const res = element.filter(item => item.age<26)
console.log(res)
res.map(item => {
	const p =document.createElement('p')
	p.textContent = `Name : ${item.name} ===> Age: ${item.age} `
	container.appendChild(p)	
})

13 what is onBlur function :  if you have input textbox & typing something - then between you clicked somewhere it got called 
14 )How to write Console.log()using Document 
<script>
document.addEventListener("DOMContentLoaded", function() {
  console.log("Hello, world!");
});
</script>

15)Difference between  <script>, <script async>, <script defer>
script: HTML parsing-> script fetch-> script excited->HTML parsing continued 
async: HTML parsing-> script fetch Parallely/async -> script excited -> HTML parsing continued 
defer: HTML parsing-> script fetch  Parallely/async ->HTML parsing -> script excited
16) What is dataSet attributes in HTML:  start with the data- prefix. They are used to store data that is not part of the standard HTML semantics.

<div data-name="John Doe"></div>

var element = document.querySelector("div");
var name = element.dataset.name;

17) What is srcset in Image ? Array of Image 

<h1>The picture element</h1>
<p>Resize the browser window to load different images.</p>

<picture>
  <source media="(min-width:650px)" srcset="img_pink_flowers.jpg">
  <source media="(min-width:465px)" srcset="img_white_flower.jpg">
  <img src="img_orange_flowers.jpg" alt="Flowers" style="width:auto;">
</picture>
18)Section and div : semantic vs non-sematic
19)Em vs REM ?  REM: RootNode- 16px, em- parent 
20)psudo element vs pseudo class
 in Css :before and :after psudo & why we call them psudo element
21)BrowserObjectModel ? BOM
The Browser Object Model (BOM) is a set of objects that allow JavaScript to interact with the browser. It is a browser-specific convention, so the objects and methods available may vary depending on the browser.
The BOM includes objects for the window, the document, the history, the navigator, and the screen. These objects can be used to access information about the browser, the current document, and the user's environment.
common objects in the BOM: Window/document/history/navigator/screen

22)Difference between block elements: <DIV>/<P>/<UL> and inline elements- <SPAN>/<IMG>/<a>
23)CSS  What is default positioning - static/relative/absoulte-parent: STATIC 
24)what are new features intoroduced into Bootstrap5
25)dangerouslyTypeHTml  && __innerhtml 
Inner HTML: Setting the value of innerHTML removes all of the element's descendants and replaces them with nodes constructed by parsing the HTML given in the string htmlString.
dangerouslyTypeHTml is a JavaScript function that allows you to inject HTML into a web page without
26) different type of storage in web browser ? Which one to use when 
27) 
Both  sets the HTML content of the element. It does not do any escaping of the HTML, so it is possible for malicious code to be injected into the web page.
The dangerouslyTypeHTML:   you to set the HTML content of the element without having to escape it yourself. However, this also means that you are responsible for making sure that the HTML is safe. If you do not escape the HTML correctly, malicious code could be injected into the web page.
26)Accessibility :  designing and developing CSS styles in a way that ensures web content is accessible to all users, including those with disabilities. 
25)strong type VS bold type: strong - how important the content is & bold- for highlighting 
26) Text centre
27) Flex box
28)HTML How do you know which html version is being used <!docType>, or if version will be displayed , some parser , or can see HTML5 features 
29)What are css preprocessors How do you write browser specific css? preprocessors- added features sass/scss, stylus, LESS -scss is preferable for complex project
browser specific css: media queries, CSS hacks, Preprocessor directives- features provided by preprocessor , Test your code,Use feature detection, clean and maintainable
30)CSS Specificity  https://www.w3schools.com/css/css_specificity.asp - higher priority will have application 
31)Css selector : https://www.w3schools.com/css/css_selectors.asp class /Id

javascript
1) SCOPE VAR/LET /CONST 
	TEMPORAL DEAD ZONE: Time between a(variable) memory allocation( a =undefined)   and a(20)initialised
2) Callback hell:  Issue with CALLBACK- synchronous (runs immediately num=[1,2,3,] num.map(n=> n*2) )vs asynchronous 
limitation of callback, print 1,2,3 when called same function using callback
Asynchronous Programming exist in JS exist due to CALLBACK
3)  Promise: is an object representation of Eventual Completion or failure of Async Opeartion, can handle more effeicntly then call back
 How to fetch data from backend ? Multiple fetch api: Promise.all() and map()
Write a promise if number is more than 2 Resolve it else error , custom promise 
When to use promise vs async awaits ? 
Async awaits - readability more simplified way- (do not usees .then- promise chain)  , async- invoke promise awaits wait till it git resolved ,use try and catch for error handling ,latest browser ,older browsers- do not support async and awaits 
Not to opt: Single Synchronous Operations, more complex nested scenarios , 


4) Closure : function with lexical scope , when function return function which can remember	pervious function data/varibale 
5)This keyword: behaves differently how it is called
https://www.w3schools.com/js/js_this.asp

6) Object Assignation Method & why Object.create is preferable & write own polyfil-protoype 
Object creation different techniques 
Display keys of object ?

7)setTimeout  & setInterval & clearInterval(NULL)
8) call apply bind [CAB] passing Object to Function  OR Function.OBJECT - practical usage ?
9)Event loop ? call stack/microstack queue /callback Queue ? How to improve queue 
10)Cookies VS local VS Sesssion 
11)Event delegation vs enent Propagation and immediate propagation and EventBubbling and eventLooping 
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#using_addeventlistener
https://www.w3.org/TR/DOM-Level-3-Events/
12 ES6 standard : literal, spread, rest, destructure , arrow function ,promise, let ,const, class 
13)Progressive Web App (PWA)/ OFFLINE service worker /Web accessibility /AA,AAA standard/Accessibility 
14)Intereceptor
15)What is generator function and why do we use it : yield- if you call Generator Function more than onec - it pause execution and execute from next yield 
What will happen if no next is called ? on the iterator object, the generator function will not execute
16)Deep copy 
const deepCopy = JSON.parse(JSON.stringify(nestedObject));
17)Event curry ? what is the usage why we use it -  f(a, b, c) into callable as f(a)(b)(c).: Currying doesn’t call a function. It just transforms it.
Event currying in JavaScript is a technique where you pre-configure an event listener with some initial arguments before attaching it to an element. This can be helpful for situations where you want to reuse the same event handler with different configurations for different elements.
Partial Function Application: Currying allows you to create specialized functions by fixing some arguments of a function
// Curried function to add two numbers
const add = (a) => (b) => a + b;

const addFive = add(5); // Fixing the first argument
console.log(addFive(3)); // Output: 8 (5 + 3)


18)Memory leakage ? how to check is your code is Memory leakage  proof ? in javascript
memory profiler: Tools like Chrome DevTools : analyze memory usage and detect potential leaks
Avoid global variables
19)declarative and imperative : JS is both  imperative(Procedural, OOPS)
20)MapObject vs Object ?
21)  global key- payment keys/ gateway keys- these are common and can’t be changed 
			- store in CONST : block
			- store in VAR: GLOBAL
What is difference and how this will impact code/speed: VAR,GLOBAL- increase the speed - we can’t	be used for const
22)for every change in textbook will trigger the Render how to prevent that 
	De-bouncing - search is commonly used for scenarios like search input fields, where you want to wait for the user to finish typing before triggering a search request.
	Throttling is commonly used for scenarios like handling scroll events, where you want to limit the frequency of function invocations to avoid performance issues.
      - a technique that ensures that the flow of data being sent into a target can be digested at an acceptable rate.
	PreventDefault() : prevent a browser from reload 
23)OOBJ - Polymorphism, -different form, abstraction:hide ,encapsulation:follow process -Petrol car put petrol ,inheritance- feature parent in child component super oops
24) CLASS/ Function ? Can a function will have Constructor ? - no ,Constructor= initial initialisation ,- useState[initilazation]
Typescript Class vs interface
25)Javascript what is the difference between regular function and arrow function & PURE FUNCTION 
Arrow function => , small ,Inherits this binding from surrounding context,Cannot be used as constructor- new keyword not be used in calling object 
26)map vs foreach : foreach - return UNDEFINED, can’t mutate (x.foreach().reduce not possible), transformation using callback , iteration speed is fast 
map - return new array , can mutate x.map().reduce(), transformation accept function  
27)how to make async to synch - using removing callback - direct call function in place of arrow function callback
28) web worker : https://www.youtube.com/watch?v=JMKLXGwltGc
Its like provide complex function in separate web worker so that it provides separate thread kind of thing (multi threading ) to make fast 

Critical rendring path -async vs defer 
Q1- setTimeout
Q2- Placement of JS
Q3- let, const and var defference
Q4- closure
Q5- Functional Programming (Pure Function)
Q6- this keyword 
Q7- Frameworks
Q8- Prototypical Inheritance
Q9- Promises, Async, Await and callback
Q10- Debounce and Throttle

—————

1)SPA microServices UI ?(MF -micro FrontEnd ) - Component Decomposed into small component  based development/deployemnt based on different technology which makes services fast in terms of changes deployment/devlop
	- monolethic repository approaches has lot of disadvantages which will be removed by SPA microServices
Creating the Root Configuration
 Registering Three Applications
Configuring the Root App — Add Shared Dependencies
Register Applications
Add the Single-SPA Application into the Import Map
Q. what difference  Runtime MFs vs Build-time MF
RunTIme: each micro frontend is a standalone application that is loaded and executed in the user's browser at runtime
Build-time MF: he micro frontends are compiled and built together during the build process. The final output is a single bundled application that includes all the micro frontends
2)difference between yarn and npm
While NPM fetches packages from the online npm registry for every 'install' command, YARN stores dependencies locally in most cases and fetches packages from a local disk
considerably faster 
3) Redux Async and await 
export const fetchCounter2Data = () => async (dispatch) => {
  try {
    const response = await axios.get('https://api.example.com/counter2');
    const data = response.data;
    // Dispatch action with fetched data
    dispatch({ type: 'FETCH_COUNTER2_DATA', payload: data });
  } catch (error) {
    console.error('Error fetching Counter 2 data:', error);
  }
};

dispatch({ type: 'FETCH_COUNTER2_DATA', payload: data });

Here, dispatch is used to send an action to the Redux store. The action has a type of 'FETCH_COUNTER2_DATA' and a payload containing the fetched data. This action will be processed by the appropriate reducer, and the state associated with 'FETCH_COUNTER2_DATA' will be updated accordingly.

Component re render and updated value will be available 

4) Other library used with React
* 		State Management:
    * Redux: A popular library for managing global state in a predictable way.
    * Context API: Built-in React feature for managing state without external libraries.
* 		Routing:
    * React Router: A library for handling navigation and routing in a React application.
* 		UI Components:
    * Material-UI: A popular UI framework with pre-designed components following Material Design guidelines.
    * Ant Design: A comprehensive UI framework with a set of high-quality components.
    * Chakra UI: A modular and accessible UI component library.
* 		Forms and Validation:
    * Formik: A library for building forms in React, with support for validation and error handling.
    * React Hook Form: A library for managing form state and validation using React hooks.
* 		API Requests:
    * Axios: A promise-based HTTP client for making API requests.
    * Fetch: A built-in browser API for making network requests.
* 		Styling:
    * Styled Components: A library for writing CSS-in-JS and styling React components.
    * CSS Modules: A way to locally scope CSS classes in React components.
* 		Stateful Logic:
    * React Query: A library for managing and fetching data with caching and automatic refetching.
    * SWR (Stale-While-Revalidate): A hook for remote data fetching with caching and revalidation.
* 		Animation:
    * React Spring: A library for animating UI elements using spring physics.
    * Framer Motion: A library for creating smooth animations and interactive UI.
* 		Testing:
    * Jest: A popular testing framework for testing React components and applications.
    * React Testing Library: A library for testing React components with a focus on user behavior.
* 		State Visualization:
    * Redux DevTools: A browser extension for debugging and inspecting Redux state.
* 		Code Quality:
    * ESLint: A popular linting tool to enforce coding standards and identify potential issues.
    * Prettier: A code formatter that ensures consistent code style.
* 		Build Tools:
    * Webpack: A module bundler for building and packaging applications.
    * Babel: A transpiler that converts modern JavaScript code to a backward-compatible version.

import useErrorBoundary from "use-error-boundary"


5) Pi chart : chart type, width ,height , data
Google pie chart
Hi chart
Apex chart 
https://www.youtube.com/watch?v=-CwzaTKniH4


6)useState, useEffect,customHook,useReducer, useMemo,useCallback,ContextAPI
7)MSIL 
Microsoft Intermediate Language
login authentication is a secure way to authenticate users because it uses cryptography to protect the user's credentials. The MSIL code is encrypted before it is sent to the server, and only the server can decrypt it. This prevents unauthorized users from intercepting the user's credentials and gaining access to the application.
8) why class component Name start with CAPITAL letter 

————
1) VDOM : As you can see, the React application communicates with the DOM through ReactDOM, which is a library that is part of React. ReactDOM is responsible for taking the VDOM and updating the DOM to reflect it.
The reconciliation process takes place in the browser. It is the responsibility of the browser to update the DOM to reflect the changes in the VDOM. The React application provides the VDOM to the browser, but the browser is responsible for updating the actual DOM nodes.
VDOM: stores in app 

Javascript Architect: 
MicroFrontend :Independent Development/Loose Coupling/Scalability/Seamless Integration/Continuous Delivery/Independent Deployment
What is micro front end ?
Multiple micro UI, microservices 
Has common container : common code share
All other projects are loosely coupled : means not attached directly so if one is fairly other will not impact it 
All project have developed/deployed/maintained  separately - ci/cd pipelines , programming also
 
Micro-Frontends architecture allows teams to work independently, iterate faster, and scale their frontend development efforts. It promotes modularity, reusability, and agility by breaking down the monolithic frontend into smaller, manageable parts

Module federation 


2)Webpack:  [bundlers /code splitting /loader]
Web pack removes : Manual Script Tags/Concatenation/Dependency Management Librarie
Features : Module Bundling/Code Splitting:/Loaders- transpolar/Plugins- minification,asset management, HTML generation
Configuration- entry point 

Development Server: built-in development server that enables live reloading and hot module replacement. It automatically refreshes the browser w
Asset Management: handle  assets, including images, fonts, and other static files. It can optimize and bundle these assets
Optimization:code minification, tree shaking to eliminate unused code, scope hoisting to reduce bundle size, 
Configuration: entry points, output paths, module rules, plugins, and other settings. T
Asset Optimization: optimize  JavaScript, CSS, images, fonts, and more.
Hot Module Replacement (HMR):  which allows you to update modules in the browser without requiring a full page refresh.
Multiple Environments: configure multiple environment
Integrating with CSS Preprocessors: Sass, Less, and PostCSS.

config file -> 
a)entry point (starting points )-> build the dependency graph of your project
						 dependency graph [start loading what next file (import/export),image etc it needs ]
b)Generates output bundles- js file  that contains all the code and assets required to run your application.(Dist/bundle.js)
c) output bundles & dependency graph combines 
d)loaders: transpiling /styling/aset handling/CODE analysis  Babel, compile SCSS to CSS, or process image files
		Code Analysis- eslint-loader/ts-loader
e) plugin: html web pack plugin

When webpack generates the output bundles, it combines the modules from the dependency graph and their dependencies into these bundles. The resulting bundles can be included in your HTML files to run your application in the browser.


What is there in web pack configuration file ? Entry point, output,Loaders,Plugin,mode,devserver,resolve 
3) Code splitting VS Lazy loading	? Where the code splits actually: INSIDE CONFIG.JS. ? Dynamic Import 
4)useCallback ? Usememo ? User ? ContextAPI  ? customAPI  ?
useCallback ? - component has - increment counter & add new bed Item , if increment is clicked - add new bed Item - put bed function in UseCallback
useMemo ? - height of barchart ? Fetch all y axis - now take maxHeight ? - calculate maxHeight near to 100 -50

 git merge and rebase Git command for cherry-picking Git reset head
5)React vs ReactDom ? React-library , create Ui, reactDom- package , render UI to DOM 


Q what is diff between nav nabber useNaviagte Navigate - react router DOm 


TEST what they test
1)SCOPE - BLOCK,SCRIPT,Functional & Global Closure
Let,const  are Block scope  

Var has access to lexical  environment and shadows outer declaration 
function example() {
    // Outer lexical scope
    var varVariable = "Outer var";
    let letVariable = "Outer let";
    const constVariable = "Outer const";

    if (true) {
        // Inner block
        var varVariable = "Inner var"; // Overrides outer variable 
        let letVariable = "Inner let"; // Creates a new variable in block scope
        const constVariable = "Inner const"; // Creates a new constant in block scope

        console.log("Inside block:");
        console.log("varVariable:", varVariable);   // Inner var
        console.log("letVariable:", letVariable);   // Inner let
        console.log("constVariable:", constVariable); // Inner const
    }

    console.log("Outside block:");
    console.log("varVariable:", varVariable);   // Inner var (overridden)
    console.log("letVariable:", letVariable);   // Outer let (not affected)
    console.log("constVariable:", constVariable); // Outer const (not affected)
}

example();

2) WEB API:
Console
DOM API
FETCH API
SETTIMEout
Location 
Local storage 

2nd-Callback Queue,1st-MicroStack Queue
	- starvation : queue is full use SetInterval
			 web worker - run the long running job with the other thread 
EventLoop: GateKeeper 
Call Stack 

3)
CAB,
MRF- HOC 

4. EVENT 
https://www.youtube.com/watch?v=ndfGreSllqM



Go through:
Unit testing 
Unmount - cleanup 
Psudo classes 
Polyfill of promiseall
Translator

Extra things 
Language Translator i18n
Charting library 
Classs based 
JWT bearer token 
Hooks implementation 
Error Boundary 
Q14 What are refs in React?
Q15 forwardRefs in React?

# Seaason 2.1 Tech Mahindra 
```
Q. Output 
// console.log(count())
// console.log(count())
 
// console.log(count())
 
// output
// 1
// 2
// 3
- Closure Using calling 3 times 

Q. Authorisation and authentication 
Q. CSS 
Sudo class
Css specificity - id , class, inline,css 
Blind css 
 Q. Js 
Callback limitation - memory issue, debugging , unnecessary loop 
Event delegation - 
Promise vs Async and await 
Q. React js 
How data can be passed from child to parent - callback or Redux 
Q. Next js - server side rendering 
Q. Figma, Webpack 
Q. How you fetch the continuous data from backed from UI eg. score Live - setInterval is not good approach 
```
DEBasis Node js  
Q nodejs  - how to send html 
Q. create server 

