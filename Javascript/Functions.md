
## Function declaration

```js
function name(parameters) { // definition
	body;
}

name("Manu"); // Function call
```

Can be accessed before its `initialization`

## Function expressions

```js
let sum = function(num1, num2) {
	return num1 + num2;
}
```

Function expressions are convenient when passing a function as an argument to another function.

As you can see in the definition of `function expression` the function doesn't have a name, when defined like this it can be called an `anonymous` function, but it also can be declare with a name.

```js
let factorial = function fac(n) {
	return n < 2 ? 1 : n * fac(n - 1);
}
```

## Arrow functions

```js
let multiplication = (num1, num2) => {
	return num1 * num2;
}
```

They have a shorter syntax compared to function expressions and does not have its own [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this), [`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments), [`super`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super), or [`new.target`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target).

They are always `anonymous` functions
