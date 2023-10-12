
A record in [[Java]] is a type of [[OOP#Classes|class]] that allows you to reduce boilerplate code.

For example this will be your implementation of a class if you want to achieve the same functionality of a record

```java
public class Car {
    private final String model;
    private final int year;

    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }


    @Override
    public String toString() {
        return "Car [model=" + model + ", year=" + year + "]";
    }

    @Override
    public int hashCode() {
        final int prime = 31;
        int result = 1;
        result = prime * result + ((model == null) ? 0 : model.hashCode());
        result = prime * result + year;
        return result;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        Car other = (Car) obj;
        if (model == null) {
            if (other.model != null)
                return false;
        } else if (!model.equals(other.model))
            return false;
        if (year != other.year)
            return false;
        return true;
    }
}
```

And this is the implementation with record instead

```java
public record CarRecord(String model, int year){}
```

For records Java creates this canonical [[OOP#Constructor|constructor]] in the background, setting the fields based on the components that you passed for the record.

```java
public Car(String model, int year) {
	this.model = model;
	this.year = year;
}
```

You can override this constructor with your own implementation, maybe to test that the year that is passed cannot be negative.


Records do not implement ``setter methods`` one of the main features of records is that they are immutable by default.
Also they can't inherit another class, but they can implement an [[Interfaces|interface]].
As any other class they can implement instance methods, and also static methods.
You can define your own [[Keywords#Static|static]] fields, but you can't define non static fields, you have to define them in your instance components ``(String model, int year, etc)`` 

```java
public record CarRecord(String model, int year){
	// static field
	public static final String DEFAULT_CAR_MODEL = "Tesla";

	// Instance methods
	public String modelInUppercase() {
		return model.toUppercase();
	}
}

// Static methods
public static void printWhatever(){
	System.out.println("Whatever")
}
```

Records are implicitly [[Variables#Final keyword|final]] 