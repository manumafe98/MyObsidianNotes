
```js
class Dog {

}
```

## Constructor

```js
class Dog {

	constructor() {
		body;
	}
}
```

## Inheritance

```js
class Animal {

}

class Dog extends Animal {

}
```

## Polymorphism

It is the practice of designing objects to share behaviors and to be able to override shared behaviors with specific ones.

```js
class Animal {
	doSomething() {
		return "does something";
	}
}

class Cat extends Animal {
	doSomething() {
		return "Miau";
	}
}

class Dog extends Animal {
	doSomething() {
		return "Bark";
	}
}

function animalDoesSomething(animal) {
	return animal.doSomething();
}

const myCat = new Cat();
console.log(animalDoesSomething(myCat)); // Miau
```

## Encapsulation

```js
class Dog {
	#age; // -> Private field
	name = "Ekko"; // -> Public field
	static staticField // -> Static field
}
```

`private` cannot be accessed directly through the object
`public` can be accessed directly through the object
`static` only can be accessed by the class itself `Dog.staticField`
