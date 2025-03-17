
A constructor in [[Java]] is a ``special method`` that is used to initialize objects. The constructor is called when an object of a [[Java/OOP/Classes|class]] is created. It can be used to set initial values for [[Java/OOP/Object|object]] attributes.

```java
public class Human {

	String name;
    int age;
    double height;

    Human(String name, int age, double height) {
	    //this is like self in python
	    // atributes
		this.name = name;
        this.age = age;
        this.height = height;
    }
	
	// methods
    void eat() {
        System.out.println("Eating");
    }
}
```

As [[Methods#Overloaded methods|overloaded methods]] exist there also exist overloaded constructors that are basically the same.
