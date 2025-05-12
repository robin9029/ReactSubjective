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

