## Q.Type: generic
```
function getArray<T>(items: T[]): T[] {
  const result = [];
  for (const item of items) {
    result.push(item);
  }
  return result;
}

const numbers = getArray<number>([1, 2, 3, 4, 5]);
console.log(numbers)
```
- > [ 1, 2, 3, 4, 5 ]
```
const strings = getArray<string>(['hello', 'world', 'foo', 'bar']);
console.log(strings)
```
- > [ 'hello', 'world', 'foo', 'bar' ]

```
function identity<T>(arg: T): T {
    return arg;
}

console.log(identity<string>("Hello"));  // Output: Hello
console.log(identity<number>(42));       // Output: 42
```
## Q. difference between Class vs interface

![Screenshot 2025-02-14 at 6 58 36 PM](https://github.com/user-attachments/assets/74f19e66-6971-4bd8-a75f-4ed6b19b6752)

```
// Interface for Object with extends function 
interface ForObj { 
	First: string 
} 

interface forNewObj extends ForObj { 
	Second: number 
} 

let newArray: forNewObj = { 
	First: "Interface for Object", 
	Second: 2 
}; 
console.log(newArray);
```
- > { First: 'Interface for Object', Second: 2 }

