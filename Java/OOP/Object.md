
A ``object`` is an instance of a [[Java/OOP/Classes|class]] that may contain attributes and methods.

Here is an example of how to define an object and access it's methods and attributes

```java
Human human = new Human("elbananax", 25, 1.75);

System.out.println(human.name);
human.eat();
```

### toString()

A special method that all object inherit, that returns a string that "textually represent" an object. Can be used ``implicitly`` and ``explicitly``

```java
DiceRoller diceroller = new DiceRoller();
System.out.println(diceroller); // implicitly
System.out.println(diceroller.toString()); // explicitly


// Output: DiceRoller@23fc625e 
```

``DiceRoller@23fc625e`` is the address of the object ``DiceRoller`` in memory

Sometimes for ``toString()`` is applied what's called [[Java/OOP/Classes#Method overriding|method overriding]]
That means that you create the method ``toString()`` to display the attributes of the object itself, instead of the address in memory.


### Polymorphism

The ability of an object to identify as more than one type.

```java
public class Car extends Vehicle {

}

public class Bicycle extends Vehicle {

}
```

So for example if we want to make an array of different objects 
```java

public class Main {
	public static void main(String[] args) {
		Car car = new Car();
		Bicycle bicycle = new Bicycle();

		Vehicle[] racers = {car, bicycle} // We use the parent class
	}
}
```


### Dynamic Polymorphism

Dynamic: after compilation(during runtime).
You declare an object and make space for it in memory even if you don't know what type of object do you want.

```java
Animal animal;
```

And then after certain condition you initialize the animal with a certain subclass, example:

```java
animal = new Cat();
```
