---
title: 
date: 2019-10-24
---
# These Aren't The SCs You're Looking For...
- Speaker: Patrick Lauke
- Twitter: [@patrick_h_lauke](http://www.twitter.com/patrick_h_lauke)
- Organization: The Paciello Group
---

How did I got started:  
- Doing a11y audits
- Advising and reviewing the work of other engineers doing audits

Far too often auditors clearly dislike something, and look a justification to fail it.

We are not lawyers (or judges)
- Evaluations should be as objective as possible
- Evaluations should be consistent

WCAG is built on the idea that Success criteria (SC) can be evaluated clearly and without ambiguity 

WCAG Sucess Criterias (SC) are often misunderstood and misinterpreted

### WCAG 2.4.6 Headings and Labels (AA)
It doesn't mandate the usage of heading and labels… only that if the page uses headings and labels, they must be descriptive. 

#### Example 1
     <input type="text">
Passes WCAG 2.4.6  
Fails WCAG 3.3.2  
Fails WCAG 4.1.2

#### Example 2
    <p class="heading1">I'm a heading</p>
    <p>First name</p>
    <input type="text">
Passes WCAG 2.4.6  
Fails WCAG 1.3.1  
Fails WCAG 4.1.2  

### WCAG 3.3.2 Labels or instructions
Doesn't mandate that labels be marked up as `<label>` it mandates that they are properly associated with form controls

    <p>First name</p>
    <input type="text">
Passes 3.3.2  
Fails 1.3.1  
Fails 4.1.2  

### WCAG 2.1.1
doesn't say anything about which keys are needed to control 

     <a href="#" onclick="…"role="button">fake button</a>
Passes 2.1.1 keyboard  
Even though it can't be activated with SPACE like any button would.


### WCAG 3.2.3 Consistent Navigation
Requires relative order of navigation (in relation to the other page components) to be consistent, nothing more.  
Doesn't mandate that navigation should be same, work the same, etc, across all pages.

### WCAG 1.3.3 Sensory Characteristics
Relates specifically to instructions … and not whether or not some sensory characteristics are used, this is covered by other SC like 1.4.1 use of color or even 1.1.1 non-text context

### WCAG Cascade of fail
    <a href="…"/> <img src="…."></a>
Fails multiple criteria… need to consistently report these but easy to forget do so.  
It would be announced as this is a LINK… nothing more. 

### "Speculative" cascade of fail
    <div>Read more</div>
Fails 2.1.1 Keyboard ... but also 4.1.2 name, role, value, and it acts as a link, also WCAG 2.4.4 link purpose (in context)?

### WCAG SCs that are vague, incomplete or lacking definition.

> WCAG 2.x is not perfect.

### Subjective interpretation
- 1.1.1 all non-text content [...] has a text alternative that server the quivlaent purpose … but what's the purpose ? 
- 1.3.1 information, structure and relationships conveyed through presentation [...] where do you draw the line ? 
- 2.4.6 headings and labels describe topic or purpose - what's the descriptive exactly?

Example:

    <div class="footer"> … </div>
Do you fail this under 1.3.1 for not using `<footer>` or `role="contentïnfo"`



### WCAG 2.4.5 Focus Visible (AA)
But what does visible mean? it's not properly defined.  
WCAG 2.1 decided not to modify WCAG 2.0 SCs, patched loopholes with more SCs

### WCAG 1.4.11 Non-text Contrast (AA)
Only applies to adjacent colours, doesn't apply to contrast between different colours used when in focus


