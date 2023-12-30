---
hide:
  - navigation
---
# CSS
## Locations for CSS
There are 3 locations where CSS can be defined:
1. Inline - CSS styles that is provided inside each HTML  element
2. Internal - CSS style that is provided as part of <head> which is applied to the entire HTML page
3. External - External CSS file which can be referenced and used by multiple HTML files.

## Types of CSS Selectors
CSS selectors can be broadly classified into:
1. Tag Selectors (like h1, p, body). Eg:
	```
	h1 {
	background: yellow;
	}
	```
2. Class Selectors (custom, user defined classes, which can be applied to multiple HTML elements). Eg:
	```
	.my-class-name {
	background: red;
	}
	```
3. ID Selectors (specific CSS which targets a single individual HTML element). Eg:
	```
	#my-id {
	background: brown;
	}
	```
	
A single HTML element can have more than 1 class defined, like below. 
`<p class="red-text highlight"></p>`
In this example, this are two CSS classes - "red-text" and "highlight". Properties of both these classes would be applied.

Most recommended/popularly used is external class selectors, which has wide reusability.

### Pseudo Class
A pseudo-class is used to define a special state of an element. For example, it can be used to style an element when a user hovers over it.

## CSS Useful Links
### Align Elements Side by Side
https://codepen.io/beau/pen/odbrRa

## Order of Priority
When a CSS property is defined in multiple places, the more specific identifier's definition would be taken. For example, when considering tag selectors (like h, p), class selectors and id selector, the id selector would be taken, as its most specific among all three.

When a selector at the same level/specificity is defined in multiple places like inline CSS, internal CSS and external CSS, inline CSS would have the most priority. Between internal CSS and external CSS, it depends on the order in which they are defined/called in the header section. If external CSS is defined first, followed by internal CSS and the specificity of the selectors are at same level, the internal CSS which is called last would over-ride what is defined by the external CSS.

Inline CSS will trump internal and external CSS, since that would be the last that is getting applied. Priority between Internal CSS or External CSS would depend on, what is applied last among these. If internal CSS is set after linking the external CSS, internal CSS would have the priority.
## Box Model
Everything in a web page is a rectangle/box.
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/e/ed/Box-model.svg)

## Display
### Display: Block 
Block display elements are those which occupy the entire horizontal width when placed. Some of the block display elements are - h1, p, div.
You can over-ride by explicitly specifying the width property for these elements, but still it will not allow other elements  to occupy the same row.

### Display: Inline
Inline display elements are opposite of block display & take only the width they actually occupy. Several elements can occupy the same row. Eg: span, a.

"Width" property has no effect on inline elements. If you have a <p> element, its width would be based on the content it internally has.

### Display: Inline-Block
This has properties with combinations of block and inline. Elements can occupy the same row as well as ability to configure the width of each element.

### Display: None vs Visibility: Hidden
Both display: none and visibility: hidden, hides the element. But when display:none is used, it is as this the element is removed/deleted and other elements move in and occupy its space. 

When visibility:hidden is used, the element is removed but the space it was occupying will be vacant and other elements would not take its place.

## Positioning
Types of positioning:
1. Static
2. Relative
3. Absolute
4. Fixed

### Position: Static
Default positioning of CSS elements. The position of the content would be based on the HTML flow/layout.

### Position: Relative
Positioning an element relative to its "static" positioning, where the static positioning is defined by the HTML layout. After specifying the position as relative, we can use the properties like top, right, bottom, left to move the HTML element from its static position. Just setting position to relative without setting values to properties like top, right, bottom, left will not have any effect on the position of the element. There is also a valid use case for this, when the child elements position is made absolute (covered in next section).

For example, to add a space of 200 px to the top of the element whose id is element-id:
`#element-id {
position: relative;
top: 200px;
}
`

One important thing to note is that, moving a position using relative property would not affect the positions of other elements in the web page. For example, if we are moving an element down by 200px, the element would now overlap with its bottom element.

### Position: Absolute
Absolute position would position the element relative to its parent element whose position is set to relative. If the parent element position is not set to relative, it will traverse to its parent, to see if that or its parent is relative and use that for absolute positioning. If it doesn't find anything, it will finally use the absolute position, with respect to the body element.

If the parent element is the body, then this position would make it appear as what we would call as absolute positioning.

When an element's position is made absolute, the entire page layout is redrawn as if the element is removed. Hence, other elements move in and occupy its space.

### Position: Fixed
The element will stay at fixed position in the screen, even when user scrolls.

### Centering a Div
To center a div, there are multiple options.

One way is to, make text-align property of parent element to be center, to make all child elements to be center.
`body {
  text-align:center;
}`

This would not work with those child elements, which has width property. When an element has width, you can use margin to auto to center the element as below.
`container {
  width: 600px;
  height: 300px;
}`

## Sizing
1. px - Pixels. Absolute units, doesn't change even when user changes the font size to be larger in browser settings.
2. vh - View screen height. 100vh refers to the 100% height of the view screen.
3. vw - View screen width, similar to vh. 100vw refers to 100% width of the view screen.
4. % - Percentage. 100% refers to the original size. For text, it corresponds to 16px.
5. em - A different unit, where 1em refers to the size of m. 2em would refer to size of 2 'm's. This unit cascades. If the font size is specified as 2em in body and a child inside the body specifies as 3em, the total size applied would be 6em.
6. rem - Root-em. To avoid cascading, use 'rem', where we are explicitly specifying the size to be relative to the root 'em'. 1 rem = 16px.

## Useful Resources
1. [Devdocs](https://devdocs.io/)
2. [Emmet shorthand](https://docs.emmet.io/cheat-sheet/)
