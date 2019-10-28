# Screen Readers and CSS
Speaker: CB Averitt  
Email: cb.averitt@deque.com  
Personal URL: [https://dive4cb.github.io/index.html](https://dive4cb.github.io/index.html)  

***Note:*** *During this notes AT refers to: Assistive Technology*

## Assumptions
CSS was meant for visual presentation, however it could have some impact on the audio presentation too. The experience for AT users could be affected by using different CSS properties.

Following is a list of examples and description on each of them.

### Code Examples
Code Examples and results can be found at
[https://dive4cb.github.io/index.html](https://dive4cb.github.io/index.html)


## CSS Properties
Let's see how the following rules are interpreted in CSS with a Screen Reader

--- 

### display: none
[https://dive4cb.github.io/accessible-css-display.html](https://dive4cb.github.io/accessible-css-display.html)  
- `display:none` hides the content  
- `visibility:hidden` hides the content too, but keeps the space in the browser.

--- 

### position: absolute
[https://dive4cb.github.io/accessible-css-absolute.html](https://dive4cb.github.io/accessible-css-absolute.html)  
Just because you placed an element there visually, it means that the AT user will get the same experience.

--- 

### ::before & ::after
[https://dive4cb.github.io/accessible-css-before-after.html](https://dive4cb.github.io/accessible-css-before-after.html)

    <p>
        <a href="https://www.google.com" class="gold">Select</a>
    </p>
    <p>
        <a href="https://www.google.com" class="diamond">Select</a>
    </p>

Both `::before` and `::after` content are read by every browser, however IE11 + JAWS won't be able to interpret this information. If you care about these users (as you should), an alternate solution must be found. 

---

### line-through
No mention of text strikethrough.  
Think about an eCommerce website, where the sale prices is striked through (via CSS) both prices are goint to be read without differentiation.

A better solution would be:

    - Add a hidden text, to be interpreted by the AT (use ARIA)
    - Change the labels to "Was 20$, ... Now: 10$"
    - Add a label with the discounted price Save $10

---

### Font Weight
[https://dive4cb.github.io/accessible-css-font-weight.html](https://dive4cb.github.io/accessible-css-font-weight.html)

Screen readers will read all text is read, but it will not mention any of the styles. Think about the importance of the bolded text, users of AT are not experiencing the same.

---

### Direction and unicode-bid
`direction: rtl;`

Even though the text is right to left on the screen, the AT will read them Left to right. 

---

### Font-size
[https://dive4cb.github.io/accessible-css-font-size.html](https://dive4cb.github.io/accessible-css-font-size.html#)  
If you ever use `font-size: 0` it will be read in every browser + AT Combo, however Safari + Voice Over will not read this text.

---

### Clipping
<div> with no clip

This is a common technique used to hide text outside of a box. However take into consideration that the AT willl read all the content, regardless of what's shown on screen.

---

### Word-break
It will show differently for sighted users, but it will be read as expected to AT users. 

---

### Opacity
Chaning the `opacity` property of an element, makes no difference to any broswer + AT combo. All the browsers reads the entire text.

Can you imagine if the ATs where to change the voice entonation based on the opacity of a text? (Kind of Whispering? could be cool, could be kreepy)

---

### Overflow
`overflow: hidden` vs `overflow: visible`

Result: 
All text is exposed to AT users, regardless of the browser display.

---

### List Style
`list-style: none;`  
Result: Voice over + Safari / Chrome / will not interpret this as a list. AT users won't have acces to shortcuts.

This is a property commonly used for Navigation Menus, we could do better.

