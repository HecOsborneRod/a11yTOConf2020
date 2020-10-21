# Finding Root Causes
Speaker: Sarah Higley  
Twitter: [@codingchaos](https://twitter.com/codingchaos)  
[Slides](http://smhigley.github.io/slides/debugging-a11y)  

## Debugging
- The accessibility process (imagination): 
    - learn html
    - test
    - fix bugs
    - include everyone
- In reality: 
    - learn html
    - test
    - ...
    - ....
    - ....
    - what?
- Not too many resources for these cases when you get stuck
- Toolbox: 
    - Browser Dev Tools
    - Assistive Tech
    - W3C Specs (aria specs, a11y mapping)
    - Github issues

## Bugs

### Table Bug
- Inspect the table in the browser 
- Use W3C Specs to check semantics
- Use Firefox, has an accessibility inspector

## Focus
- Use Inspect Dev Tool in your browser
- Use Assistive Tech
- Use `document.activeElement` on the console to check who has focus

```
document.addEventListener('focusin', () => {
    console.log(document.activeElement);
});
```

## Voice Over should read... but reads...
- Use an Assistive Tech
- Test your pattern against native patterns
- Test against known patterns


## Accessibility on 3rd Party Tools
- Check github for a11y-related activities
- Use tool to check github repo: https://github-a11y-stats.netlify.app/
    - Example: github.com/ant-design/ant-design