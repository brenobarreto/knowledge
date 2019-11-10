## parseInt();

Parses a string into an integer, allowing for math operations using values originally brought in as strings.

Example:

```
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

```
let result = parseFloat('1.7 thousand dollars');
```

result will hold the value `1.7`

---

## toLowerCase();

Example: we can use it to guarantee a string entered by the user will be validated no matter the case:

```
let answer = prompt("What is the name of the first Brazilian president elected by people's vote?");
if (answer.toLowerCase() === 'prudente de moraes') {
	document.write("That's right!");
}
```

---

## Math

An example for generating random numbers between 1 and 10:

`Math.floor( Math.random() * 10 ) + 1;`

---

`'arco' < 'bolha'` = `true`
JS considers the first letter of the string to make this comparison.

`16` < `casa` = `true`
A letter is always greater than a number.

---

`==`: Equal to --> `"7" == 7` is true -> JS converts the string to a number to make the comparison.
`===`: Strict equal to --> `"7" === 7` is false -> JS compares the value and the type.

---

