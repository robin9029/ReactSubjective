Html css: 

What is semantic ? 
Examples of non-semantic elements: <div> and <span> - Tells nothing about its content.
			styling or structural purposes, no specific meaning 
Examples of semantic elements: <form>, <table>, and <article> ,<header>- Clearly defines its content.
			meaning to both the browser and the developer- Improved SEO,Better Maintainability

semantic Logical meaning : 
1.What are sematic tags? -Meaning fun name eg- form,table ,article 
2.Position relative and postion absolute: Relative means: relative to its position & absolute : realtaive to parent/ansistor 
	https://www.w3schools.com/css/css_positioning.asp
3.What is flexbox: 1D layout System- create row or column in axis layout, display properties , design layout very easly , justify content, 
4.What is boxModel: by default show out item, every element is box - content ,padding, border,margin
       https://www.w3schools.com/css/css_boxmodel.asp. [MB likes  PC ]=== [M->B->P->C]

5.What is Eventloop? Its runtime Module present in -JS engine checks, call stack and callback queue - if there is callback function is waiting - check for call stack if it is free, then move this  callback to call stack
5.1) which executes 1st callback-promise , setimeout :  promise 
6.What is DOM: whatever response we receives from backend - it will become converted into DOM 
7. Browser side storage ? Local,cache,browser ,session - data will be reset with close of screen 
8. external, internal, inline : which is more priority : inline 
9. have you worked on grid system in css


https://www.youtube.com/watch?v=xRD0pkTJ-Zg


Learn basic css: https://www.youtube.com/watch?v=HaVBMaP3EkE

1) Image responsive 

<div class="image-container">
  <img src="desktop-image.jpg" alt="Desktop Image" class="desktop-image">
  <img src="mobile-image.jpg" alt="Mobile Image" class="mobile-image">
</div>


.image-container {
  position: relative;
}

.desktop-image,
.mobile-image {
  display: none;
}

@media (min-width: 768px) {
  .desktop-image {
    display: block;
  }
}

@media (max-width: 767px) {
  .mobile-image {
    display: block;
  }
}

2)
<!--  Create a form username  & password form 
add div to form and background color above 768 it should be width 50%
and below 768 it should be 100% -->

HTML:
<link rel="stylesheet" href="./index.css">
<div class="Parent">
<form >
  <label for="userName"> UserName: </label>
  <input type="text" class="userName" name="username" value=""/>
  <label for="password">Password: </label>
  <input type="password" class="password" name="password" value=""/>
  <input type="submit" value="submit" >
</form>
</div>



CSS
h1,
h2 {
  font-family: Lato;
}
.Grand {
  background-color: grey;
  height: 80vh;
  display: flex;
}

.Parent {
  background-color: red;
  margin: auto;
  justify-content: centre;
}

@media (max-width: 768px) {
  .Parent {
    width: 100%;
    height: 50vh;
  }
}
@media (min-width: 768px) {
  .Parent {
    width: 50%;
    height: 50vh;
  }
}

3) flex property is used to create flexible layouts within a container
Flex-grow,flex-shrink,flex-basis initial size of item before it is disturbed 


4)HTML Accessibility - Semantic -Button 
		Non-Sementic -Div
5 HTML & CSS
Difference between innerHTML & appendChild

innerHTML = Directly pass the complete HTML Element
const container = document.getElementById('app')
container.innerHTML= '<h3>This is InnerHTML </h3>'

appendChild: create first element and keep appending and 
const container4 = document.getElementById('app')
const p = document.createElement(‘p’)
p.textContent = 'This is AppendChild'
container4.appendChild(p)

6  Inline and block element
Inline - whatever is required that much space - button ,Img,<a>,span
Block- consume full width complete  <div>, <p>.

7) External<Internal< Inline 
Inline css <div style="color: red; font-size: 20px;">This is a red text with font size 20px.</div>
Internal css 
<!DOCTYPE html>
<html>
<head>
  <title>Internal CSS Example</title>
  <style>
    body {
      background-color: #f1f1f1;
      font-family: Arial, sans-serif;
    }

    h1 {
      color: blue;
      text-align: center;
    }

    p {
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h1>Welcome to My Website</h1>
  <p>This is a paragraph with some text.</p

8)Types of CSS selectors in CSS
1. Type Selector: Targets elements based on their HTML tag name. For example, h1 selects all <h1> elements.
2. Class Selector: Targets elements based on their class attribute. For example, .my-class selects all elements with class="my-class".
3. ID Selector: Targets a specific element based on its ID attribute. For example, #my-id selects the element with id="my-id".
4. Attribute Selector: Targets elements based on their attribute values. For example, [type="submit"] selects all elements with type="submit".
5. Universal Selector: Targets all elements in the document. For example, * selects all elements.
6. Descendant Selector: Targets elements that are descendants of another element. For example, ul li selects all <li> elements that are descendants of a <ul> element.
7. Child Selector: Targets elements that are direct children of another element. For example, ul > li selects all <li> elements that are immediate children of a <ul> element.
8. Adjacent Sibling Selector: Targets an element that is the next sibling of another element. For example, h1 + p selects the <p> element that comes immediately after an <h1> element.
9. General Sibling Selector: Targets elements that are siblings of another element. For example, h1 ~ p selects all <p> elements that are siblings of an <h1> element.

### 9) Specificity Hierarchy
Every CSS selector has its place in the specificity hierarchy.
There are four categories which define the specificity level of a selector:
1. Inline styles - Example: <h1 style="color: pink;">
2. IDs - Example: #navbar
3. Classes, pseudo-classes, attribute selectors - Example: .test, :hover, [href]
4. Elements and pseudo-elements - Example: h1, ::before

10)Css Floating vs Positioning 
CSS Floating is used to position elements horizontally on a webpage, allowing other content to flow around them

.float-left {
  float: left;
  margin-right: 10px; /* Adds some space between floated element and surrounding content */
}

.float-right {
  float: right;
  margin-left: 10px; /* Adds some space between floated element and surrounding content */
}

Positioning: CSS Positioning is used to precisely position elements on a webpage.

.container {
  position: relative;
}

.absolute-positioned {
  position: absolute;
  top: 50px;
  left: 50px;
}

https://www.youtube.com/watch?v=ecZjJPBkgSs

11 SVG- scalable vector Graphic - create circle 
12  CSS Reset vs Normalize css

 aims to reset or remove all default styles
body,
h1,
p,
ul,
li {
  margin: 0;
  padding: 0;
}

Normalize css: more comprehensive approach that aims to normalize or establish consistent styles across different browsers.
Normalise across Browsers
<link rel="stylesheet" href="normalize.css">

13 Flexbox vs CSS Grid:
Flexbox: 1D
https://www.w3schools.com/css/css3_flexbox.asp

CSS Grid: 2d 
https://www.w3schools.com/css/css_grid.asp

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Relationship_of_grid_layout_with_other_layout_methods



14: Difference between semantic and non-semantic elements
https://www.geeksforgeeks.org/difference-between-semantic-and-non-semantic-elements/
Semantic elements	Non-Semantic elements
They have meaning	They don’t have meaning
They describe how the content within them is supposed to behave	They can contain anything
They have specific attributes for their structure	The ‘class’ attribute can be used to work with their structure
Table, section, form header, footer	Span div

Q. sudo class vs sudo 
Q. Service worker blind people
Q. when to use DIv & article & section 
Q. BOM 
Q. 
