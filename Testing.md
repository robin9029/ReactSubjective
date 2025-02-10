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
src/components/__tests__/Sum.test.js
Import {sum} from ’Sum.js’

//test(’Description_string’,callback_Function ) this is format of test
Test(“sum of two numbers”,()=>{
	const result= sum(2,3)
//Assertion 
	expect(result).toBe(7)
})
```
## Q. how to group 
- Using `describe` (‘groupby String ’, ()=>{All your test cases})
- describe can have multiple describe nested
 ```
describe (‘groupby String ’, ()=>{
Test(“sum of two numbers”,()=>{.   // inlace of TEST we can also write IT
	const result= sum(2,3)
//Assertion 
	expect(result).toBe(7)
})})
```
## Q. Unit Testing 
```
import { fireEvent, render, screen } from '@testing-library/react';
import { Provider } from 'react-redux';   
import appStore from '../../utils/appStore';
import Header from '../Header';
import { BrowserRouter } from 'react-router-dom';
import '@testing-library/jest-dom';

it('Should change Login Button to Logout on click', () => {
  render(
    <BrowserRouter>
      <Provider store={appStore}>
        <Header />
      </Provider>
    </BrowserRouter>
  );

  const loginButton = screen.getByRole('button', { name: 'Login' }); // is recommended

  fireEvent.click(loginButton); //click Event 

  const logoutButton = screen.getByRole('button', { name: 'Logout' });

  expect(logoutButton).toBeInTheDocument();
});
```
## Q.Integration testing? Search- Scenerios As soon as my Body loaded it has 20 card &&  Search burger && we get 4 cart 
- Mock data because JestDOM doesn't work with Browser API- Fetch OR fake call

 ```
  const fetchData = async () => {
    const data = await fetch(URL))  //promise 
    const json = await data.json();  //promise 
    useListOfResturant(
      json.data.cards.filter((obj) => "info" in obj.card.card)
    );
  };
```
- JEST doesn’t work on Browser , this is running on JSDOM, - so it can’t make actual call So we are facking the calls
```
global.fetch = jest.fn(() => {
  return Promise.resolve({
    json: () => {
      return Promise.resolve(MOCK_DATA);  //manually you have to provide this data 
    },
  });});
```
- When you are updating your state wrap it to GET()
```
useListOfResturant(
      json.data.cards.filter((obj) => "info" in obj.card.card)
    );
```
- you can directly hit on the HTML using   screen.getByTestId 

- you have to provide this id into your Module return
```
<input
              type="text"
              data-testid="searchInput"
              placeholder="Search a restaurant you want..."
              className="px-4 py-2 border-0 border-transparent shadow-md font-medium bg-gray-100 rounded-md focus:border-0 focus:outline-0 w-[300px] placeholder:font-medium focus:border-b-2 focus:border-green-500"
              value={searchText}
              onChange={(e) => {
                setSearchText(e.target.value);
              }}
            />

```
```
  const searchInput = screen.getByTestId('searchInput');
```
- can input using into search text
```
  fireEvent.change(searchInput, { target: { value: 'burger' } });
```
- Where  { target: { value: 'burger' } } is `e.traget.value` over above search card

## complete code below 

```
// * Integration Testing - Testing Search Feature => which includes many components

import { fireEvent, render, screen } from '@testing-library/react';
import Body from '../Body';
import MOCK_DATA from '../mocks/mockResListData.json';
import { act } from 'react-dom/test-utils';
import { BrowserRouter } from 'react-router-dom';
import '@testing-library/jest-dom';
```
- fake call
```
global.fetch = jest.fn(() => {
  return Promise.resolve({
    json: () => {
      return Promise.resolve(MOCK_DATA);
    },
  });
});
```
- Render
```
it('should search ResList for burger text input', async () => {
  await act(async () =>
    render(
      <BrowserRouter>
        <Body />
      </BrowserRouter>
    )
  );
```

- get by testID all restuarant rendered
```
  const cardsBeforeSearch = screen.getAllByTestId('resCard');
```
- Resturancard Return jsut put TESTID
```
  <div
      data-testid="resCard"
      className="m-4 p-4 w-[250px] bg-gray-100 rounded-lg hover:shadow-md hover:bg-gray-200 transition-all "
    >
```

- Assertion total Resturent card 20
```
  expect(cardsBeforeSearch.length).toBe(20);
```
- search for Button name 'search'
```
  const searchBtn = screen.getByRole('button', { name: 'Search' });
```
- search for Button name 'search' ref above,
```
   const searchInput = screen.getByTestId('searchInput');

  fireEvent.change(searchInput, { target: { value: 'burger' } });  //search for Burger

  fireEvent.click(searchBtn);  // click event searchBtn
```
- get by testID filter `burger` restuarant rendered
```
   const cardsAfterSearch = screen.getAllByTestId('resCard');
```
- Assertion After search Burger is 9
```
  expect(cardsAfterSearch.length).toBe(9);
});
);
```
