
[[JavaScript]] is a [dynamic](https://en.wikipedia.org/wiki/Dynamic_programming_language) language with [dynamic types](https://en.wikipedia.org/wiki/Type_system#DYNAMIC). Variables in JavaScript are not directly associated with any particular value type, and any variable can be assigned and re-assigned values of all types.

## Declaration keywords

### var

The keyword `var` is used to declare a variable with **global** scope

```js
var test = "hello";
```

### let

The keyword `let` is used to declare a variable with **block** scope, it is recommended to used instead of [[Javascript/Variables#var|var]] because is safer and has a more predictable behavior.

```js
let test = "hello";
```

### const


## Data types

![[Javascript_data_types.jpeg]]

```js
let test; // undefined
```

## Comparison operators

![[Javascript_comparison_operators.jpeg]]

## typeof

You can use `typeof` to check the data type of a variable

```js
let num = 1;

console.log(typeof (num))
```