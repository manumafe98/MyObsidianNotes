An `enum` in [[Java]] is a special [[Java/OOP/Classes|class]] that represents a group of **constants** (unchangeable [[Java/Variables|variables]], like [[Java/Variables#Final keyword|final]])

To create an `enum`, use the `enum` keyword (instead of class or interface), and separate the constants with a comma. Note that they should be in uppercase letters

```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}
```

You can also have an `enum` inside a class.

```java
public class Main {
	enum Food {
		Pizza,
		Hamburger,
		Pasta;
	}
}
```


Just like regular Java classes ``enums`` can have fields and [[Methods|methods]]
```java
public enum Subjects {
	Math(8),
	Programming(9),
	Physics(7);

	final int grades;

	Subjects (int grades) {
		this.grades = grades;
	}
}
```
