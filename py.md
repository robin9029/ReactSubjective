## CBA 
- LIST comprehension flat 2*3 array
- how to declare private variable - __
- OOPS concepts
- let str = 'abc_def_001'; increment using 002, 003 etc 
```
let str = 'abc_def_091';
let num= Number(str.substr(8))
let newStr= str.substr(0,8)
console.log(str.lastIndexOf('_'),newStr,num)

num += 1
num<9? num ='00'+num : num<99 ? num ='0'+num :num
console.log(num, typeof(num))

console.log(newStr+num)
```
