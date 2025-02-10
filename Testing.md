# EP13 Testing 
## Q. Types of testing 
- Unit Testing : Test only Header 
- Integration Testing : search for Pizza in APP(multiple module to be Tested )
- End to End Testing : (all the Flows - User landing to page & exiting the page )

## Q. jest is JS library
React Testing Library is actaully `DOM testing Library` which -> uses `JEST` -> uses `babel` 

## Q. setup
- Setting up Testing in our app
- Install React Testing Library
- Install Jest
- Install Babel Dependencies
- Configure Babel
- Configure Parcel Config File to disable default Babel transpilation
- Jest - npx jest --init
- Install `jsdom` library -`its not browser but kind of Browser all our testing code runs here`
- Install @babel/preset-react - to make JSX work in test cases
- Include @babel/preset-react inside my babel config
- npm i -D @testing-library/jest-dom
- npm run test

## Q.where to put your code during Testing with Example
- __tests__ `dender test` put all your module here 
- Eg. if you want to test sum.js Module 
```
Sum.js
	export const sum =(a,b)=>{return a+b}
```
```
__tests__
Sum.test.js
Import {sum} from ’Sum.js’
//test(’Description_string’,callback_Function )

Test(“sum of two numbers”,()=>{
	const result= sum(2,3)
//Assertion 
	expect(result).toBe(7)
})
```
## Q. Q how to group 
- Using `describe` (‘groupby String ’, ()=>{All your test cases})

 ```
describe (‘groupby String ’, ()=>{
Test(“sum of two numbers”,()=>{.   // inlace of TEST we can also write IT
	const result= sum(2,3)
//Assertion 
	expect(result).toBe(7)
})})
```
