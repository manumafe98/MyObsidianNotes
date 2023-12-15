
In [[Java]] interfaces are like a template that can be applied to a [[Java/OOP/Classes|class]].
Similar to [[Java/OOP/Classes#Inheritance|inheritance]], but specifies what a class has/must do.
Classes can apply more than one interface, inheritance is limited to one super class.
Similar with [[Keywords#Abstract|abstract]] keyword as well, cause you must implement the methods that are in the interface making an override.

Prey.java
```java
public interface Prey {
	void flee(); //has no body like abstract methods
}
```

```java
public class Fish implements Prey {
	@Override
	public void flee() {
		System.out.println("The fish is escaping");
	}
}
```
