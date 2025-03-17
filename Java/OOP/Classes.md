
The primary object-oriented construct in [[Java]] is the _class_, which is a combination of data ``fields`` and behavior ``methods``. The fields and methods of a class are known as its _members_.

### Inheritance

is a mechanism in which one object acquires all the properties and behaviors of a parent object. It is an important part of  Object Oriented programming system.


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

### Method overriding

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


### Encapsulation

Is when the attributes of the class are hidden or private, but can be accessed only through methods (getters & setters).
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