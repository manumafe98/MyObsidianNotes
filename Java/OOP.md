
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


#### Encapsulation

If when the attributes of the class are hidden or private, but can be accessed only through methods (getters & setters).
You should make attributes [[Access Modifiers#Private|private]] if you don't have a reason to make them public/protected

```java
public class Car {
	private int year:
	private String model;

	Car(int year, String model) {
		this.setYear(year);
		this.setModel(model);
	}
	
	public int getYear() {
		return year;
	}

	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public void setYear(int year) {
		this.year = year;
	}
}
```

So then you can access those attributes or set them only through [[Methods|methods]]


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


#### Polymorphism

The ability of an object to identify as more than one type

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


#### Dynamic Polymorphism

Dynamic: after compilation(during runtime).
You declare an object and make space for it in memory even if you don't know what type of object do you want.

```java
Animal animal;
```

And then after certain condition you initialize the animal with a certain subclass, example:

```java
animal = new Cat();
```


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
