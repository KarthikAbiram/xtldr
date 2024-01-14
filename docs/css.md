---
hide:
  - navigation
---
# CSS
## CSS Types
| Type     | Description                                                                           |
| -------- | ------------------------------------------------------------------------------------- |
| Inline   | CSS styles that is provided inside each HTML element                                  |
| Internal | CSS style that is provided as part of <head> which is applied to the entire HTML page |
| External | External CSS file which can be referenced and used by multiple HTML files.            |

### Order of Priority
> More specific -> Higher the priority. 

For example, when considering tag (like h, p), class and id selectors, the id selector has the highest priority, as its most specific among all three.

> Last specified rule overrides previous set rules.

Inline CSS will trump internal and external CSS, since that would be the last that is getting applied. Priority between Internal CSS or External CSS would depend on, what is applied last among these. If internal CSS is set after linking the external CSS, internal CSS would have the priority.

## CSS Selectors
| Selector | Format                              | Description                                                                                    |
| -------- | ----------------------------------- | ---------------------------------------------------------------------------------------------- |
| Tag      | `h1 {background: yellow;}`          | Tag Selectors (like h1, p, body)                                                               |
| Class    | `.my-class-name {background: red;}` | Class Selectors (custom, user defined classes, which can be applied to multiple HTML elements) |
| ID       | `#my-id {background: brown;}`       | ID Selectors (specific CSS which targets a single individual HTML element)                     |

### Multiple Classes
A single HTML element can have more than 1 class defined, like below. 
`<p class="red-text highlight"></p>`
In this example, this are two CSS classes - "red-text" and "highlight". Properties of both these classes would be applied.

### Pseudo Class
A pseudo-class is used to define a special state of an element. For example, it can be used to style an element when a user hovers over it.

## Box Model
Everything in a web page is a rectangle/box.
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/e/ed/Box-model.svg)

## Display Types
| Type                  | Description                                                                                 | Width               |
| --------------------- | ------------------------------------------------------------------------------------------- | ------------------- |
| Display: Block        | Occupies entire horizontal row  . Eg: h1, p, div                                            | Can't specify width |
| Display: Inline       | Takes required width based on content. Multiple elements can occupy single row. Eg: span, a | Can't specify width |
| Display: Inline-Block | Elements can occupy the same row, as well as ability to specify width                       | Can specify width   |

**Display: None vs Visibility: Hidden**  
Both display: none and visibility: hidden, hides the element. But when display:none is used, it is as this the element is removed/deleted and other elements move in and occupy its space. 

When visibility:hidden is used, the element is removed but the space it was occupying will be vacant and other elements would not take its place.

## Positioning

=== "Position: Static"
	> Position the element based on the HTML flow/layout.

	Default positioning of CSS elements. 

=== "Position: Relative"
	> Position an element relative to its "static" positioning, where the static positioning is defined by the HTML layout. 
	
	After specifying the position as relative, we can use the properties like top, right, bottom, left to move the HTML element from its static position. 
	
	Just setting position to relative without setting values to properties like top, right, bottom, left will not have any effect on the position of the element. There is also a valid use case for this, when the child elements position is made absolute (covered in next section).

	For example, to add a space of 200 px to the top of the element whose id is element-id:

	```css
	#element-id {
	position: relative;
	top: 200px;
	}
	```

	One important thing to note is that, moving a position using relative property would not affect the positions of other elements in the web page. For example, if we are moving an element down by 200px, the element would now overlap with its bottom element.

=== "Position: Absolute"
	> Position the element, relative to its parent element which is set to relative. 
	
	If the parent element position is not set to relative, it will traverse to its parent, to see if that or its parent is relative and use that for absolute positioning. If it doesn't find anything, it will finally use the absolute position, with respect to the body element.

	If the parent element is the body, then this position would make it appear as what we would call as absolute positioning.

	When an element's position is made absolute, the entire page layout is redrawn as if the element is removed. Hence, other elements move in and occupy its space.

=== "Position: Fixed"
	> The element will stay at fixed position in the screen, even when user scrolls.

### Centering a div
One way is to, make text-align property of parent element to be center, to make all child elements to be center.
```css
body {
  text-align:center;
}
```

This would not work with those child elements, which has width property. When an element has width, you can use margin to auto to center the element as below.
```css
container {
  width: 600px;
  height: 300px;
}
```

## Sizing
| Unit | Description                                                                                                                        |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------- |
| px   | Pixels. Absolute units, doesn't change even when user changes the font size to be larger in browser settings.                      |
| vh   | View screen height. 100vh refers to the 100% height of the view screen.                                                            |
| vw   | View screen width, similar to vh. 100vw refers to 100% width of the view screen.                                                   |
| %    | Percentage. 100% refers to the original size. For text, it corresponds to 16px.                                                    |
| em   | 1em refers to the size of m. Cascades. If the body font size is 2em and a child font size is 3em, the size applied would be 6em.   |
| rem  | Root-em. To avoid cascading, use 'rem', where we are explicitly specifying the size to be relative to the root 'em'. 1 rem = 16px. |

## CSS Useful Links
1. [Align Elements Side by Side](https://codepen.io/beau/pen/odbrRa)

## Useful Resources
1. [Devdocs](https://devdocs.io/)
2. [Emmet shorthand](https://docs.emmet.io/cheat-sheet/)
