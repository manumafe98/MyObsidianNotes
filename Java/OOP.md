
[[Java]] is an [[Java#Object Oriented|Object oriented Programming]] language.

### Classes

#### Inheritance

We create a parent class
```java
public class Vehicle {
	double speed;

	void go() {
		System.out.println("This vehicle is moving");
	}
}
```

Then extend the child class with the parent that's called a ``Subclass``
```java
public class Car extends Vehicle {
	
}
```

And when we define a new car object we will see all the parent class methods and attributes inherited.
```java
Car car = new Car();
car.go();
```

#### method overriding

Declaring a method in a sub class, which is already present in a parent class, this is done so the child class can give its own implementation.

```java
public class Animal {
	void speak() {
		System.out.println("The animal speaks");
	}
}

public class Dog extends Animal{
	@Override  // this is a annotation, does nothing but is good practice
	void speak() {
		System.out.println("The dog goes *bark*")
	}
}
```


### Object

A ``object`` is an instance of a class that may contain attributes and methods.

Here is an example of how to define an object and access it's methods and attributes
```java
Human human = new Human("elbananax", 25, 1.75);

System.out.println(human.name);
human.eat();
```

#### toString()

A special method that all object inherit, that returns a string that "textually represent" an object. Can be used ``implicitly`` and ``explicitly``

```java
DiceRoller diceroller = new DiceRoller();
System.out.println(diceroller); // implicitly
System.out.println(diceroller.toString()); // explicitly


// Output: DiceRoller@23fc625e 
```

``DiceRoller@23fc625e`` is the address of the object ``DiceRoller`` in memory

Sometimes for ``toString()`` is applied what's called [[OOP#Classes#method overriding|method overriding]] 
That means that you create the method ``toString()`` to display the attributes of the object itself, instead of the address in memory.


### Constructor

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
