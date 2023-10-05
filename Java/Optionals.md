
A container object which may or may not contain a non-`null` value, if a value is present.
Optionals are intended to be used as a return type when the value may be null.


Imagine that this list represents a database, and you want to search for a value
```java
private static Optional<Cat> findCatByName (String name) {

	List<Cat> catList = new ArrayList<>();
	catList.add(new Cat("Pepe", 5));
	catList.add(new Cat("Benedetto", 1));
	catList.add(new Cat("Ekko", 3));
	catList.add(new Cat("Glameow", 15));


	for (Cat cat : catList) {
		if (cat.getName().equals(name)) {
			return Optional.ofNullable(cat);
		}
	}
	return Optional.ofNullable(null);
}
```

That value may or may not be there.
```java
public static void main(String[] args) {
	Optional<Cat> optionalCat = findCatByName("Ekko");
	Cat myCat = optionalCat.orElse(new Cat("UNKNOWN", 0));
	System.out.println(myCat.getName());
}
```

So we use optionals to handle the value if it's null.

### isPresent() and get()

is the most traditional way to use it. using the same example as above.

```java
public static void main(String[] args) {
	Optional<Cat> optionalCat = findCatByName("Pepon");
	
	if (optionalCat.isPresent()) {
		System.out.println(optionalCat.get().getName());
	} else {
		System.out.println("UNKNOWN");
	}
}
```

Is present returns a boolean value, if there is a value in the optional is ``true`` else ``false`` so you can handle that, also with ``get()`` you extract the value inside the optional.
``orElse`` does the same but in a shorter way.


