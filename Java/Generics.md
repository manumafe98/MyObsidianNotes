
Enables types ([[Python/Classes]] and [[Interfaces]]) to be parameters, when defining
- Classes
- Interfaces
- [[Methods]]
The benefit is to eliminate the need to create multiple versions of classes or methods for different [[Variables#Data Types|data types]]. So you can use the same one for all reference data types.

### Generic methods

Here is the way to define a generic method
```java
public static <T> void displayArray(T[] array) {
	for(T x : array) {
		System.out.print(x+" ");
	}
	System.out.println();
}
```

Then when you instantiate the different arrays with different data types
```java
Integer[] myInts = {1, 2, 3, 4};
String[] myStrings = {"hello", "world", "skere"};

displayArray(myInts);
displayArray(myStrings);
```

You still can print their content, without the need of making a ``displayArray`` for every array

And if you have a method that has a return you can create it like this.
```java
public static <T> T getFirst(T[] array) {
	return array[0];
}
```

Instead of  using void you use the same letter or word to capture the data type to return it.

### Generic classes

The ``<T>`` is what is going to capture the reference data type working as a wildcard, Instead of "T" you can use anything that you want but using "T" is like a convention.

```java
public class MyGenericClass<T> {
    T x;

    MyGenericClass(T x) {
        this.x = x;
    }
    public T getValue() {
        return x;
    }
}
```

Then in the instantiation of the object you define between the ``<>`` the reference data type.
```java
MyGenericClass<String> myString = new MyGenericClass<>("Hello");
MyGenericClass<Integer> myString = new MyGenericClass<>(1);
```

### Bounded Types

Is a way to "limit" the type of data types that you can pass to the generic.
For example you can create the objects of a generic class to have data of specific derived types. [Number](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Number.html) that is the parent of Integer, Double, etc.

```java
public class MyGenericClass<T extends Number> {
    T x;

    MyGenericClass(T x) {
        this.x = x;
    }
    public T getValue() {
        return x;
    }
}
```

So then when you instantiate the object you only be allowed to use ``Double``, ``Integer``, etc.
