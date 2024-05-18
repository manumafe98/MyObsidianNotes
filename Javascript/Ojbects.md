
## Define a new object

```js
let user = {
	name : "Manuel",
	surname : "Maxera",
	age : 25,
	greet : function() {
		return `Hey, I'm ${this.name}`;
	}
}
```

## Access object values

#### attribute

```js
let userName = user.name; 

console.log(userName); // Manuel
```

#### method

```js
let receivingGreeting = user.greet();

console.log(receivingGreeting) // Hey, I'm Manuel
```

## Update a object value

```js
user.age = 26:
```

## Add a new property to the object

```js
user.favouriteSport = "Football";
```

## Delete a property of an object

```js
delete user.favouriteSport;
```
