# Cross Screen Reader Bugs & Where To Find Them
Speaker: Weston Thayer  
Twitter: [@WestonThayer5](https://twitter.com/WestonThayer5)

- Popular Screen Reader 
    - NVDA
    - JAWS
    - Voice Over
    - Talk back (Android)
- Screen readers, there not agreed upon certification. Each company defines their own thing to do.
- Two screen readers can read the exact same UI, and mention different things
- Each SR has their own navigation paradigm (keyboard keys)
- CSS `text-transform: uppercase` wont be read by SR
- The a11y Tech Stack
    - HTML
    - Browser
    - OS (MSAA, IA2, UIA, AX, NSAccessibility)
    - AT
- When trying to find bugs, validate each layer on the stack

## text-transform: uppercase
- Search MDN text-transform
- Accessibility Inspector (tool that comes with Xcode)
- Mac OS exposes the content all capitalized
- Inspect  (Windows)
    - inspect.exe https://docs.microsoft.com/en-us/windows/win32/winauto/inspect-objects
    - Microsoft Accessibility Insights for Windows is another great tool https://accessibilityinsights.io/docs/en/windows/overview/

- Exposes the text correctly (non capitalized)

## Custom Controls
- Sometimes default HTML controls are not enough for accessibility
- Custom controls might have "bugs" with keyboard interaction
- How to understand what's happening


## Custom Selects
- Not easy to build
- Try to use already created pattern

## Emerging overlook HTML5
- input type=color 
- input type=date
- With the new and shiny or old and dusty, chances are that Screen Reader might not support your html code

## How to fix them? 
- Wait, it might be possible to add a bug in the Software (Screen Reader / Browser)
- Simplify your code
- Start with examples & experiment
    - Check [WAI-ARIA practices guide](https://www.w3.org/TR/wai-aria-practices-1.1/) for code examples

"Two screen readers can read the exact same UI, and mention different things" 
@WestonThayer5 #a11yTOConf
Screen readers, there not agreed upon certification


## Resources
- Fun fact, the VO bug was fixed last week https://bugs.webkit.org/show_bug.cgi?id=204049
- [a11ysupport](http://a11ysupport.io) is such a great resource, kind of like canIuse for screen readers.