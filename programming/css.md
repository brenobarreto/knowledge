## CSS Reset

`normalize.css`

It resets some styles from User Agent Stylesheet to provide cross-browser compatibility

---

## Sticky Footer

Example for a footer with 200px height:

```
.main-wrapper {
	min-height: calc(100vh - 200px);	// 100% of the viewport - the footer height
}
```

---

## Inline elements attributes | `inline-block`

For inline elements the browser will *not* apply:
- Wigth
- Height
- Top and bottom margin
- Top and bottom padding

`display: inline-block` keeps elements floating horizontally but can bu styles as a block element

---

## `clear` property

It sets whether an element must be moved below (cleared) floating elements that precede it.

Possible values:
`clear: none`
`clear: left`
`clear: right`
`clear: both`

---

## clearfix to fix Float and collapsing heights

When you float elements, the parent container's height collapses, because it no longer respects the space of the floated elements inside it.

```

.clearfix::after {
	content: "";
	display: table;
	clear: both;
}

```

---

## overflow

The `overflow` shorthand CSS property sets what to do when an element's content is too big to fit in its block formatting context. 

When using `overflow: hidden` fixes it by forcing the header to expand and contain the floating elements.

---

## `absolute` and `relative` positioning

By default, the browser viewport is the positioning context for elements with `absolute` position.

An element with `absolute` position is always relative to the first parent that has `relative` position. The first parent with `relative` position becomes the positining context for the element with `absolute` position.

---

## `z-index`

Positioned elements follow a stacking order that determines which elements are displayed above others.

By default, the staking order is defined by the order the elements appear in the source code. Elements that appear later in the HTML sit on top of elements that appear earlier.

We can adjust the stacking order of relative, absolute and fixed elements with the z-index property.

An element with a higher z-index value overlaps elements with lower z-index values when they occupy the same space.

Positioned elements have a z-index of 0 by default.

---

## transition

The shorthand is written as follows:

transition: <property> <duration> <timing-function> <delay>

Example:

`transition: font-size 2s ease 1s`

---

## flexbox

- `display: flex` //turns the element into a flexbox container, occupying the entire line
- `display: inline-flex` //flexbox container acting as an inline element 
- `flex-direction: row`
- `flex-direction: row-reverse`
- `flex-direction: column`
- `flex-direction: column-reverse`
- `flex-wrap: wrap` //wraps child elements in more than one row or column so they fit regardless the size of the window
- `justify-content: flex-start` //(default)
- `justify-content: flex-end`
- `justify-content: center`
- `justify-content: space-between` //puts equal space between the flex elements, with the first and last elements at the edges
- `justify-content: space-around` //puts equal space between the flex elements and between the first and last elements and the edges
- `order` //the default value is `0`. So, if I want to show an element first, I can use any value lower than 0. If I want to show it later, I can use any value greater than 0.
- `flex-grow` //the default value is `0`. With different values, the items expand. The higher the value, the more space the element takes compared to the others.
- `flex-basis` //sets the initial main size of a flex item. 
- `flex` is shorthand for `flex-grow`, `flex-basis` and `flex-shrink`.
- `align-items: stretch` //items stretch vertically
- `align-items: flex-start` //items align to the start of the cross axis
- `align-items: flex-end` //items align to the end of the cross axis
- `align-items: center` //aligns items in the cross axis
- `align-self` //alignment of single elements

Important:
Using `margin: auto` in a flex item makes its margin occupy the entire space between the element and its sibling.
With it, we can override the alignment specified by `justify-content`.

---

## Attribute selectors

```css
[class]				//targets every element that has any class
[id="main"]			//targets every element with id "main"
input[type="text"]	//targets input elements with a type attribute of "text"
```

---

## CSS combinators

`>` //direct children -> targets all immediate children (does not target other descendants [grandchildren, etc.])

`+` //adjacent sibling -> targets the second element only if it immediately follows the first element, and both are children of the same parent element
Example:
```
img + p {				//this will target paragraphs that come immediately after any image 
	font-style: bold;
}
```

`~` //general sibling combinator -> targets the second element only if it follows the first element (though not necessarily immediately), and both are children of the same parent element
```
img ~ p {				//this will target every paragraph that is sibling to any image 
	font-style: bold;
}
```

---

