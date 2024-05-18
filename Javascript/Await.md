The **`await`** operator is used to wait for a [[Promise|promise]] and get its fulfillment value. It can only be used inside an [[Async|async function]] or at the top level of a module.

```js
await expression
```

For example can be used in a `fetch` to wait until the response.

```js
const response = await fetch('https://api.example.com');
```
