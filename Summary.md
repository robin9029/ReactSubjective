# EP1- INCEPTION
## CDN Links for React
````
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
````

## Q: html how to put h1 in root tag
1) JAVSCRIPT
 
```
<div id="root">     
    </div>
    <script>
        const h1tag = document.createElement("h1")
        h1tag.innerHTML= "Hello World ";
        const root =document.getElementById("root")
        root.append(h1tag)
    </script>
```
2) React
Same thing can be do via React 
 ```
<div id="root">
      <h1>This is Ravi here </h1>.  
							                      
    </div>
// html load this message and once react render it will replace it
// react can work only on particular root and rest it will amends 
```
```
<div id =‘NewRoot’>
  <h1>This is new Ravi here </h1> 
    </div>
// react can work only on particular root and rest it will apends that’s why its library  
```
```
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script>
      const ele = React.createElement("h1", {}, "Hello world Program");   //Object 
      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(ele);
    </script>
```
#### React.createElement("h1", {}, "Hello world Program");   //it create Object
####  root.render(ele) : take react element/which is Object (h1). 
Convert it into h1 tag  which understand by Browser and
put it into the ROOT  

# EP2,3

## Q:npm init - initialises ?
 name, author, project name, test, licence etc 
#### Package.json - is configuration for NPM , keeps track of package we are using`(Approx)`
#### Package-lock.json- keeps lock of track of `(exact) version` is installed 
 
#### Package-lock.json
```
"integrity": "sha512-FLNI5OrZxymGf/Yln0E/kjnGn5sdkQAxW7pQVdtuM+5VeN75yibJRjsSGv88PvJ+KvpD2ANgiIJo1RufmoPcww==",
````
So my code is working local but not Prod because of versions , So integrity hash value to use 

if you have both these package - you can recreate all the node modules since it has all the details of all the packages 
So if you push code to gitlab, just do npm install it will provide you with the dependency of Package in node_modules 

## Q: `npm install -D parcel`- D is DEV
## Q: Versions 
`”^2.13.3"` automatically upgrade to minor - its advisable `[caret]`

`“~2.13.3" ` automatically upgrade to major update not advisable`[tilda]` 

## Q:`node_modules`:- DB which has so many packages
## Q: `Parcel` : https://parceljs.org/

- Creates build 
- Local server 
- HMR - Automatically refreshing HMR = Hot Module Replacement - exchanges, adds, or removes modules while an application is running, without a full reload
and some of more cool features of Parcel are:
- File Watching Algorithm - written in C++ keep tracks of File
- Faster build because of caches 
- Image optimisation 
- Magnification - bundling 
- Compress 
- Consistent hasing 
- Code splitting 
- Differential bundling : provide different bundling to support different browser - chrome/firefox explorer older version of Browser
- Diagnostic - on error 
- Error handling - provide suggestion 
- https 
- Tree shaking ALGO - remove unused code for you - eg from module you are using only very few functionality , parcel remove unused code tree shaking 
- Different Dev and prod Bundlers 
- So parcel is hosting our app and on port 1234

`npx parcel index.html` npx- is to execute the package 

This will build the Development and put your code in Dist folder 

`Whenever changes it will come from - Dist to UI`

Parcel will HMR (Hot modules refresh ) Automatically refreshing , minify and put into the Dist

#### Production Build `npx parcel build index.html` 

## Q:type="module"  will include modules from node modules 

  ```
<script type="module" src="./App.js">
```
## Q:browserslist: https://browserslist.dev/
allows to configure our APP which	 will support what all version of Browser will support inside package.json 

## Q:Babel- transpiler, compiler  https://babeljs.io/

- JSX- is not html inside javascript, its like html/xml `its different syntax`
- JSX - is transpiler before it reaches the JS ,who does ? `-Parcel-> Babel` 
- JSX => React.createElement => ReactElement-`JS Object` => HTMLElement(render) 
- Javascript = can be written in `{}`


- Both below are same 
```
const xmlHeading = <h1 className="heading" > Namsate Dev 2</h1> 
```

```
const xmlHeading2 = (<h1 className="heading" >
                     Namsate Dev 2
                     </h1> )
```

- JSX - prevent cross site attack and it sentizes 
You JSX is after all Javascript 

## Q: Component - functional 
- starts with Capital letter 
- Javascript function which returns a JSX or ReactElement 
```
root.render(xmlHeading);
root.render(<h1 id="heading" > Namsate Dev 3</h1>);
```

how to pass functional component in render using wrapper </>
```
root.render(<HeadingComponent/>)
```

## Q:  component composition 
- Once component is called inside another and then render
## Q: how to pass React Element in Functional component 
- using '{}'
- You can use or write complete javascript code inside {}

  ![download1](https://github.com/user-attachments/assets/49cc38df-9523-47bd-9412-1a1dca7bb0a5)

# EP4 -key,config driven UI,MAP,function,Props

## Q.you can provide inline style in JSX using  javascript object {}
```
const styleComponent= {
  backgroundColor:'#f0f0f0'
}
const RestaurantCard = () => {
  return (<div className="res-card" style={styleComponent}>
    <h3> Meghna Foods</h3></div>)  ;
};
```
## Q: Config Driven UI- controlling your Ui using Data 
- Ui is driven by `Config like Data`, you change the place all the display are same like eg-  `AMAZON-UK,India,US`
- Swiggy - for Delhi offers are different than Bangalore than Sahibganj- no offer (so if Data is comes where it doest allow offer for Sahibganj )
- If you want to display Delhi- red,Bangalore- Brown, Sahibganj-Green just pass colour based on location -
- Restaurent - provide VEG,Non-VEG
- UI Layer, Data Layer  `what data is coming based on that we build UI' - This is called Config Driven UI
 
## Q:props ?
- are argument to function 
- Props is properties 
- Props are javascript Object 

## Q: what happens if you don’t provide key to map/LOOP/ListItem what happens ?
- If new element/restaurant card came react re-render all 
- if you give Unique key , reacts knows what keys new element comes and only re render only new one - improves performance 
- REACT uniquely identifies new element 
```
<div className="res-container">
       {resList.map(restaurant =>(<RestaurantCard key ={restaurant.data.id} resData ={restaurant}/> ))}
      </div>
```
- Its ok to use Index but its not recommended 
```
{resList.map((restaurant, index) =>(<RestaurantCard key ={index} resData ={restaurant}/> ))}
```

# EP5 hook, file structure, Import/export 

## Q. When data changes my UI layer not changed why ? DOM manipulation not happening 
- Updating DOM or DOM manipulation or changes in Data my UI also changes , efficient DOM manipulation 
- As soon as my state Variable  of data changes using SetState my UI  - react will re-render the Components
Means you changed the data - `it refresh page - re-render` (refresh page again )
- Render: calling module/component 
- Whenever state variable changes - React triggers reconciliation process and re-render 

## Q. Hooks ?
- it is normal javascript function with inbuilt utility features provided by React
- It keeps your data Layer and UI layer in synch
- JS Utility function 

- Eg. `USESTATE`: it is used to create localSTATE inside your Function 

```
const [listOfResturant] = useState([]). Define variable it return array 
const [listOfResturant, useListOfResturant] = useState(data) 
```

- Or 
```
Const are =useState(data). //it return array 
const [listOfResturant, useListOfResturant] = arr. //array Structure 
```
- example filtering based on rating 
```
<button
          className="filter-btn"
          onClick={() => {  
            const listOfResturantUpdated= listOfResturant.filter(res=> res.data.avgRating>4)
            useListOfResturant(listOfResturantUpdated)}>
          Top Rated Resturant
        </button>
```
- The Moments you call useListOfResturant, you are updating the listOfResturant(State ) , React Re-render (Refresh page )
#### when you call useListOfResturant to update 
 const listOfResturant  , React  changes to `new variable listOfResturant` as `undefined`  &  update value useListOfResturant(listOfResturantUpdated)

## Q. What is Virtual DOM & Reconciallation or React Fibre (after REACT16)
- Virtual DOM: is replica of DOM
- its an ReactElement or
- its `Javascript representation of HTML` as  `Object` or OBJECT representation oF UI 
- Eg nested DIV 

## Q: Reconciallation Algo/ Process ? 
- Suppose starting we have 7-RestaurantCard, same in Virtual DOM
- Now once you filter based on rating>4  we have 4-RestaurantCard
- Algo compares `Previous_Virtual_DOM`(Previous_OBJECT) & `current_Virtual_DOM`(Current_OBJECT) 
- If finds changes then update DOM 
- Actually React doesn’t work on Html - DIV its finds better way like `Javascript Object` and see the changes in Object which makes 
Manipulation fast 
- It does not touches DOM

## Q: Why react is FAST ?
- Efficient DOM manipulation ,it is Virtual DOM, `it can find out the DIV and updates`
- ACDlite GitHub react Fiber  : https://github.com/acdlite/react-fiber-architecture


# EP6 -API call,UseEffect
## Q. monolithic vs microservices 
microservices
	Single responsibility principle 
	Seperation of concern 

## Q. API calls
- 1st Approach `Load->API call(wait till receive data) -> render`
- 2nd Load->Render(Skeleton ) -> API call -> Re-render(with data)

##### React approach - because it will give better user experience : 2 render is ok since render mechanism is fast 

## Q: what is shemer uI- till the data fetch you show fake cards
## Q: fetch api - browser api 
```
fetch('url') // api for the get request
    .then(response => response.json())
    .then(data => console.log(data));
```
OR
```
 async function getRestaurant to fetch Swiggy API data
  async function getRestaurants() {
    const data = await fetch(
      "Swiggy_API_URL"
    );
    const json = await data.json();
    // we get the Swiggy API data in json format
    console.log(json);
  }
 ```
