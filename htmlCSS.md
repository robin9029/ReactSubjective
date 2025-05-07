## CSS selector
![Screenshot 2025-05-07 at 10 51 37 PM](https://github.com/user-attachments/assets/63db02d8-4c9a-4790-8a25-1cdaa1dc811c)

## Class and ID Selectors ?
class- use .DOT selector , can be have same name multiple time 
ID - use # selector, can't be have same name multiple time  

suppose you have same styles need to be implemented inside ordered list, you can mention same class name mulitple times 
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
aside {
  background-color: #f7f7f7;
  border-top: 5px solid #1098ad;
  border-bottom: 5px solid #1098ad;
}
