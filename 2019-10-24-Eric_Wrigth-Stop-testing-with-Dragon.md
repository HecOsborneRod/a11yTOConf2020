# Stop Testing with Dragon
Speaker: Eric Wright  
Twitter: [@ewaccess](http://www.twitter.com/ewaccess)

Note: During this notes AT refers to: Assistive Technology

## What's Dragon
Dragon -> AT to replace the keyboard for input.
[Insert link here]

## Mozilla Common Voice Project

> "Most speech databases are trained with an overrepresentation of certain demographics which results in a **bias towards male and white and middle class**. Accents and dialecs tend to be underrepresented in training datasets. Many machines **struggle with understanding female voices or voices of elderly people**" - Kelly Davis, Head of Machine Learning , Mozilla

Mozila Common Voice Project isinviting people to dictate with their own voice to increase / fix the training dataset  
[https://voice.mozilla.org/en](https://voice.mozilla.org/en)


## Close Button
Now image if we have a close button with an X as text  
`<button aria-label="Close">X</button>`  
Screen reader announces this as "Close" (thanks to the aria label).  
Using Dragon, the user can say: 
- "Click close" [aria-label]
- "Click (letter) X" [content]
- "Click (letter) x-ray" [content]
- "Click button" [element type]

In Dragon, `aria-label` adds to the content. 
Speech recognition requires a role


## Naming a Ridiculous
```
<a href="https://en.wikipeidia.org/wiki/Yes_(band)">
    <img src="https://upload/wikimedia.org/wikipedia/commons/5/51/Green-checkmark.svg title="Correct!" alt="Yes!" aria-label="System requirements met" aria-labelledby="nope/>
</a>
<span class="hidden" id="nope">ridiculous</span>
```

Screen reader announces:
Ridiculous. [aria-labelledby] Link graphic [roles]

As Dragon user I can say:
- "Click correct" [title]
- "Click yes" [alt]
- "Click requirements" [aria-label]
- "Click link" [but only if it's styled / looks like a link]
- But I can't say "Click ridiculous"

## Wrapped labels
`<label>Name: <input type="text"/></label>`  
This won't work on Dragon, even though it's perfect HTML.


## Things I can't use with Dragon
- Accessible names
- HTML5 input types
- Wrapped Labels
- Roles that don't look like what they are (link / button)
- Most ARIA labelling techniques
- Any browser besides Chromium or IE 11

## Modal Close Button
`<button aria-label="Close">X</button>`
What I see: A close button
What I say: press ESC button

## Conclusion
How would you design for a keyboard user who is not pressing anything?

- Give a visual indicator
- Give a tab order without any surprises


