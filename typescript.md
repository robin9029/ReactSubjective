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
