
The **spread (`...`)** syntax allows an iterable, such as an [[Javascript/Array|array]] or string, to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected.

Can be useful as well to make a copy of an array.

```js
const array1 = [1, 2, 3];
const array2 = [...array1];
```

Or as said before to use the values of an array to act as parameters of a [[Javascript/Functions|function]] 

```js
const numbers = [1, 2, 3, 4, 5];

const sum = (a, b, c, d) => {
    return a + b + c + d;
};

const result = sum(...numbers);

console.log(result) // 10
```

You can see in the previous example, that the array has more elements than the function parameters, this doesn't alter the functionality as it takes the number of elements as parameters has.

Can be used as well in [[Ojbects|objects]]

```js
const object1 = {
    a : 1,
    b : 2,
}

const object2 = {
    ...object1,
}

console.log(object2) // { a: 1, b: 2 }
```

Something to keep in mind is that as you are making a copy if you then add an element to the original object or array, that element is not going to be in the copy.

```js
const numbers1 = [1, 2, 3, 4, 5];

const numbers2 = [...numbers1];

numbers1.push(6);

console.log(numbers1) // [ 1, 2, 3, 4, 5, 6 ]
console.log(numbers2) // [ 1, 2, 3, 4, 5 ]
```
