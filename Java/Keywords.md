[[Java]] keywords

### Public



### Private



### Static
is used to create class-level properties and methods that are shared among all instances (objects) of that class and can be accessed through the class itself, not just through instances. It's like features of the blueprint rather than features of individual objects created from that blueprint.
You can apply this to [[Variables]] , [[Methods]] and classes

```java
public class Friend {
	String name:
	static int numberOfFriends;

	Friend(String name) {
		this.name = name;
		numberOfFriends++;
	}

	static void displayFriends() {
		System.out.println("You have "+numberOfFriends+" friends");
	}
}
```

```java
public class Main {
	public static void main(String[] args) {
		Friend friend1 = new Friend("Carlos");
		Friend friend2 = new Friend("Pepe");
		Friend friend3 = new Friend("Michael");

		System.out.println(Friend.numberOfFriends); // Accesed throw class
		// Output = 3

		Friend.displayFriends();
		// Output = "You have 3 friends"
	}
}
```
So if you delete the static keyword from ``numberOfFriends`` then you would have to access that variable throw the ``friend1`` for example and it would display 1, instead of 3.

### Void
its used when you don't want to return a value, but you have to specify it.


### Super
refers to the superclass (parent) of an object very similar to the "this" keyword, used with [[OOP#Classes#Inheritance|inheritance]]. Works with [[Variables]] and [[Methods]].

```java
public class Person {
	String name;
	int age;

	Person(String name, int age) {
		this.name = name;
		this.age = age;
	}
}
```

```java
public class Hero extends Person {
	String power;

	Hero(String name, int age, String power) {
		super(name, age);
		this.power = power;
	}
}
```
