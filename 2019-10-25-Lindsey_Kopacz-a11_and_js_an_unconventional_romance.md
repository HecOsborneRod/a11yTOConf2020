# a11y & JS An Unconventional Romance
Speaker: Lindsey Kopacz  
Twitter: [@LittleKope](http://www.twitter.com/LittleKope)  
Slide Deck: [https://lkopacz.github.io/ a11yTo-a11y-js-unconventional-romance/#/](https://lkopacz.github.io/a11yTo-a11y-js-unconventional-romance/#/)

## Who is Lindsey

- React Developer
- Accessibility Blogger www.a11ywithlindsey.com

## Why Do I care? 
- Learning more about CogDis, including more about mine ADHD
- Think about the jokes that we create, it's not just about HTML
- The Great Divide - CSS-Tricks [https://css-tricks.com/the-great-divide/](https://css-tricks.com/the-great-divide/)
- The idea that JS is not a11y is not an unfounded …. every application that I see immerse errors on is usability and SPA or a PWA. 
- WebAIM Million
    - Good reminder on how inaccessible sites are
    - 4 out of the 6 main categories got worse
        - Low contrast text 85.3% => 86.1%
        - Empty links 58.1% => 58.9%
        - Missing form input labels 52.8% => 53.2%
        - Empty buttons 25% => 27%

## Modal
- We want to make sure the focus to the modal once is open
- Focus Trapping, ensure the focus stays in the modal, unless you exit
- Upon close the focus should return to the place it was before
- React Modal - [https://codesandbox.io/s/optimistic-hugle-l0krn](https://codesandbox.io/s/optimistic-hugle-l0krn)

## Overall Focus Management
- Making sure the focus isn't going to visually hidden elements.
- You need to remove the tabindex if the menu is out of Screeen!
- [https://codesandbox.io/s/immutable-dew-0lpwq](https://codesandbox.io/s/immutable-dew-0lpwq)

## Using localStorage
- Don't store secure information
- Examples: Reducing Motion, High Contrast Mode
- Example: [https://codesandbox.io/s/testing-reducing-motion-76xj6](https://codesandbox.io/s/testing-reducing-motion-76xj6)
	
## Progressive Enhancement
- Adding a class that gets removed first when JavaScript loads
- Adding alternative styling if the JavaScript doesn't load
- Adding aria attributes via JavaScript, especially if it indicates interactivity
- Example: [https://lkopacz.github.io/a11yTo-a11y-js-unconventional-romance/#/12/1](https://lkopacz.github.io/a11yTo-a11y-js-unconventional-romance/#/12/1)
	

		
	
