
## If statement

```js
if (condition) {
	let do_something = "drives";
	return do_something;
}
```

## If/else if/else

```js
if (condition) {
	console.log("Test");
} else if (another_condition) {	
	console.log("another test");
} else {
	console.log("final")
}
```


## Ternary operators

```js
let number = 5;

(number > 1) ? `${number} is greater than one` : `${number} is lower than one`;
```

If you want to execute multiple things in a ternary operator you can do the following

```js
let number = 5;

(number > 1) ? (
	`${number} is greater than one`,
	console.log(number) ) : (
		`${number} is lower than one`,
		console.log(number) );
```
