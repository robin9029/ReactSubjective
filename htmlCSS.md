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
