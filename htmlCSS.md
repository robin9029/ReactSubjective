## CSS selector
![Screenshot 2025-05-07 at 10 51 37 PM](https://github.com/user-attachments/assets/63db02d8-4c9a-4790-8a25-1cdaa1dc811c)

## Class and ID Selectors ?
- class- use .DOT selector , can be have same name multiple time 
- ID - use # selector, can't be have same name multiple time  

- suppose you have same styles need to be implemented inside ordered list, you can mention same class name mulitple times 
```html
<aside>
        <h4>Related posts</h4>
        <ul class="related">
          <li>
            <a href="#">How to Learn Web Development</a>
            <p class="related-author">By Jonas Schmedtmann</p>
          </li>
          <li>
            <a href="#">The Unknown Powers of CSS</a>
            <p class="related-author">By Jim Dillon</p>
          </li>
          <li>
            <a href="#">Why JavaScript is Awesome</a>
            <p class="related-author">By Matilda</p>
          </li>
        </ul>
      </aside>
```
### border makes solid border 

```html
<style>
p {
  border-top: 5px solid Black;
  border-bottom:5px solid black;
  padding: 20px
}
</style>
```
<img width="702" alt="Screenshot 2025-05-07 at 11 09 40 PM" src="https://github.com/user-attachments/assets/2f390785-e2dd-4ec9-b6fe-4cc4a03dbac3" />

### psudo class

```html
/* unvisited link */
a:link

/* visited link */
a:visited 

/* mouse over link */
a:hover 
/* selected link */
a:active 
```
```html
select only List item first child 
li:first-child {  
  font-weight: bold;
}


select only List item last child 
li:last-child {
  font-style: italic;
}

li:nth-child(odd) {
  /* color: red; */
}
```
###  CONFLICTING SELECTORS AND DECLARATIONS : specificity 
- if id, class and tag selector comes for <p> , how CSS applied 
![Screenshot 2025-05-08 at 12 56 37 AM](https://github.com/user-attachments/assets/4dc1f2cd-ed34-44bc-bd85-2df6db31939a)

![Screenshot 2025-05-08 at 12 56 47 AM](https://github.com/user-attachments/assets/04348008-60a4-47c4-aa40-50be47de63b6)
- if `<p class = 'first second  Last'>`
  - Class = `Last` CSS will be applied
 
### BOX models 
![Screenshot 2025-05-12 at 10 34 58 PM](https://github.com/user-attachments/assets/71ebfbac-872b-44ed-966e-41a2529e8047)
- margin: spaces between element
- padding space inside element or inside box 
- Box models behaves differently with the Bloxk and inline 
- for Inline : margin top and bottom does not apply

### Inline-Block
![Screenshot 2025-05-12 at 10 36 09 PM](https://github.com/user-attachments/assets/8edb85bd-9738-4071-b0b5-74f7b602ac02)

### Position - Relative vs absolute
- absolute: is fixed w.r.t parent conatiner & also you have to mention parent postion as relative
- Relative : is relative to view port or visible screen 
![Screenshot 2025-05-12 at 10 35 46 PM](https://github.com/user-attachments/assets/6940e9eb-d517-4cf1-b18d-abfa2e7cb124)

### FlexBOX
![Screenshot 2025-05-12 at 10 57 19 PM](https://github.com/user-attachments/assets/50b21935-0f85-4086-9853-891b3ae63e87)
![Screenshot 2025-05-12 at 10 57 32 PM](https://github.com/user-attachments/assets/f992ece7-5575-4b01-81b5-c729e104ed46)

## Grid 
![Screenshot 2025-05-12 at 10 57 41 PM](https://github.com/user-attachments/assets/9aaa383c-0150-45d9-9060-2940e0267fb8)![Screenshot 2025-05-12 at 10 57 49 PM](https://github.com/user-attachments/assets/a01b79a4-b63f-44cf-ad08-814840abb8f8)



## 🔷 1. **HTML Basics & Structure**

* `<!DOCTYPE html>` – Informs the browser about the HTML version.
* Older HTML: `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"...`
* HTML is used for layout on web pages.
* HTML Layout includes: `header`, `footer`, `head`, `title`, etc.
* Tags in HTML define elements (`<h1>` to `<h6>`) and structure of content.

---

## 🔷 2. **Semantic vs Non-Semantic HTML**

* Semantic tags: `header`, `footer`, `section`, `article` – meaningful and readable.
* Non-semantic tags: `div`, `span` – no inherent meaning.
* `<section>` vs `<div>`: Semantic vs generic.
* Difference between semantic and non-semantic: semantic = meaningful to both developer and browser.

---

## 🔷 3. **Block vs Inline Elements**

* Block elements: take full width (`<div>`, `<p>`, `<section>`)
* Inline elements: flow with text (`<a>`, `<span>`)
* `<div>` is block, `<a>` is inline.

---

## 🔷 4. **CSS Basics and Types**

* Types of CSS:

  * **Inline**
  * **Internal**
  * **External**
* Adding global CSS in React:

  * In `public/index.html`: `<link rel="stylesheet">`
  * In JS: `import './styles.css';`
* Libraries: Bootstrap, Tailwind, Material UI, Saas, Less

---

## 🔷 5. **CSS Box Model**

* Box Model = `Margin > Border > Padding > Content (MBPC)`
* `box-sizing`: includes `padding` and `border` in width/height.
* Space between elements = `margin`
* Space inside element = `padding`

---

## 🔷 6. **Flexbox & Grid**

* Flexbox:

  * 1D layout (row or column)
  * Makes layout responsive
  * `display: flex`
* Grid:

  * 2D layout (rows and columns)
  * Use when you need control over both axes
* Difference:

  * Flexbox: simpler for one-directional layouts.
  * Grid: more powerful for complex layouts.

---

## 🔷 7. **Positioning in CSS**

* `relative`: moves relative to its normal position.
* `absolute`: relative to the nearest positioned ancestor.
* `fixed`: fixed to the viewport.
* `sticky`: switches between relative and fixed based on scroll.

---

## 🔷 8. **Visibility & Display**

* `display: none`: element is removed from DOM layout.
* `visibility: hidden`: element is hidden but takes up space.
* Compared:

  * `display: none` = no space.
  * `visibility: hidden` = hidden, but space is preserved.

---

## 🔷 9. **CSS Selectors**

* `div > p`: styles only direct children `<p>` inside `<div>`
* `div p`: styles all `<p>` inside `<div>`, regardless of depth
* Example:

```html
div > p { color: red; }  // immediate child only
div p { color: red; }    // all nested <p> elements
```

---

## 🔷 10. **Pseudo-classes and Pseudo-elements**

* **Pseudo-classes**: `:hover`, `:first-child`, `:focus`
* **Pseudo-elements**: `::first-letter`, `::before`, `::after`
* Pseudo-classes relate to element states.
* Pseudo-elements add virtual elements.

---

## 🔷 11. **CSS Specificity & Priority**

* Order of priority:

  1. Inline styles (`style=""`)
  2. ID selectors (`#id`)
  3. Classes, attributes, pseudo-classes (`.class`, `:hover`)
  4. Elements and pseudo-elements (`div`, `::before`)
* Most specific rule wins.

---

## 🔷 12. **Units in CSS: rem, em, %, px**

* `rem`: relative to root font size (usually 16px)
* `em`: relative to parent element’s font size
* `%`: relative to parent element’s size
* `px`: absolute unit
* When to use:

  * `rem`: consistent scaling
  * `em`: context-aware scaling
  * `%`: responsive layouts
  * `px`: precise control

---

## 🔷 13. **Advanced HTML Attributes**

* `data-*` attributes: store custom data in elements

  * Example: `<a data-name="ravi" href="#">Link</a>`
* `srcset`: for responsive images

  * Example: `<img src="default.jpg" srcset="small.jpg 480w, large.jpg 800w">`

---

## 🔷 14. **Script Loading in HTML**

* `<script>`: blocks rendering until loaded
* `<script async>`: loads asynchronously, may execute before HTML is parsed
* `<script defer>`: loads in background, runs after HTML parsing

---

## 🔷 15. **JavaScript Events in HTML/React**

* `onBlur`: fires when an input loses focus
* Character counter example:

```html
<textarea id="text"></textarea>
<p>You've written <span id="character-count">0</span> characters.</p>
<script>
  const textarea = document.getElementById('text');
  const count = document.getElementById('character-count');
  textarea.addEventListener('input', () => {
    count.textContent = textarea.value.length;
  });
</script>
```

---

## 🔷 16. **Document vs Window in JS**

* `document`: represents the HTML DOM
* `window`: represents the browser window
* `document` is a property of `window`

---

## 🔷 17. **Miscellaneous CSS/HTML Topics**

* `strong` vs `bold`:

  * `strong`: semantically important
  * `b`: stylistically bold
* BOM (Browser Object Model): control browser components like alert, history, location, etc.
* Iframes: embed external content; can overlap UI
* Blend CSS: combining multiple stylesheets or styles logically

---

## 🔷 18. **Common Interview Questions (Summarized)**

* What is the difference between:

  * `absolute` vs `relative` positioning
  * Flexbox vs Grid
  * Inline vs block elements
  * `em` vs `rem`
  * `display: none` vs `visibility: hidden`
  * Semantic vs non-semantic HTML
  * `window` vs `document`
  * `strong` vs `b`
  * CSS specificity
  * `div > p` vs `div p`


## 🔷 19. **Types of CSS selectors in CSS**
  * Type Selector: Targets elements based on their HTML tag name. For example, h1 selects all <h1> elements.
  * Class Selector: Targets elements based on their class attribute. For example, .my-class selects all elements with class="my-class".
  * ID Selector: Targets a specific element based on its ID attribute. For example, #my-id selects the element with id="my-id".
  * Attribute Selector: Targets elements based on their attribute values. For example, [type="submit"] selects all elements with type="submit".
  * Universal Selector: Targets all elements in the document. For example, * selects all elements.
  * Descendant Selector: Targets elements that are descendants of another element. For example, ul li selects all <li> elements that are descendants of a <ul> element.
  * Child Selector: Targets elements that are direct children of another element. For example, ul > li selects all <li> elements that are immediate children of a <ul> element.
  * Adjacent Sibling Selector: Targets an element that is the next sibling of another element. For example, h1 + p selects the <p> element that comes immediately after an <h1> element.
  * General Sibling Selector: Targets elements that are siblings of another element. For example, h1 ~ p selects all <p> elements that are siblings of an <h1> element.

## 🔷 20. **Specificity Hierarchy [IICE] **
Every CSS selector has its place in the specificity hierarchy.
There are four categories which define the specificity level of a selector:
* Inline styles - `Example: <h1 style="color: pink;">`
* IDs - Example: #navbar
* Classes, pseudo-classes, attribute selectors - Example: .test, :hover, [href]
* Elements and pseudo-elements - Example: h1, ::before

