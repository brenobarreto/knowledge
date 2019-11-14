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