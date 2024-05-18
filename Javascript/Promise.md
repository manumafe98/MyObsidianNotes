A **`Promise`** is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a _promise_ to supply the value at some point in the future.

A `Promise` is in one of these states:

- _pending_: initial state, neither fulfilled nor rejected.
- _fulfilled_: meaning that the operation was completed successfully.
- _rejected_: meaning that the operation failed.

Example:

```js
const guessedNumber = prompt("Guess a number from 1 to 10");

const promise = new Promise((res, rej) => {
  const random = Math.round(Math.random() * 10 );

  random == guessedNumber
    ? res("Your guess is correct!")
    : rej(`The actual number was ${random}`);
});

promise
  .then((res) => {
    console.log(res);
  })
  .catch((error) => {
    console.error(error);
  });
```

You can set a timeout in promises and also have multiple ones.
If you want to control the execution order of promises you can use `Promise.all` like this:

```js
const promise1 = new Promise((res, rej) => {
  setTimeout(() => {
    res("This is promise number1");
  }, 2000);
});

  

const promise2 = new Promise((res, rej) => {
  setTimeout(() => {
    res("This is promise number2");
  }, 1000);
});

  

Promise.all([promise1, promise2]).then((res) => {
  console.log(res[0]);
  console.log(res[1]);
});
```

If you do not use `Promise.all` the execution will be `promise2` and then `promise1` because of the timeout settled
