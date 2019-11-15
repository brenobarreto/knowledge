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

