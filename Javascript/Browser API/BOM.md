The **Browser Object Model (BOM)** is a browser-specific convention referring to all the objects exposed by the web browser. The BOM allows [[Javascript]] to “interact with” the browser. 

The object of the window represents a browser window and all its corresponding features. A window object is created automatically by the browser itself. JavaScript `window.screen` object contains information about the user’s screen. It can also be written without the window prefix.

Some functionalities of the `BOM` are:
- [[Geolocation]]
- [[LocalStorage]]
- [[SessionStorage]]
- [[DOM]]

## Window methods

### Alert

Mainly used to display a message in the browser.

```js
alert("Incorrect password");
```

### Prompt

```js
const res = prompt("What is your favourite programming language", "Java");
```

- First parameter is the question you want to trigger in the browser
- Second parameter is the default value

### Confirm

```js
const res = confirm("Are you the boss?");
```

This one will display `true` or `false` depending if the user clicked yes or no in the browser
