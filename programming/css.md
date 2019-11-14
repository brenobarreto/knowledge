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

`display: inline-block` 

---