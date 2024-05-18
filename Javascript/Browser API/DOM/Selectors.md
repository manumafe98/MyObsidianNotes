
## getElementById

Imaging that you have a `<p>` tag in the `index.html` file

```html
<body>
    <p id="test">test</p>
    <script src="script.js"></script>
</body>
```

You can select that element in your `js` file with the following method

```js
document.getElementById("test")
```

Then you can apply changes to it some examples:

### set Attribute

This one will apply a certain class to that element

```css
.red {
    color: red;
}
```

```js
document.getElementById("test").setAttribute("class", "red")
```


## querySelectorAll

Is a selector in the query format, like the `css` one

```js
document.querySelectorAll("p.test");
```

This selector selects all the elements that match that criteria, so then you need or either iterate or select it by index.

