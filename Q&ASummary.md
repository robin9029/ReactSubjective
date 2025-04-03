

### **1) HTML**  
Q. - **HTML?** → Layout of web pages.  
- **HTML Layout?** → Header, footer, head, title.  
- **Tags in HTML?** → Determine the content structure (`h1` is highest, `h6` is lowest).  

Q. - **What is `<!DOCTYPE>`?**  
  - It tells the **browser** what version of HTML to expect.  
  - Modern HTML uses:  
    ```html
    <!DOCTYPE html>
    ```
  - **Older versions:**  
    - HTML 4.01 Transitional:  
      ```html
      <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
      ```
    - HTML5 is more **flexible** and does not require a strict DOCTYPE declaration.  
Q. **Difference Between `<script>`, `<script async>`, and `<script defer>`**:
   - `<script>`: Executes immediately when the browser encounters the script tag.
   - `<script async>`: Downloads the script asynchronously and executes it as soon as it's ready.
   - `<script defer>`: Downloads the script asynchronously but waits until the HTML document has been parsed before executing it.

Q. **What is `dataSet` Attributes in HTML?**:
   - Used to store custom data attributes within HTML elements. Example:
     ```html
     <a href="#" data-name="ravi"></a>
     ```

Q. **What is `srcset` in Images?**:
   - Allows specifying multiple images with different resolutions or sizes for responsive design. Example:
     ```html
     <img src="image-default.jpg" srcset="image-500.jpg 500w, image-800.jpg 800w" />
     ```
Q. **Section vs Div (Semantic):**  
   - `<section>`: A semantic element used for grouping related content with a clear meaning.  
   - `<div>`: A non-semantic element used as a generic container without any specific meaning.

Q. **What is a Pseudo-Element?**  
   - A CSS selector used to style specific parts of an element.  
   - Examples: `::before`, `::after`, `::first-letter`.  
   - Example:
     ```css
     p::first-letter {
         font-size: 2em;
         color: red;
     }
     ```

Q. **HTML vs HTTPS (COROS)**:
   - **HTML**: Standard markup language for creating web pages.
   - **HTTPS (Hypertext Transfer Protocol Secure)**: An internet communication protocol that ensures secure data transfer using encryption.

Q. **Semantic vs Non-Semantic Elements**:
   - **Semantic Elements**: Convey meaning (e.g., `<header>`, `<footer>`, `<article>`).
   - **Non-Semantic Elements**: Do not convey meaning (e.g., `<div>`, `<span>`).
Q. **How much time required to convert wireframe to HTML code?**


### **2) CSS**  
- **Strong vs Bold?** → `strong` emphasizes importance, `bold` is for highlighting.  
- **Types of CSS?** → External, inline, internal.
- **Position attributes?**  
  - `absolute`: Position relative to the nearest positioned (non-static) ancestor.  
  - `fixed`: Stays fixed relative to the viewport.  
  - `relative`: Moves based on its normal document flow.  
- **Flexbox?** → Helps make pages responsive.  
- **`display: none` vs `visibility: hidden`?**  
  - `display: none`: Removes the element from the DOM.  
  - `visibility: hidden`: Hides the element but keeps its space.
- **CSS vs. CSS3**  
  | Feature | CSS | CSS3 |
  |---------|-----|------|
  | **Modularization** | Single large specification | Split into **modules** for better organization |
  | **Animations** | No built-in animation support | `@keyframes`, `animation` property |
  | **Selectors** | Basic selectors | New selectors: `:nth-child()`, `:not()`, etc. |
  | **Box Model** | Basic box model | `box-sizing: border-box;` to include padding and border |

- **Box Sizing in CSS**  
  - Controls **how width & height are calculated**:  
    ```css
    box-sizing: border-box; /* Includes padding and border inside the element size */
    ```
- **How to add CSS and JavaScript globally in React JS?**  
  - Using the public folder (`styles.css` in the CSS directory and `app.js` in the JS directory).  
  - Importing CSS inside `index.html` (`<link>` in `<head>`) or via `import * ./src/styles/global.css`.  
  - Importing JavaScript using `<script>` inside `index.html` or using `react-script-tag`.
2. Semantic tag in HTML: Have meaningful names and easily readable, e.g., `header`, `footer`, `vertical`.  
3. BOX model: How elements on the webpage can be rendered & calculated (content, padding, border, margin [MBPC]).  
   - Increase space between two elements: Margin.  
   - Content of an element with a border: Padding.  
4. Flexbox: Making the page responsive.  
5. Pseudo classes (`:first-child`, `:hover`) and Pseudo elements (`<p>::first-letter`).  
   - [Documentation Link](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements).  
   - Pseudo classes: Specific to state.  
   - Pseudo elements: Add new HTML elements.
 8. Styling approaches:
   - Using Bootstrap, CSS, Sass, Less, and Material UI.
 
5. **Visibility**:
   - `visibility: none`: Does not take space.
   - `visibility: hidden`: Takes space.

6. **Margin vs Padding**:
   - **Margin**: Space around the element.
   - **Padding**: Space inside the element (between content and border).
12. **Responsive Design with Media Queries:**  
   - Example:
     ```css
     @media (max-width: 768px) {
         .container {
             display: block;
         }
     }
     ```
- **Display fetched data in CSS cards**:
  Example CSS for styling:
  ```css
  .card {
      border: 1px solid #ccc;
      padding: 20px;
      margin: 10px;
      box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
  }
  ```
  7. **What is Box Model?**:
   - Describes the structure of HTML elements, including:
     - Content.
     - Padding (space between content and border).
     - Border (outer layer surrounding the padding).
     - Margin (space outside the border).
    
  8. **Text Centering**:
   - Horizontal centering:
     ```css
     text-align: center;
     ```
   - Vertical and horizontal centering:
     ```css
     display: flex;
     justify-content: center;
     align-items: center;
     height: 100vh;
     ```

9. **Flexbox**:
   - Layout for aligning items easily:
     ```css
     display: flex;
     justify-content: space-between;
     align-items: center;
     ```
3. **EM vs REM:**  
   - `EM`: Relative to the font-size of its parent.  
   - `REM`: Relative to the font-size of the root (`html`) element, typically 16px by default.

4. **Box Model:**  
   - Describes the structure of elements in CSS:
     - Content.
     - Padding (space inside the border).
     - Border.
     - Margin (space outside the border).
2. **CSS Libraries**:
   - **Bootstrap**: A popular framework for responsive design, offering pre-designed components like buttons, grids, and forms.
   - **Tailwind CSS**: A utility-first CSS framework that allows developers to build custom designs directly in HTML using predefined classes.

3. **Accessibility in CSS**:
   - CSS can enhance accessibility by:
     - Providing visual cues (e.g., focus outlines for keyboard navigation).
     - Improving readability (e.g., high contrast colors for text).
     - Supporting assistive technologies (e.g., ARIA roles and attributes).
3. **CSS Grid vs Flexbox**:
   - **Grid**: Two-dimensional layout (rows and columns).
   - **Flexbox**: One-dimensional layout (row or column).  
   - Example:
     ```css
     /* Flexbox */
     .container {
         display: flex;
         justify-content: center;
         align-items: center;
     }

     /* Grid */
     .grid-container {
         display: grid;
         grid-template-columns: repeat(3, 1fr);
         grid-gap: 10px;
     }
     ```

1. **Pseudo Class**:
   - Applies styles to elements based on their state:
     ```css
     a:hover {
         color: red;
     }
     ```

2. **Specificity**:
   - **Order of Importance**: Inline styles > ID selectors > Class selectors > Element selectors.
   - Example:
     ```html
     <div id="unique" class="class" style="color: red;">Text</div>
     ```

3. **CSS Pre-Processors**:
   - **Example with Variables**:
     ```scss
     $primary-color: #3498db;

     .button {
         background-color: $primary-color;
     }
     ```

4. **Display `none` vs Invisible**:
   - **`display: none;`**: Element is removed from layout.
   - **`visibility: hidden;`**: Element remains in layout but is invisible.

5. **Flexbox vs Grid**:
   - **Flexbox**: Single-direction layout (row or column).
   - **Grid**: Two-dimensional layout (rows and columns).

