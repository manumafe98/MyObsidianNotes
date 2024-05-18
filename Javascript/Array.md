
As javascript is not strong typed you can combine multiple data types into a single array, but it's not recommended


Define an array:

```js
let numbers = [];
```

Access the values of an array;

```js
console.log(numbers[index]);
```

## Methods

#### Length

```js
console.log(numbers.length)
```

#### push

Pushes one or more elements to the end of the array

```js
let numbers = [1, 2, 3];

numbers.push(4);

console.log(numbers) // [1, 2, 3, 4]
```

You can also pass multiple parameters to push and they will be added in order.

#### pop

Eliminates the last element of the array

```js
let numbers = [1, 2, 3];

let deletedNumber = numbers.pop();

console.log(numbers) // [1, 2]
console.log(deletedNumber) // 3
```

#### shift

Eliminates the first element of the array

```js
let numbers = [1, 2, 3];

let deletedNumber = numbers.shift();

console.log(numbers) // [2, 3]
console.log(deletedNumber) // 1
```

#### unshift

Adds one or more elements to the beginning of the array

```js
let numbers = [1, 2, 3];

numbers.unshift(0);

console.log(numbers) // [0, 1, 2, 3]
```

You can also store it in a variable to get the new `length` of the array

```js
let numbers = [1, 2, 3];

let new_length = numbers.unshift(0);

console.log(new_length) // 4
```

#### join

```js
let test = ["t", "e", "s", "t"];

let newString = test.join("");

console.log(newString) // test
```

#### indexOf

#### lastIndexOf

#### includes

#### concat

#### sort

#### find

#### splice

#### slice

#### map

#### filter

#### reduce

#### for-each


