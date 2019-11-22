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

