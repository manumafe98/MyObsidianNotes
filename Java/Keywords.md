[[Java]] keywords

### Static
is used to create class-level properties and methods that are shared among all instances (objects) of that class and can be accessed through the class itself, not just through instances. It's like features of the blueprint rather than features of individual objects created from that blueprint.
You can apply this to [[Java/Variables]] , [[Methods]] and classes

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

		System.out.println(Friend.numberOfFriends); // Accesed through class
		// Output = 3

		Friend.displayFriends();
		// Output = "You have 3 friends"
	}
}
```
So if you delete the static keyword from ``numberOfFriends`` then you would have to access that variable through the ``friend1`` for example and it would display 1, instead of 3. Also used to avoid the declaration of the object, so you can call it directly from the main class.

#### Static Initialization Blocks

A _static initialization block_ is a normal block of code enclosed in braces, `{ }`, and preceded by the `static` keyword. Here is an example:

```java
    static int B;
    static int H;
    static boolean flag;
    static 
    {
        Scanner scanner = new Scanner(System.in);
        B = scanner.nextInt();
        H = scanner.nextInt();
        if (B < 0 || H< 0 ) {
            System.out.println("message");
        } else {
            flag = true;
        }
    }
```

A static initialization block in Java is not like a method that you call explicitly. Instead, it is a block of code that is executed when the class is loaded into memory, and it runs before any instance of the class is created or any static members of the class are accessed. The purpose of a static initialization block is to initialize static variables or perform some one-time setup for the class.

A class can have any number of static initialization blocks, and they can appear anywhere in the class body. 


### Void
its used when you don't want to return a value, but you have to specify it.

```java
void hello() {
	System.out.println("Hello");
}
```


### Super
refers to the superclass (parent) of an object very similar to the "this" keyword, used with [[Java/OOP/Classes#Inheritance|inheritance]]. Works with [[Java/Variables]] and [[Methods]].

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
Are declared but without an implementation


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
