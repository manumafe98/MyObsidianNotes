[[Java]] keywords

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

```java
void hello() {
	System.out.println("Hello");
}
```


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

### Abstract

#### Abstract classes
Cannot be instantiated but they can have a subclass. Used classes that are to vague, for example a Vehicle you want a subclass to inherit some methods/attributes but do not want to be instantiated itself. 

#### Abstract methods
Are declared but whiteout an implementation


```java
public abstract class Vehicle {
	abstract void go();
}
```

```java
public class Car extends Vehicle {
	@Override
	void go() {
		System.out.println("The car goes")
	}
}
```

So if you implement a abstract method within a class then you are forced to make an implementation/override from that class to you subclasses.
