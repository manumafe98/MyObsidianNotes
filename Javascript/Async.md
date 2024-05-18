
The **`async function`** declaration creates a binding of a new async function to a given name. The [[Await||await]] keyword is permitted within the function body, enabling asynchronous, [[Promise|promise]]-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains.

Can be written like a [[Javascript/Functions#Function declaration|function declaration]]

```js
async function name(params) {
	body;
}
```

or like an [[Javascript/Functions#Arrow functions|arrow function]] as well

```js
const func = async() => {
	body;
}
```
