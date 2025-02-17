Q.1 Add  or Sub
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
- > OBJECT 
```
function getAge1 (args){
    console.log(typeof args)
}
getAge1(21) 
```
- > NUMBER 


