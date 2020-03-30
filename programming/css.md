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

Elements set to `inline` only occupy the space that their `.innerHTML` property takes up.

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

## Units of measurement for CSS properties

Absolute units:
- px
- in
- mm
- cm

Relative units:
- %
- em  //A unit equivalent to the current font size. 
- vw  //1vw = 1/100th of the viewport width
- vh  //1vh = 1/100th of the viewport height

---

## `text-decoration`

`text-decoration: none` //removes the underline 

---

## Hexadecimal and RGB

`#0000ff` = `#00f` = `rgb(0,0,255)` = `rgb(0%,0%,100%)` = `blue`

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

- `order` //the default value is `0`. So, if I want to show an element first, I can use any value lower than 0. If I want to show it later, I can use any value greater than 0.
- `flex-grow` //the default value is `0`. With different values, the items expand. The higher the value, the more space the element takes compared to the others.
- `flex-basis` //sets the initial main size of a flex item. 
- `flex` is shorthand for `flex-grow`, `flex-basis` and `flex-shrink`.

Important:
Using `margin: auto` in a flex item makes its margin occupy the entire space between the element and its sibling.
With it, we can override the alignment specified by `justify-content`.

The **flex container** contains the **flex items**.

If you have `flex-direction: row` or `flex-direction: row-reverse`, the **main axis** is horizontal.
If you have `flex-direction: column` or `flex-direction: column-reverse`, the **main axis** is vertical.

The start of the main axis is the **main start** and the end of the main axis is the **main end**.

The cross axis runs perpendicular to the main axis.
It also has a **cross start** and a **cross end**.

`justify-content` controls where flex items sit in the **main axis**.
- `justify-content: flex-start` //(default)
- `justify-content: flex-end`
- `justify-content: center`
- `justify-content: space-between` //puts equal space between the flex elements, with the first and last elements at the edges
- `justify-content: space-around` //puts equal space between the flex elements and between the first and last elements and the edges


`align-items` controls where flex items sit in the cross axis.
- `align-items: stretch` //items stretch vertically
- `align-items: flex-start` //items align to the start of the cross axis
- `align-items: flex-end` //items align to the end of the cross axis
- `align-items: center` //aligns items in the cross axis
- `align-self` //alignment of single elements

---

## Flexbox vs. CSS Grid

- Grid is two dimensional, while Flexbox is one dimensional
- Grid is layout first, while Flexbox is content first
- Flexbox is for components of an app, while Grid is for the app layout itself

---

## CSS Grid

```css
.container{
	display: grid;
	grid-template-columns: 10vw 10vw; //sets two columns, each with 10vw
	grid-template-rows: 15vh 15vh; //sets two rows, each with 15vh
	grid-gap: 10px; //sets a gutter of 10px between rows and columns
	justify-content: center;
}
``` 

---

## Grid areas

```css
.container {
	grid-template-columns: 45px 150px;
	grid-template-rows: 50px 150px 30px;
	grid-template-areas:	//creates the grid area
	"hd hd hd hd hd"
	"sd sd main main main"
	"ft ft ft ft ft";
}

.item1 {
	grid-area: main;	//places the item1 in the main area
}

.item2 {
	grid-area: 1/1/3/5;	//row-start(including itselfi)/column-start(including itself)/row-end(excluding itself)/column-end(excluding itself) 
}
```

---

## Explicit tracks vs. Implicit tracks

Explicit tracks are created with `grid-template-rows` and `grid-template-columns`. You manually define the number of tracks.

Implicit tracks are automatically created when there are more grid items than cells.
Implicit tracks are created with `grid-auto-collumns` and `grid-auto-rows`.
```css
.item{
	grid-auto-columns: 15px; //new automatic columns will be 15px wide
	grid-auto-rows: auto; //new automatic rows will have auto size
}
``` 

---

## fr unit

`1fr` is 100% of the space available taking into account the gutter.
For example:
```css
.container {
  display: grid;
  grid-template-columns: 800px repeat(3, 1fr); //creates 1 column with 800px and then 3 columns, each with the same fraction of the remaining space 
  grid-auto-rows: minmax(50px, auto);
  grid-gap: 10px;
}
```

---

## `auto-fill` and `auto-fit`

```css
grid-template-columns: repeat(auto-fill, 200px); //will create as many columns of 200px as possible inside the container
grid-template-columns: repeat(auto-fit, 200px); //will create as many columns of 200px as there are elements to be displayed. Any empy tracks collapse. If there are more items, auto-fit creates more columns.
```

---

## repeat() CSS function

Can be used in the properties `grid-tempalte-columns` and `grid-template-rows`.
`grid-template-rows: repeat(4, 1fr)` = `grid-template-rows: 1fr 1fr 1fr 1fr`

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
Examples:
```
img + p {				//this will target paragraphs that come immediately after any image 
	font-style: bold;
}
```
```
input[type="checkbox"]:checked + label {
	font-weight: bold;	//this will make every label next to a ckecked radio or checkbox bold
}
```

`~` //general sibling combinator -> targets the second element only if it follows the first element (though not necessarily immediately), and both are children of the same parent element
```
img ~ p {				//this will target every paragraph that is sibling to any image 
	font-style: bold;
}
```

---

## `:first-child` and `:last-child`

`li:first-child` //targets every first li element
`li:last-child` //targets every last li element

---

## `:only-child`

Targets elements that have no siblings

---

## `:empty`

Targets elements that have no content or no other elements nested inside

---

## Substring matching attribute selectors

`^` //defines the **begins with** selector
```
a[href^="http://"]		//this targets only anchor elements whose href attribute's value starts with "http://"
```

`$` //defines the **ends with** selector
```
a[href$=".pdf"]			//this targets only anchor elements whose href attribute's value ends with ".pdf"
```

`*` //defines the **contains** selector
```
img[src*="thumbnails"]	//this targets only img elements whose src attribute's value contains "thumbnails"
```

## Action pseudo-classes

`:hover`
`:focus`

---

## State pseudo-classes

`:disabled`
`:checked`

---

## `nth-child()` vs. `nth-of-type()`

`div:nth-child(2)` targets the second **element** of its parent.
`div:nth-of-type(2)` targets the second **div** of its parent.

---

## `:root` pseudo-class

Targets the top element in the document (usually the <html>).

---

## `:target` pseudo-class

Targets the element that is currently the target of a link

---

## `:not` pseudo-class

Targets every element that does *not* fulfill the rule
Examples: `input:not([type="submit"])` | `div:not(:first-child)`

---

## CSS pseudo-elements

`::first-line`
`::first-letter`
`::before` //We always need to use `content: ` in conjunction with `:before` and `:after`.
`::after`

Note: although single colon works, usually we use double colon (`::`) with pseudo-elements to distinguish them from pseudo-classes.

---

## attr()

Function used to retrieve the value of an attribute of the selected element and use it in the stylesheet.

```
a {
	content: attr(href);
}
```

---

## transform

Note: doesn't work for inline elements such as <a>. I can change the element to `inline-block` to make it work.

---


