# 1. Redux- is Central state Managenemnt 

![diapatch](https://github.com/user-attachments/assets/63e6bacc-fb31-41d9-8b28-aaf40b55a172)


			   
### COMPONET - 
- subscribes to Central store
- want to change STORE call reducer
- using dispatch Action(Type,payload) 
### Dispatch
### Reducer
- JS function which actually changes the State
- based on action.Type-ADD_TO_CART & Action.payload
   
1. Reduer is having actual code to update passed in Store
```
 const store = createStore(
             reducer,
            window.__REDUX_DEVTOOLS_EXTENSION__ )
   
```
2.  <Counter> is View Layer having Store because it called by 
    ```
    <Provider store = {store}>
        <App />   // calls <Counter>
    </Provider>
    ```
3. when user click on increment it actually try to find where increment Action is defined and calls
```
   /CONTAINER/counterContainer.js 
    increment: () => dispatch(increment()),
```
5.  dispatch(increment()) calls ACTIONS to identify what actions increment function & return  `INCREMENT`
    ```
    export function increment() { return {type: 'INCREMENT'} }
    ```
6. once Dispatch recieve Actons increment:`INCREMENT` means user is calling for INCREMNT Action  
   now call reducer to update REDUX state  where `Action:INCREMENT` | reducer is available in APP -Store
   ```
   const reducer = (state = 0, action) => 
         { switch (action.type) {
           case 'INCREMENT': return state + 1}
   ```
 8. returned with updated state 
    return state + 1

#### 0.Reducer passed to APP inside store- >pure functions
```
/reducer/index.js
initialState= 0;

const reducer = (state = initialState, action) => {
    switch (action.type) {
       case 'INCREMENT': return state + 1
       case 'DECREMENT': return state - 1
       case 'RESET' : return 0 
       default: return state
    }
 }
 export default reducer;
```
#### 1. Index calls ->APP which has Store(Reducer)
```
/index.js
import React from 'react'
import { render } from 'react-dom'
import { Provider } from 'react-redux'
import { createStore } from 'redux';
import reducer from '../src/reducer/index'
import App from '../src/App'
import './index.css';

const store = createStore(
   reducer,
   window.__REDUX_DEVTOOLS_EXTENSION__ && 
   window.__REDUX_DEVTOOLS_EXTENSION__()
)
render(
   <Provider store = {store}>
      <App />
   </Provider>, document.getElementById('root')
)
```
#### 2. App calls ->Counter
```
/App.js
import React, { Component } from 'react';
import './App.css';
import Counter from '../src/component/counter';

class App extends Component {
   render() {
      return (
         <div className = "App">
            <header className = "App-header">
               <Counter/>
            </header>
         </div>
      );
   }
}
export default App;
```
#### 3. Counter- is View Layer : User clicks to update
```
/component/Counter.js
import React, { Component } from 'react';
class Counter extends Component {
   render() {
      const {counter,increment1,decrement1,reset1} = this.props;  // this is commig from /Container/countCounter.js
      return (
         <div className = "App">
            <div>{counter}</div>
            <div>
               <button onClick = {increment1}>INCREMENT BY 1</button>
            </div>
            <div>
               <button onClick = {decrement1}>DECREMENT BY 1</button>
            </div>
            <button onClick = {reset1}>RESET</button>
         </div>
      );
   }
}
export default Counter;
```
#### 4. mapStateToProps,mapDispatchToProps 
- this is connected to <Counter> and provide functions as well as increment1,counter

```
/Container/countCounter.js
import { connect } from 'react-redux'
import Counter from '../component/counter'
import { increment, decrement, reset } from '../actions';

const mapStateToProps = (state) => {
   return {
      counter: state
   };
};
const mapDispatchToProps = (dispatch) => {
   return {
      increment1: () => dispatch(increment()),   // 1) Action creator object 2)dispatch ActionOBJ to STORE
      decrement1: () => dispatch(decrement()),
      reset1: () => dispatch(reset())
   };
};

export default connect(mapStateToProps,mapDispatchToProps)(Counter)
```

# 2. ReduxToolKIT
- https://blog.logrocket.com/smarter-redux-redux-toolkit/
- Redux store is too `complicated`,`lot of packages required`,`boilerplate code`
- createSlice Object has reducer which has all(Action)
- From <Counter> just useDispatch action,  no mapping requires with state/Dispatch
#### 1.Store  
```
// store.js
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from '../features/counter/counterSlice'

export const store = configureStore({
  reducer: {
    counter: counterReducer,
  },
  })
```
#### 2.APP
```
// index.js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import { store } from './app/store';
import { Provider } from 'react-redux';

ReactDOM.render(
  <React.StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </React.StrictMode>,
  document.getElementById('root')
);
```
#### 3.createSlice Object
- sample
```
export const counterSlice = createSlice({name: 'counter',
					initialState,
					reducers: {increment: (state) => {state.value += 1;}})
```
- Exact createSlice Object
```
// counterSlice.js
import {  createSlice } from '@reduxjs/toolkit';
const initialState = {
  value: 0, // this is state 
};

// Redux Toolkit slice
export const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload;
    },
  },
  
  },
});
export const { increment, decrement, incrementByAmount } = counterSlice.actions;

export default counterSlice.reducer;
```
- The counterSlice file uses the createSlice method from RTK. This method returns an object with reducers and actions 
#### 4.Counter View Layer
```
/ Counter.js
import React, { useState } from 'react';
import { useDispatch } from 'react-redux';
import {increment,} from './counterSlice';
import styles from './Counter.module.css';
export function Counter() {
  const dispatch = useDispatch();

  return (
    <div>
      <div className={styles.row}>
        <button
          className={styles.button}
          aria-label="Increment value"
          onClick={() => dispatch(increment())}
        >
          click for Increment+
        </button>
      </div>
    </div>
  );
}
```
