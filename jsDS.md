- https://www.linkedin.com/feed/update/urn:li:activity:7126622705935663105?updateEntityUrn=urn%3Ali%3Afs_updateV2%3A%28urn%3Ali%3Aactivity%3A7126622705935663105%2CFEED_DETAIL%2CEMPTY%2CDEFAULT%2Cfalse%29

# SDET
## Q1. Reverse a String:
- Write a JS program to reverse a given string.
```
var str= "Welcome to Programiz!";
str.split('').reverse().join('')
```
- > 'Programiz! to Welcome'
####  O/p: emocleW ot !zimargorP 
```
function ReverseFun(str){
    let str2= str.split(' ')
    let final= ""
    for (let i=0;i<str2.length;i++){
        final += str2[i].split('').reverse().join('') +" "
    }
    return final
}

console.log(ReverseFun(str))
```
```
function resFun(str) {
  return str.split(' ').map(word => word.split('').reverse().join('')).join(' ');
}
```

## Q2.Find the Largest Element in an Array:
 Find and print the largest element in an array.

## Q3.Check for Palindrome:
- Determine if a given string is a palindrome (reads the same backward as forward).
```
var arr1= "abcba"
var arr= "abcba1" 

function Palindrome(arr){    
    n=arr.length
   for(let i=0; i<n/2 ; i ++ ){
      if( arr[i] !== arr[n-i-1])
     {
      //console.log(arr[i],arr[n-i-1],'its a NOT Palindrome')
       return 'its NOT a Palindrome';
     }
       return 'its a Palindrome'
    }
}
```
- console.log(Palindrome(arr)) - `its NOT a Palindrome`

- console.log(Palindrome(arr1)) - `its a Palindrome`
```
const input = "A man, a plan, a canal, Panama!";
const normalized = input.replace(/[^a-z0-9]/gi, '');
console.log(normalized); // Output: "AmanaplanacanalPanama"  `its a Palindrome`
```


## Q4. Factorial Calculation:
 Write a function to calculate the factorial of a number.
```
function fact(n) {
    let res = 1;
    for (let i = 1; i <= n; i++) {
        res *= i;
    }
    return res;
}
console.log(fact(5));
```
```
function fact(n) {
    if (n === 0 || n === 1) {
        return 1;
    }
    return n * fact(n - 1);  //recursive
}
console.log(fact(5)); 
```

## Q5. Fibonacci Series:
- Generate the first n numbers in the Fibonacci sequence.
- F(0) =0,f(1)=1
- F(n) = F(n-1)+F(n-2)
```
function fibonacci(n) {  
 if(n<=1) return n; 
else 
return fibonacci(n-1) + fibonacci (n-2); }   //recursive
```
- fibonacci(12); = 144

or 
```
function fibonacci(n){
 	var fibo = [0, 1]; 
 if (n <= 2) return 1;
 for (var i = 2; i <=n; i++ ){
 fibo[i] = fibo[i-1]+fibo[i-2]; 
}
 return fibo[n];
 }
```
 

## Q6. Check for Prime Number:
 Write a program to check if a given number is prime.
```
 for (let i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
```

## Q7. String Anagrams:
 Determine if two strings are anagrams of each other.
```
function areAnagrams(str1, str2) {
    // Normalize the strings: remove spaces and convert to lowercase
    const normalize = (str) => str.replace(/[^a-z0-9]/gi, '').toLowerCase();
    
    // Normalize both strings
    const normalizedStr1 = normalize(str1);
    const normalizedStr2 = normalize(str2);
    
    // Sort the characters of both strings
    const sortedStr1 = normalizedStr1.split('').sort().join('');
    const sortedStr2 = normalizedStr2.split('').sort().join('');
    
    // Compare the sorted strings
    return sortedStr1 === sortedStr2;
}
```
- Example usage:
```
console.log(areAnagrams("listen", "silent")); // true
console.log(areAnagrams("triangle", "integral")); // true
console.log(areAnagrams("apple", "pale")); // false
console.log(areAnagrams("A gentleman", "Elegant man")); // true
```
## Q8. Array Sorting:
 Implement sorting algorithms like bubble sort, merge sort, or quicksort.

## 9. Object sort 
```
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];
```
- sorting based on year
```
cars.sort(function(a, b){return a.year - b.year});
console.log(cars)
O/p
[  { type: 'Saab', year: 2001 },
   { type: 'BMW', year: 2010 },
   { type: 'Volvo', year: 2016 }]
   ```

- sorting based on Type
```
cars.sort(function(a, b){
  let x = a.type.toLowerCase();
  let y = b.type.toLowerCase();
  if (x < y) {return -1;}
  if (x > y) {return 1;}
  return 0;
});
```
```
console.log(cars)
[ { type: 'BMW', year: 2010 },
  { type: 'Saab', year: 2001 },
  { type: 'Volvo', year: 2016 }]
```
## Q9  Sort based on values and remove duplicates on key
 
```
 a = [{a: 1}, {b: 2}, {a: 1}, {c: 0}]
 output [{c: 0}, {a: 1}, {b: 2}]
```
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

## Q10. Binary Search:
 Implement a binary search algorithm to find an element in a sorted array.
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

## Q11. Duplicate Elements in an Array:
 Find and print duplicate elements in an array.

## Q12 Wiggle short - /**
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
```
```
const nums = [3, 5, 2, 1, 6, 4];
wiggleSort(nums);
console.log(nums); // Output: [1, 6, 2, 5, 3, 4]
```
