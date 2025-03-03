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

# Q and A
### Q.1 Add  or Sub
- console.log("O========Operation ================")
- console.log("(-) Behaves mathimatic and converts as       2-2= ","2"-"2")
- console.log("(-) Behaves mathimatic and converts as       A-2= ","A"-2)
- console.log("(+) Behaves concatination and converts as string= ","2"+"2")
- console.log("2"-2)
```
o/p
(-) Behaves mathimatic and converts as Number       2-2=  0
(-) Behaves mathimatic and converts as String       A-2=  NaN
(+) Behaves concatination and converts as string	     =  22
0
```

### Q.2 Hoisting:variable defined after usage
```
console.log(x)
var x=20
```
- o/p: undefined
```
let x;
console.log(typeof x);
```
- o/p: Error

### Q.3 Hoisting:Function defined after usage

```
console.log(getName)

function getName() {
console.log("Hello world")}
```
-o/p:  [Function Object]
- program before execution skims code and reserve memory for variable=undefined and function = whole function it self
```
function getName() {
console.log("Hello world")
}
```
### Q.4 Function defined as variable and store as undefined first")
```
var getname = () => {
    console.log("JS")
}
console.log(getname)
console.log(getname())
```
- > [Function: getname]
- > JS
- > undefined

### Q.5 GLOBAL SCOPE created, then local scope created doSomething, after execution it got deleted   
```
var x=2 
function doSomething(){
   var x= 33;
  console.log(x);
 
}

doSomething()
console.log(x)
```

- > 33
- > 2
```  
b)var x =21.                 //1st GLOBAL Execution scope- x defined as undeclared
function xyz(){
    console.log(x)
    var x=20                   //2nd  GLOBAL Execution scope- x defined as undeclared 
}
xyz()
```
- undefined

### Q.6  "BLOCK SCOPE VS GLOBAL SCOPE"
```
a)var a=2
{   
    var a = 100
    console.log(a)
}
  console.log(a)
```
- block scope a shadows GLOBAL SCOPE, both defined in GLOBAL, Trying to access same global scope
- > 100
- > 100

![Screenshot 2025-02-12 at 12 02 19 AM](https://github.com/user-attachments/assets/a358d099-ba93-4d53-ac2a-f192b4aa4443)

### Q.7 BLOCK SCOPE VS GLOBAL SCOPE
```
var a=2
{   
    let a = 100 // let & let possbile – same SCOPE result
    // let & var not possible : redefined Error 
    console.log(a)
}
  console.log(a)
```
- > 100
- > 2
-block scope a shadows GLOBAL SCOPE, both defined in GLOBAL 

### Q.8 SetTimeout is callback, and runs on web api, till it come back its i value updated due to GLOBAL scope
```
for(var  i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
}
```
- > 6,6,6,6,6,6

#### SetTimeout is callback, and runs on web api, LET will give updated copy of vailable in every loop
```
for(let i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
} 
```
- > 0,1,2,3,4,5
```
let i=0;
for(  i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
}
```
- > 6,6,6,6,6,6

#### How you can achive LET  using VAR
```
for(var i=0; i<=2; i++){
    setTimeout(function(){console.log(i)}, 1000);
}

```
- Expected Answer:: 0,1,2
```
function print(i){
    setTimeout(function(){console.log(i)}, 1000)
}

for(var i=0; i<=2; i++){print(i)}
```
- > 0,1,2 

- SIMILAR to LET & MAP gives new copy of array in every transaction ??
### Q9. MAP , Filter Reduce [MRF]
-MAP SIMILAR to LET & MAP gives new copy of array in every transaction
- "MAP: transformation 2=> 2square"
```
const arr=[5,1,2,3,4,6]
function binary(x) {
			return x.toString(2)	}
const output = arr.map(binary) 
console.log("output : ",output)
OR
console.log(arr.map(x=>x.toString(2)))
```

- > output :  [ '101', '1', '10', '11', '100', '110' ]

#### Filter: filter ODD Number 
```
function isodd(x){
		return x%2
		}
const output = arr.filter(isodd)
const output2 = arr.filter(function isodd(x){
		return x%2
		})

const output3 = arr.filter((x) => x%2)
```
- > output :  [ 5, 1, 3 ]
- arr.map(x=> x%2)
- > Output:  [1, 1, 0, 1, 0, 0]


#### Reduce : sum of number 
```
const output = arr.reduce(function(acc,curr) { acc=acc+curr;
            return acc},0)
```
- > output :  21

OR
```
arr = [1,2,4,5,6]
console.log(arr.reduce((a,c) =>  a+c ))
```
### Q.10 Flatten array
- Arr1 = [1,2[3,4],[4,5[7,8]]]
- Make it simple Arr1 =[1,2,3,4,5,7,8]
```
Steps:
1)common func with input & flattenarry output
2)check in loop if element is   Array.isArray
3)yes- call common func & store result 
3.1) result is and array so insert one by one to flattenarry output
4)No- means its an element so let it insert flattenarry output
```

```
console.log("Array Flaten Arr1 = [1,2[3,4],[4,5[7,8]]] ")
var arr1 = [1,2,[3,4],[4,5,[7,8]]]
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
console.log(flattenArray(arr1))
```
- > [1, 2, 3, 4,4, 5, 7, 8]


### Q.11 FuNction Overloading : same name with different argument")

```
function greet(name) {
  if (typeof name === 'string') {
    console.log(`Hello, ${name}!`);
  } else if (Array.isArray(name)) {
    name.forEach((n) => {
      console.log(`Hello, ${n}!`);
    });
  } else {
    console.log('Hello, stranger!');
  }
if (typeof name == 'number'){
        console.log(" Number ", name )
    }
}

greet('John'); // logs "Hello, John!"
greet(['John', 'Jane', 'Bob']); // logs "Hello, John!", "Hello, Jane!", "Hello, Bob!"
greet(); // logs "Hello, stranger!"
```
- > FuNction Overloading : same name with different argument
- Hello, John!
- Hello, John!
- Hello, Jane!
- Hello, Bob!
- Hello, stranger!

### Q.12 Output ?
```
let c ={greeting: "Hey!"}
let d;
d=c;
c.greeting ="hello";
console.log(d.greeting)
```
- >  Pointing to same memory location in SCOPE, VAR also will be same 
- >  o/p - hello for both
### Q.13 Output
```
const bird = {size: "small"}

const mouse ={
    name: "Micky",
    small: true 
}
```
- > //console.log(mouse.bird.size)   // : referenceError: : 
- > console.log(mouse[bird.size]) `true`
- > console.log(mouse[bird['size']]) `true`
### Q.14 Output
```
const person ={name: "Lydia"}
Object.defineProperty(person,"age",{value: 21})
console.log(person)               //{name:"Lydia",age:21 }
console.log(Object.keys(person))         //['name']
```
### Q.15 Output

```
const myPromise =() => Promise.resolve("I have resolved ")
function myFirstFunction(){
    myPromise().then(res => console.log("res: ",res)) // .then return a callback
    console.log('second')
}

// second
// res:  I have resolved   promise : due to callback

async function  mySecondFunction() {
    console.log(await myPromise())     //first resolve await and then move next line 
    console.log('SeconD')
}
myFirstFunction()
mySecondFunction()
```
```
// second
// res:  I have resolved   
// I have resolved 
// SeconD
```
### Q.16 Output
```
const foo = () => console.log("First")
const bar = () => setTimeout ( () => console.log("Second"))
const baz = () => console.log("Third")

bar()
foo()
baz() 
```
```
//o/p
// First 
// Third 
// Second : callback 
```
### Q.17 Output
```
String.prototype.giveLidyaPizza = () => {
    return "just Given lidya pizza already ";
}

const name = "Lydia";
console.log(name.giveLidyaPizza()); // This will print the returned string to the console
```
- > just Given lidya pizza already

### Q.18 Output
```
/ how log cool_secret accessable ?
sessionStorage.setItem("cool_secret",123);

// till when the browser closed
```
### Q.19 Output
```
function getAge (...args){
    console.log(typeof args)
}

getAge(21)  
```
  > OBJECT
  >  JavaScript, the typeof operator returns a string indicating the type of the operand.
  > For arrays, typeof will return "object", since arrays are a special kind of object. 
```
function getAge1 (args){
    console.log(typeof args)
}
getAge1(21) 
```
> NUMBER
### 20. In javascript when to use for..of , foreach, map with example ?
for.. of : can be break loop,used for all iteration set,array,string.
```
const message = "Hello"; or const mySet = new Set([1, 2, 3]);
for (const char of message) {
  console.log(char); // Output: H, e, l, l, o (each on a new line)
}```

foreach:    no break in loop, used for side effect, works on array
Map:  no break in loop, used for side effect, works on array,  new arrary creation 
```

![Screenshot 2025-02-21 at 10 51 11 AM](https://github.com/user-attachments/assets/337e790c-5010-498d-8acb-5cde1b40f773)

### 21. find the non repeating char

```
str = "abcba"
//c 1st and last index are same 

console.log(str.charAt(2))
console.log(str.indexOf("c"))
console.log(str.lastIndexOf("c"))

function findNonRepeat(str){  
  for (let i =0; i < str.length; i++){
  let j = str.charAt(i)  
  if(str.indexOf(j) == str.lastIndexOf(j)){
    console.log(" non repeating ",j)
  }
  
  }
}
findNonRepeat(str)
```
```
for (let i of str){
    if (str.lastIndexOf(i) == str.indexOf(i)){
        console.log(i)
    }}
```
### 22 Find minimum of array = [40,20,30,2,5,6]
```
function findMinimum(arr) {
  if (!arr || arr.length === 0) {
    return undefined; // Or throw an error, depending on your needs
  }

  let min = arr[0]; // Initialize min with the first element

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < min) {
      min = arr[i]; // Update min if a smaller element is found
    }
  }

  return min;
}

const myArray = [40, 20, 30, 2, 5, 6];
const minimumValue = findMinimum(myArray);
console.log("Minimum value:", minimumValue); // Output: Minimum value: 2
```
```
//Alternative using Math.min and spread syntax.
const minimumValue2 = Math.min(...myArray);
```
### 23
```
const arr=[1,2,3];
console.log(arr);
arr.push(4);
console.log(arr);

 O/p : [1,2,3,4] because its reference constant
```
### 24 Spread operator 
```
arr =[1,2,3]
arr2 = [3,4,5]

// arr3 = arr+arr2
// arr3 = [...arr,...arr2]

arr3=[1,2,3,...arr,7,9,10,...arr2]
console.log(arr3)
```
```
//When pass argument as spread operator 
<FunctionA value= {}>

function getSum(...nums){
// its an Object
}
```
// Spread operator 2
```
const student = { name: "ravi",place:"Sahibganj",age:33}
let studentOne = {...student,name:'Kumar'}
console.log(studentOne)
```
//{name: 'Kumar', place: 'Sahibganj', age: 33}

```
const {name,...rest}= student
console.log(name,typeof name)
console.log(rest,typeof rest)
```
- // ravi - string
- //{place: 'Sahibganj', age: 33} 'object'

### 25 insert In between 

- var str = "hello How are you ?"
 - o/p: "hello Shaket How are you ?"

```
var str2 = " Shaket"
console.log(str.substr(0,5)+str2+str.substr(5))

// or 
function insert (str,index,value){
    return str.substr(0,index) + value + str.substr(index)
}

console.log(insert(str,5,str2))
o/p: "hello Shaket How are you ?"

OR

let res = str.replace(/hello/g,'hello Shaket') where g= global varible 
console.log(res)
```

### 26 Splice(start position,delete till the number of element): Modification in array: mutates
- Chilka kaat ke jo bacha wo original array left
```
const food = ['pizza', 'cake', 'salad', 'cookie'];

food.splice(2,1). //Delete salad then give 
 ['pizza', 'cake', 'cookie']

food.splice(2,0).  // start deleting from 2 to 0th means none 
 ['pizza', 'cake', 'salad', 'cookie']

food.splice(2).  // start deleting from 2 to all
['pizza', 'cake']

food.splice(3,0,'mitha'). //INSERT  ['pizza', 'cake', 'salad', 'mitha','cookie']
```


### 27 Slice(start position,  Provide number of element till you want  ): No Modification in array
- Takes chilka of Aam
```
const cities = ["Tokyo","Cairo","Los Angeles","Paris","Seattle"];

console.log(cities.slice(2,4));   // Here start from 2 got to 4th
[ 'Los Angeles', 'Paris' ]

const emojis =[1,2,3,4,]
emojis.slice(2,4,5)
```

- > (2) [3, 4]
- emojis
- > (4) [1, 2, 3, 4]

### 28 Convert Number to Array and find sum in single digit 
- number =5431 = 5+4+3+1 =13 = 1+3 = 4
  ```
function convertSingleDigit(n){
    //let str = `${n}`.  // convert to string  
    let arr = [...`${n}`].map(Number). // convert to array 
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
- OR 
```
function convertSingleDigit(n){
    let str =`${n}` // string 
    let arr = [...str].map(Number)
    const  sum = arr.reduce((a,c) => {return a+c} )
    if (sum > 9) 
    {
        convertSingleDigit(sum)
    }
    else {
        return console.log(sum)
    }
    }
convertSingleDigit(5431)```
### 29 output
```
function fun1(){
    setTimeout(() => {console.log(x);
        console.log(y)
    },3000) ;
    var x=2;
    let y=7;
}
fun1()
```
- o/p 2,7

### 29
```
let x ={},y={name:"Ronny" },z={name:"Jhon"}

x[y] = {name:"Vivek"}
x[z] = {name:"Akki"}
console.log(x[y])
console.log(x[z])
console.log(x)
```
- o/p
```
{name: 'Akki'}
{name: 'Akki'}
{[object Object]: {name: 'Akki'}}
```
### 30 Find max occurance of array ******* (for of used why ?)
```
const arr = [1,1,2,3,1,4]
const count ={};
for (const element of arr){
    console.log(count)
    if(count[element]) 
    {
     count[element] +=1;
    }
    else {
        count[element] =1;
    }
}
console.log(count)```

- { '1': 3, '2': 1, '3': 1, '4': 1 }

```
//Find Max occurance from result
let maxCount =0
var maxElement;
for(const [ele,count1] of Object.entries(count)){
    if(count1>maxCount){
       maxCount =count1;
       maxElement= ele
}
}	
console.log(maxElement)  ```

### 31
```
var b = b+1
console.log(b)
```
- > NaN
```
let a =a+1
console.log(a);;
```
- > refernce error 

```
console.log(typeof 42);;
//number
console.log(typeof typeof 42);;
//string
```
```
var arr=[1,2,3,4]
arr.concat([5])
console.log(arr,arr.length) 4 : concat() method does not modify the original array,
```
- > [ 1, 2, 3, 4 ]
- > Length 4


### 32 Short objectArray 
```
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];
sort on Number 
cars.sort(function(a,b){a.year-b.year})
 
cars.sort(function(a,b){
	let x= a.type.toUpperCase()
	let y= b.type.toUpperCase()
	if (x<y) return -1;
	if (x>y) return 1;
return 0; 
})
```

### 33
```
var arr= [3,5,7]
arr.foo="hello"

console.log("INDEX")
for(let i in arr){
    console.log(i)
}

console.log("Element"). //not part of element 
for(let i of arr){
    console.log(i)
}
```
```
INDEX
0
1
2
foo
Element
3
5
7
```


### 34
```
const promise=new Promise(res=> res(2))
promise.then(v => {
    console.log(v)
    return v*2
})
.then(v => {
    console.log(v)
    return v*2
})
.finally(v => {
    console.log(v)      //V is not accessible in finally
    return v*2
})
.then(v => {
    console.log(v) 
})
```
- o/p
```
2
4
undefined
8
```

### 33 write a program in javascript print the value from 1 and 20 of arr and incrementing one at a time , without printing array element

- const arr = [1, 3, 5, 10, 20];
```
let counter=0;
for(i=1;i<=20;i++){
    if(arr[counter]!==i){
        console.log(i)
    }
    else counter ++;
    
}
```
### 34 find the add the sum of number # factorial
```
function RecursiveFun(n){
   if (n>0) return n + RecursiveFun(n-1)
   else return n;
}
console.log(RecursiveFun(9))
```
### 35
```
function x(){
        setTimeout(() => {
      console.log(i);
    }, 1000)
        var i=10


}
x()
```
- > 10

### 36 find unique arraylist
```
Const input = [2,3,5,6,7,3,4,5,3] 
Const unique = […new Set(input)]
```
- OR
```
const uniqueArray = [];

for (let i = 0; i < input.length; i++) {
  if (!uniqueArray.includes(input[i])) {
    uniqueArray.push(input[i]);
  }
}
```
- If array is STRING 
```
const str =’235673453’ 

[...new Set(arr)].toString().split(',').join('')
```
### 37 O/p
```
let a = {
    name:"test"
}
let b ={...a}				//Deep copy 
b.name='test2'
```
- > a =test
- > b=test2
### 38 
```
let a = {
    name:"test",
    add: {code:1}
}
let b={…a}      //shallow at nested copy
b.add.code=2
```
- > console.log(a.add.code) - 2
- > console.log(a.add.code) -2
- a & b will be same  : Because shallow copy b={…a} but add is an object which refer to same address
### 39  Object  find only nun null keys
```
const obj1 ={
    key1:'test1',
    key2: 'test2',
    key3:'test3',
    key4:' ',
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
```
```
for(const i in obj1)
{   if(obj1[i]!=''){
    console.log(`${i}`,`${obj1[i]}`)
}}
```
### 40 o/p
```
function EmployeeName() {}

EmployeeName.prototype={
    names: [],
    showNames: function () {
        return this.names 
    }} 
var e1 = new EmployeeName();
e1.names.push("foo")		//foo
console.log(e1.showNames())


var e2 = new EmployeeName();
e2.names.push("bar")		//foo bar

console.log(e2.showNames())
```
- To fix this, you can create a separate names array for each instance of the EmployeeName function. This can be done by using the this keyword in the names property of the prototype object:
```
EmployeeName.prototype = {
    names: function () {
        if (!this._names) {
            this._names = []
        }
        return this._names
    }
};
```
### 41 PRIME NUMBER 
```
for (let i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
```
- how to caluclate 0-10 prime number ? just call above function passing range
  
### 41 arr = [1,2,3,2], find sum of all non repeating array sum=[1,3]=4
```
var arr = [1,2,3,2]
let countArr ={}

for(let i of arr){
    if(countArr[i]){
       countArr[i] += 1 
    }
    else {
        countArr[i] = 1 
    }}

var sum=0
for(let [ele,counter] of Object.entries(countArr))
{
    if (counter ==1){
        console.log(sum,"ele ",ele,"counter ",counter)
        sum += Number(ele)
        
}}
```
### 42 Binary Search
```
function BinarySearch(arr,target, start=0,end=arr.length-1){
    
    if(start> end){
        return -1
    }
    const mid =Math.floor((start+end)/2)
    
    if(arr[mid]== target){
        return mid
        
    }
    if (arr[mid]>target){
         return BinarySearch(arr,target,start,mid-1)
    }
    else {
        return BinarySearch(arr,target,mid+1,end)
    }
    }
```
- Example usage
```
const sortedArray = [1, 3, 5, 7, 9, 11, 13, 15, 17];
const target = 9;
const index = BinarySearch(sortedArray, target);
console.log(index)
```
### 43 o/p
- var arr = [4,5,6,7,8,2,5,6,7]
- o/p: [2,4,[5,5],[6,6],[7,7],8]
```
let uniqArr = [...new Set(arr)]
let finalArr = []

uniqArr.map(ele => {
    let subArr = []
    for(let i=0;i<arr.length; i ++ ){
        if(ele == arr[i]) {
          subArr.push(arr[i])  
          console.log(subArr)
        }}
    finalArr.push(subArr) 
})
console.log('res: ',finalArr)
```
### 44  Sort based on values and remove duplicates on key
- a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}]
-  output [{c: 0}, {a: 1}, {b: 2}]
```
const a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}];

const sortedAndDistinct = [...new Map(a.map(item => [Object.keys(item)[0], item])).values()]

sortedAndDistinct.sort((a,b) => Object.values(a) - Object.values(b))
console.log(sortedAndDistinct);
```
- OR
```
[...new Map(a.map(item=> [Object.keys(item)[0],item])).values()]
.sort((a,b)=> Object.values(a) -Object.values(b))
```
### 45 delete key
```
var Employee =
{
company: 'xyz'
}
var Emp1 = Object.create(Employee);
delete Emp1.company;
console.log(Emp1.company);
```
- > xyz. Deleting the instance 

### 46
```
var y = 1;
if (function F(){})
{
    console.log(typeof F).  //undefined 
y += typeof F;
}
console.log(y);
//undefined
```
### 47 How to Find the number is integer without using inbuilt function
```
function isInteger(num) {
  return typeof num === 'number' && Math.floor(num) === num;
}

var num = 42;

if (isInteger(num)) {
  console.log("The number is an integer");
} else {
  console.log("The number is not an integer");
}
```
### 48 difference between two code explain output *****
- 1)
```
const person = 
{  name: 'John Doe', 
 getName: () => {   return this.name;  } 
}; 
console.log(person.getName()); // Output: undefined
```
- Reason: The getName function inherits the this binding of its surrounding context, which is the global scope.
- The global scope doesn't have a name property, hence the undefined output.

```
const getNameBound = person.getName.bind(person);
console.log(getNameBound()); // Output: John Doe
```
- 2) 
```
const person = {  name: 'John Doe',
  age: 30,  
greetArrow:()=>{`this` automatically refers to person  OBJ
console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);  }, }

person.greetArrow(); // Outputs expected message, without 
Hello, my name is  and I'm undefined years old.
```
- Reason: The greetArrow function works because it directly accesses properties (name and age)
- of the object it's defined within (person).
- This is because the this context within the function automatically refers to the surrounding object.

### 49 Wiggle short - /**
```
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
```
### 50 
```
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
```
```
O/p 
1
2
4
timerStart
timerEnd
success
```
### 51 Program to create sub array of repeating elements of array,
### 52 convert below code to async and await 
```
function asyncTask() {
return functionA()
.then((valueA) => functionB(valueA))
.then((valueB) => functionC(valueB))
.then((valueC) => functionD(valueC))
.catch((err) => logger. error(err)) }
```
```
async function asyncTask() {
  try {
    const valueA = await functionA(); // functionA() resolves → valueA is assigned
    const valueB = await functionB(valueA); // functionB resolves → valueB is assigned
    const valueC = await functionC(valueB); // functionC resolves → valueC is assigned
    const valueD = await functionD(valueC); // functionD( resolves → valueD is assigned
    return valueD; // Return final result if needed
  } catch (err) {
    logger.error(err);
  }
}
```

![Screenshot 2025-02-23 at 10 09 33 AM](https://github.com/user-attachments/assets/ebec0e86-788d-41d6-a34d-a50c7774607d)

