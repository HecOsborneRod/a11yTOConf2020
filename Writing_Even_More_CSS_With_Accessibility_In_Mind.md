# Writing Even More CSS With Accessibility In Mind 
Speaker: Manuel Matuzović   
Twitter: [@mmatuzo](https://twitter.com/mmatuzo)  

## Progressive Enhancement
- Instead of loading thousands of lines of code, use less JS & CSS
- Only us JS if you really need it
- Layers
    - HTML
    - CSS
    - JS
- CSS has error handling in itself
- This color will work fine in any browser, the error is skipped
```
div {
    color: #FFF;
    css-is: amazing;
    background: #000;
}
```
- Clip-path demo https://codepen.io/matuzo/pen/yEYyOB
- Writing even more CSS with Accessibility in Mind, Part 1: Progressive Enhancement [https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-progressive-enhancement/](https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-progressive-enhancement/)

## Respecting User Preferences
- Font Size
    - The default font size is most browsers is 16px
    - Don't use px units! `font-size: 18px;`
    - We can use relative units `font-size: 1rem;`
    - 18px / 16px => 1.125rem
- Respect user animations' preferences
    - Accessibility for Vestibular Disorders: How My Temporary Disability Changed My Perspective [https://alistapart.com/article/accessibility-for-vestibular/](https://alistapart.com/article/accessibility-for-vestibular/)
    - It is hard to focus with too many animations
    - Use CSS to `@media (prefers-reduced-motion: reduce)`
    - Moonwalk demo [https://codepen.io/matuzo/pen/NWrWeNq?editors=1100](https://codepen.io/matuzo/pen/NWrWeNq?editors=1100)
    - Designing With Reduced Motion For Motion Sensitivities [https://www.smashingmagazine.com/2020/09/design-reduced-motion-sensitivities/](https://www.smashingmagazine.com/2020/09/design-reduced-motion-sensitivities/)
    - Defensive prefers-reduced-motion use - no motion first design [https://codepen.io/patrickhlauke/pen/YzPPdeo](https://codepen.io/patrickhlauke/pen/YzPPdeo)
    - Use CSS to `@media (prefers-reduced-motion: no-preference)` can be used to target only browsers that support animation preference
    - Scroll-behaviour demo [https://codepen.io/matuzo/pen/bGprNYo](https://codepen.io/matuzo/pen/bGprNYo)
    - Writing even more CSS with Accessibility in Mind, Part 2: Respecting user preferences [https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-user-preferences/](https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-user-preferences/)

## Improving a{}y with CSS
- explaining user interfaces
- `<a href="document.pdf" download>download file</a>`
- `a[download]::after { background-image: url('icons/download.png')}`
- Tips on Making Sure Hidden Content is Accessible (or Not!) [https://scottvinkle.me/blogs/blog/hidden-content](https://scottvinkle.me/blogs/blog/hidden-content)
- Use aria-describedby to enhance user message

## Testing  a11y
- `a11y-tests.css file https://github.com/matuzo/a11y-tests.css`
- Test a website without a mouse
- remove all colours `a11y-tests-grayscale`
```
.a11y-tests-grayscale {
    filter: grayscale(100%) !important
}

<html class="a11y-test-grayscale lang="en">
...
</html>
```
- Even better: html[lang*=" "] instead of html[lang=" "] to test for any number of spaces [https://codepen.io/matuzo/project/editor/ZyrVee](https://codepen.io/matuzo/project/editor/ZyrVee)

```css
html:not([lang]),
html[lang=" "],
html[lang=""],
html:not(:lang(en)) {
    border: 10px solid red;
}
```
- About the lang attribute and translations: The lang attribute: browsers telling lies, telling sweet little lies [https://www.matuzo.at/blog/lang-attribute/](https://www.matuzo.at/blog/lang-attribute/)
- Check for buttons
- Check for links nested inside button

## HTML Semantics
- A div not good enough as a button
- A `<button>` is much better button than a `<div>`
- CSS can affect the accessibility tree. 
- There's a but in Chrome that removes elements from a11y DOM `display: content`
- don't use `display: none` to hide checkboxes, (they will be removed from a11y tree)
- `list-style-type: none`  Voice over made a choice to remove the announcement of the element list
- "Fixing" Lists [https://www.scottohara.me/blog/2019/01/12/lists-and-safari.html](https://www.scottohara.me/blog/2019/01/12/lists-and-safari.html)
- The CSS "content" property accepts alternative text [https://www.stefanjudis.com/today-i-learned/css-content-accepts-alternative-text/](https://www.stefanjudis.com/today-i-learned/css-content-accepts-alternative-text/)
- `div::before { content: url('icons/ping.png') / "You're here."; }`
- In the meantime Adrian published “Alternative Text for CSS Generated Content” with more tests [https://adrianroselli.com/2020/10/alternative-text-for-css-generated-content.html](https://adrianroselli.com/2020/10/alternative-text-for-css-generated-content.html)

## Resources
- HTMHell [https://www.htmhell.dev/](https://www.htmhell.dev/)
- HTMHell on GitHub [https://github.com/matuzo/HTMHell](https://github.com/matuzo/HTMHell)
- a11y.css [https://ffoodd.github.io/a11y.css/](https://ffoodd.github.io/a11y.css/)
- [https://codepen.io/matuzo/pen/oNLYmXX](https://codepen.io/matuzo/pen/oNLYmXX)
- Manuel posted this link for content [https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-user-preferences/](https://www.matuzo.at/blog/writing-even-more-css-with-accessibility-in-mind-user-preferences/)
- [Writing CSS with Accessibility in Mind](https://medium.com/@matuzo/writing-css-with-accessibility-in-mind-8514a0007939)
