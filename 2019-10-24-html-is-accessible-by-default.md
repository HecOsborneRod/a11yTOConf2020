---
title: HTML is accessible by default, right?
date: 2019-10-24
---
# Old School - Gaming And Aging
- Speaker: Scott O'Hara
- Twitter: @scottohara
---

## 1. ARIA  
- https://www.w3.org/TR/core-aam-1.1/  
- http://w3c.github.io/test-results/core-aam/
- [Accessibility Tree](http://whatsock.com/training/)


## 2. CSS Provides skin deep semantics

> Sometimes CSS + HTML = semantics  

### Examples: 
	- Responsive Tables.
	- List styles (ol & ul are announced the same way)
	- Css visibility: hidden and display: none, remove elements from semantics
	- Display: contents (removes all the a11y mappings assigned to it)

## 3. HTML 
Semantics, are really important for developers and robots that browse the site

### Link
`<a href="….">`  
You can't truly transform an anchor link into a button, without a lot of changes. For instance, there are difference when you Right Click in a button or a link.

You need to override the accessibility map of the link.

### Images
`<img src="…." alt="…."/>`  
You can't undo an image.  
You could add a role via ARIA, however it's not the most accurate way. It doesn't translate well.


### Conditional Semantics
- `<section>`
- `<header>`
- `<footer>`

All of these have the same semantics as a `<div>`

Sections should always have a role and label, watch out, it creates a landmark, we don't want to many landmarks messing with the landmark navigation.

### Undead Semantics
- `<menu>`
- `<hgroup>`

`<menu>` is no longer being supported by Browsers as spected.
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu#Browser_compatibility

 
## 4. Semantic "accessible html" can be misused to make inaccessible user experiences
- Title attribute.
- Be careful with autofocus and focus traps.
- Video autoplay is a no-no, browser like safari and chrome have removed it.
- Anchor tag that wraps highly structured content.
	
	
## What do we do?
- We teach and write
- We can get involved in writing standards
- We can report bugs, and call BS that don't match reality
	
