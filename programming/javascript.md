## parseInt();

Parses a string into an integer, allowing for math operations using values originally brought in as strings.

Example:

```js
let age = prompt('What`s your age?');
let futureAge = parseInt(age) + 5;
document.write('In 5 years you will be ' + futureAge + ' years old.');
```

---

## parseFloat();

Similar to `parseInt()`.
Parses a string into a float number.

OBS: you can even parse a string beginning with number, such as "1.7 thousand dollars". Only the number part of the string will be parsed. The same applies for parseInt().

Example:

```js
let result = parseFloat('1.7 thousand dollars');
```

result will hold the value `1.7`

---

## toLowerCase();

Example: we can use it to guarantee a string entered by the user will be validated no matter the case:

```js
let answer = prompt("What is the name of the first Brazilian president elected by people's vote?");
if (answer.toLowerCase() === 'prudente de moraes') {
	document.write("That's right!");
}
```

---

## Math

An example for generating random numbers between 1 and 10:

```js
Math.floor( Math.random() * 10 ) + 1;`
```

---

## Comparison between strings and between string and number

`'arco' < 'bolha'` = `true`
JS considers the first letter of the string to make this comparison.

`16` < `casa` = `true`
A letter is always greater than a number.

---

## `==` vs. `===`

`==`: Equal to --> `"7" == 7` is true -> JS converts the string to a number to make the comparison.
`===`: Strict equal to --> `"7" === 7` is false -> JS compares the value and the type.

---

## A `return` statement causes the function to exit *immediately*

---

## Function accessing the global scope

Without the `var` or `let` keyword inside the function, it is accessing the global scope, which is usually a *bad idea*.

Example

```js
let name = 'Brian';

function upperName() {
	name = name.toUpperCase();
	return name;
}

```

Without using the `var` or `let` keywords inside the function, I'm overwriting the `name` global variable.

---

## `throw new Error("Error message");`

This throws an error to the console

---

## `break` statement

It exits a loop immediately.

---

## `push()` and `unshift()` array methods

`push()` inserts one or more items at the end of the array
`array.push( 1, 'hello', false );`

`unshift()` inserts one or more items at the beginning of the array
`array.unshift( 0, 'hi', true );`

---

## `pop()` and `shift()` array methods

`pop()` removes the last item of the array and returns it
`let lastItem = array.pop();`

`shift()` removes the first item of the array and returns it
`let firstItem = array.shift();`

---

## `join()` array method

Returns a string with all the items in the array separated by a separator provided as the parameter

```js
let nums = [1,2,3,4,5];
let numsString = nums.join(', ');
// numsString = "1, 2, 3, 4, 5"
```

---

## `concat()` array method

Concatenates two arrays

```js
let fruits = ['apple', 'orange'];
let newFruits = ['banana', 'watermelon'];
let allFruits = fruits.concat( newFruits ); // allFruits = ['apple', 'orange', 'banana', 'watermelon'];
```

---

## `indexOf()` array method

Show the index of an element inside the array

```js
let letters = ['a', 'b', 'c', 'd'];
let position = letters.indexOf('c'); // position = 2 
```

If the element is *not* in the array, `indexOf()` returns '-1':

```js
let position2 = letters.indexOf('g'); // position2 = -1
```

This is useful for checking if an element is part of an array.
Example:

```js
let search = prompt('What fruit do you want?');
if ( array.indexOf( search ) !== -1 ) {
	document.write('We have it!')
} else {
	document.write("Sorry, we don't have it.");
}
```

---

## Accessing values in two-dimensional arrays

```js
let nums = [
	[78, 90, 'olá', 2],
	[99, 132],
	['josé', 'maria', 'carlos', 35, 88]
]

let data = nums[1][0] // data = 99
```

---

## Why creating a function to do something simple like printig to the page?

`#bestpractices`

Because if I'm printing 100 times to the page and later I find a better way to do this, I only have to edit my function 1 time, instead of editing 100 lines of code.

---

## "for in" loop

Used to iterate through object's properties or values

```js
let employee = {
	name: 'John',
	age: 26,
	area: 'Finance',
	partner: false
}

for (let key in employee) {
	console.log(key);			// This logs the keys
}

for (let key in employee) {
	console.log(employee[key]);	// This logs the values
}
```

---

## When the user presses the 'Cancel' button in a prompt window, the value returned is `null`

---

## Listening for clicks

```js
let buttonHello = document.getElementById('hello');
buttonHello.addEventListener('click', () => {
	// do something
});
```

---

## querySelector vs. querySelectorAll

`document.querySelector()` returns the first HTML element that mathces
`document.querySelectorAll()` returns a collection of all HTML elements that match

Note 1: with `querySelector` you need to provide the dot in case you want a class or a pound if you want an id
Examples: `document.querySelector('.main')` | `document.querySelector('#items')`

Note 2: you can select any attribute this way:
`document.querySelector('[attribute=value]')`

Note 3: you can use descendant selectors:
`galleryLinks = document.querySelectorAll('#gallery a');`
or
`navigationLinks = document.querySelectorAll('nav ul li a');` //this brings a collection of `<a>` elements inside every `<li>` inside every `<ul>` inside every `<nav>` 

---

## textContent and innerHTML

```html
<p class="el">Texto</p>
<ul>
	<li>1</li>
	<li>2</li>
</ul>
```
```js
let element = document.querySelector('el');
let text = element.textContent; // text = "Texto"
let list = document.querySelector('ul');
let listContent = list.innerHTML; // listContent = "<li>1</li> <li>2</li>"
```

---

## className

To get the class of an element we use the property `.className`

`<a href="#" class="topLink">Hey</a>`
```js
let link = document.querySelector('.topLink');
let linkClass = link.className; // linkClass = 'topLink'
```

---

## Appending nodes

node.appendChild(childElement)

```
<p id="par">text</p>
<div class="main"></div>
```
```js
let paragraph = document.getElementById('par');
let mainDiv = document.getElementsByClassName('main');
mainDiv.appendChild(paragraph);
```

---

## Removing elements

node.removeChild(ChildElements)

---

## Passing functions into functions

Functions are first-class citizens in JS, so they can be passed as arguments.

```js
function say(what){
	alert(what);
}

function execFunc(func, arg){
	func(arg);
}

execFunc(say, 'olá');

/* Turning that into a function expression*/
execFunc(function say(what){
	alert(what);
}, 'olá');

/* Turning the function passed in as argument into an arrow function*/
execFunc((what) => {
	alert(what);
}, 'olá');
```

---

## Event Bubbling

If we set an event handler on an element, the callback will trigger whenever its children are triggered.
Example: `<div class="hasClickEvent"><ul><li><p>Hello</p></li></ul></div>`
>If p, li or ul are clicked, the callback will be triggered.

However, it's ideal to add the event listener as close to the target element as possible. 

---

## The Event object

When an event handler is called, it receives an Event object as its first argument.

```js
let container = document.querySelector('div.main');
container.addEventListener('click', (event) => {
	console.log(event);		// this logs the event object passed in when the div is clicked
})
```

---

## parentNode

```
<div>
	<ul>
		<li>Item 1</li>
		<li>Item 2</li>
	</ul>
</div>
```
```js
let listItem1 = document.getElementsByTagName('li')[0];
let parent = listItem1.parentNode; //parent = <ul>...</ul>
```

---

## previousElementSibling | nextElementSibling

```
<div>
	<ul>
		<li class="c1">Item 1</li>
		<li class="c2">Item 2</li>
	</ul>
</div>
```
```js
let listItem2 = document.getElementsByTagName('li')[1];
let previous = listItem2.previousElementSibling; //previous = <li class="c1">Item 1</li>
```

---

## insertBefore()

```
[parentNode].insertBefore([newNode],[referenceNode]); 
//the [referenceNode] is the one before which the [newNode] will be inserted
```

---

## .children | .firstElementChild | .lastElementChild

* `el.firstElementChild` = `el.children[0]`

---

## classList

- classList.add() | `el.className += "hello"` = `el.classList.add("hello")`
- classList.remove()
- classList.toggle()

---

## Hoisting

At run-time, all variables declared with `var` are hoisted, which means they are raised to the top of the functions scope.

Variables declared with `let` or `const` are scoped to the **block** (between curly braces), not the function. 
In such case, the variable is stuck in the **temporal dead zone** until its declaration is processed, if it ever is.

---

## `let` and `const`

`let` and `const` can't be redeclared in the same scope.
`let` can be reassigned. `const` cannot.

---

## Template literals

Used for more efficient string interpolation (compared to interpolating through regular concatenation).

Examples:

```js
let name = "Breno";
console.log(`My name is ${name}.`);
```

```js
let bananas = 3;
let apples = 5;
console.log(`There are ${bananas+apples} fruits in the basket.`)
```

---
