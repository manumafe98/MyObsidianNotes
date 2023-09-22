
[[Java]] is an [[Java#Object Oriented|Object oriented Programming]] language.

A ``object`` is an instance of a class that may contain attributes and methods.

Here is an example of how to define an object and access it's methods and attributes
```java
Human human = new Human("elbananax", 25, 1.75);

System.out.println(human.name);
human.eat();
```

A ``constructor`` is a special method that is called when a method is instantiated

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
