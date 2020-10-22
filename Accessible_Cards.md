# Accessible Cards
Speaker: Rian Rietveld  
Twitter: [@RianRietveld](https://twitter.com/RianRietveld)  
Slides: [slides](http://lvl.li/a11yto-2020)  
Examples: [examples](https://a11y-collective.github.io/talks/cards/index.html)

## Intro
Cards typically have
- Image
- Name
- Date
- Number of Attendees

Google Search Results Cards
- Link 
- Date
- Summary
- Collection of Links, Videos, Images

Subscribe to newsletter
- Can be considered a Cards
- Cards should contain enough information to be useful

## Elements in a Cards
- Should contain a Title and a Link (minimum)
- Optional extra fields: 
    - description
    - image
    - publishing / event date
    - meta data
        - author[s]
        - comments
        - number of comments
        - number of shares
    - ~image slider~ please don't do this
    - video
    - view more link
    - share links , like a post (you haven't read)

## What information makes you click? 
- What's really useful? it depends on your content / type of user
- Example: Playstation blog: image, title, date, author, description, number of likes, number of comments.
- Research how much data you want to display
- Don't just copy/paste a pattern
- Some people will just go away if too much info is presented (visual / non visual users)

## What are the basic requirements for a11y / usability?
- Order of things
    1. There must be a logical order from top to bottom
    2. Semantics: use Semmantic HTML5
    3. heading structure: a heading should reflect the content beneath. The heading level must make sense with the page 
    4. Zoom: must be usable / readable when user zooms in
    5. Screen reader: all info should be readable by Screen
    6. Links: should give context, avoid learn more / view more
    7. Tab order should be the same as the visual order (overall)

## Designers
- Spend time understanding what best for your user
- Do Research
- Proximity & Order: tell a story, from top to bottom
- Not everybody can see the entire screen, order should make sense
- If horizontal lines (HR) are not visible, you might miss the visual proximity! (think of screen readers)
- Read elements of your designers from top to bottom
- Start with the Heading!

### Focus Styles
- What's clickable? 
- Where am I when I use TAB / SHIFT TAB?
- Design hover style & focus style. Test !

### Let your design breathe & Flow
- How about small screens?
- How about zoom in?
- Make your design and navigation intiutive
- Don't make your users feel useless because the can't understand your design


## Developers
### Don't DIV the DOM
- Browser knows how to display the code, there's more than DIVs
- A button starts an action
- A link opens a page
- A heading is a title
- Choose the proper markup
- How to choose ?  [Use Morzilla Developer Network MDN] (https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- Take pride on the quality of your code

### Heading Level
- Talk to your designers, plan the page structure
- Don't use them to just make your test look big
- If reusing the heading (for instance in a Listing Page)

### Links & Link text quality
- Should link to the content you want your users to read
- Not everybody can use mouse!
- Make the link text understandable on its own
- For example: View deals (repeated in multiple cards in the same page) Example: [Virgin Atlantic](https://www.virginatlantic.com/)
- Read more
    - hide from visual users <a href="#">Read more <span class="sr-only"> about our favourite books</span></a>
    - Use screen-reader-text, sr-only class needs to be 1px, if not SR won't announce it
    - Use an arial-label (it will override everything inside) <a href="url" arial-label="Read more about our favourite books">Read more.</a>

### Tab order
- Should be predictable
- For WCAG, the tab order should be the same as the visual display
- **Pro Tip:** Don't use tab order


### Multiple links in the same Card
- A link for the image
- A link to the title
- A link to the read more
- It's not a WCAG violation, but it's a Screen Reader / Keyboard navigation issue.
- We can do better
- Solutions:
    - Link only on the title
        - Pros: people are drawn to link
        - Cons: user expect 
    - Hide Links 
        - tabindex="-1"
        - aria-hidden="true"
        - Use tabindex and aria-hidden together
        - Multiple targer for mouse users
        - One target for Screen Reader / Keyboard
        - Con: 
            - Not every visually impaired user is completely blind
    - Wrap an <a> around everything
        - PRO: easy
        - CON: results in a long imconprehensive link **PLEASE don't do this**
    - Use an empty <span> around the link
        - span: position: absolute, 
        - PRO: card clikable
        - CON: text not selectable
        - CON: empty element inside in card
    - Use CSS with pseudo-content (preferred)
        - `<h3 ><a>::after</a></h3 >  .h3 a ::after { position:absolute }`
        - PRO: whole wrapper clickable
        - CON: no way to select part of the text
        - NOTE: Don't add extra links inside the text!, you can move things using Z-index, but this is confusing for visual / mouse users.
- There's no one solution for this!
- Work together with your designer, collaborate!

