### Q.1 Add  or Sub
- console.log("O========Operation ================")
- console.log("(-) Behaves mathimatic and converts as       2-2= ","2"-"2")
- console.log("(-) Behaves mathimatic and converts as       A-2= ","A"-2)
- console.log("(+) Behaves concatination and converts as string= ","2"+"2")
- console.log("2"-2)
```
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
- undefined
```
let x;
console.log(typeof x);
```
- Error

### Q.3 Hoisting:Function defined after usage

```
console.log(getName)

function getName() {
console.log("Hello world")}
```
- [Function Object]
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
[Function: getname]
JS
undefined

4)console.log("4========================")
console.log("GLOBAL SCOPE created, then local scope created doSomething, after execution it got deleted   ")
var x=2 
function doSomething(){
   var x= 33;
  console.log(x);
 
}

doSomething()
console.log(x)
33
2
b)var x =21.                 //1st GLOBAL Execution scope- x defined as undeclared
function xyz(){
    console.log(x)
    var x=20                   //2nd  GLOBAL Execution scope- x defined as undeclared 
}
xyz() - undefined


console.log("5========================")
console.log( "BLOCK SCOPE VS GLOBAL SCOPE") 
a)var a=2
{   
    var a = 100
    console.log(a)
}

  console.log(a)
 
  console.log("block scope a shadows GLOBAL SCOPE, both defined in GLOBAL ")
Trying to access same global scope
100
100
var a=2
{   
    var a = 100
    console.log(a)
}

  console.log(a)	let a=2
{   
    let a = 100
    console.log(a)
}

  console.log(a)	var a=2
function xyz()
{   
    var a = 100
    console.log(a)
}
xyz()
  console.log(a)	
var a=2
function xyz()
{   
    
    console.log(a)
}
xyz()
  console.log(a)
100,100	100,2	100,2	2,2



console.log("6========================")
console.log( "BLOCK SCOPE VS GLOBAL SCOPE") 
var a=2
{   
    let a = 100 // let & let possbile – same SCOPE result
    // let & var not possible : redefined Error 
    console.log(a)
}

  console.log(a)
 100
2

  console.log("block scope a shadows GLOBAL SCOPE, both defined in GLOBAL ")
  console.log("7========================")
console.log("SetTimeout is callback, and runs on web api, till it come back its i value updated due to GLOBAL scope")
for(var  i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
} 
6,6,6,6,6,6

console.log("8========================")
a)console.log("SetTimeout is callback, and runs on web api, LET will give updated copy of vailable in every loop")
for(let i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
} 

0,1,2,3,4,5
console.log("8.1========================")

let i=0;
for(  i=0;i<=5;i++){
    setTimeout(() => {
      console.log(i);
    }, 1000);
}
6,6,6,6,6,6

8.2) How you can achive LET  using VAR
for(var i=0; i<=2; i++){
    setTimeout(function(){console.log(i)}, 1000);
}
Expected Answer:: 0,1,2
function print(i){
    setTimeout(function(){console.log(i)}, 1000)
}

for(var i=0; i<=2; i++){print(i)}
0,1,2 

 const arr=[5,1,2,3,4,6]. : SIMILAR to LET & MAP gives new copy of array in every transaction 
console.log("9========================")
console.log("MAP: transformation 2=> 2square")
function binary(x) {
			return x.toString(2)	}

const output = arr.map(binary) //
console.log("output : ",output)
output :  [ '101', '1', '10', '11', '100', '110' ]


console.log("10========================")
console.log("Filter: filter ODD Number ")
function isodd(x){
		return x%2
		}
// const output = arr.filter(isodd)
const output2 = arr.filter(function isodd(x){
		return x%2
		})

const arr=[5,1,2,3,4,6]
// const output = arr.filter((x) => x%2)
output :  [ 5, 1, 3 ]
// arr.map(x=> x%2)
Output: (6) [1, 1, 0, 1, 0, 0]


console.log("10.1========================")
console.log("Reduce : sum of number ")

const output3 = arr.reduce(function(acc,curr) { acc=acc+curr;
            return acc},0)

Reduce : sum of number 
output :  21

OR
arr = [1,2,4,5,6]
console.log(arr.reduce((a,c) =>  a+c ))
18 Flatten array
Arr1 = [1,2[3,4],[4,5[7,8]]]
Make it simple Arr1 =[1,2,3,4,5,7,8]
Steps:
1)common func with input & flattenarry output
2)check in loop if element is   Array.isArray
3)yes- call common func & store result 
3.1) result is and array so insert one by one to flattenarry output
4)No- means its an element so let it insert flattenarry output


console.log("11========================") FLATTEN array
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
[
  1, 2, 3, 4,
  4, 5, 7, 8
]



console.log("12========================")
console.log("FuNction Overloading : same name with different argument")
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

FuNction Overloading : same name with different argument
Hello, John!
Hello, John!
Hello, Jane!
Hello, Bob!
Hello, stranger!
![image](https://github.com/user-attachments/assets/1a0298b7-7f0d-4d46-abd5-b29e817ed9b9)
