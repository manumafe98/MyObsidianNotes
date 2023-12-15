  
In [[Java]], a collection is a framework that provides classes and interfaces to store, manipulate, and organize groups of objects. Collections are essential for managing and working with data in various data structures efficiently.

One of the things about collections is that you can instantiate or declare the object with the [[Interfaces|interface]] as well as the concrete [[Classes|class]] type.

```java
import java.util.HashSet;
import java.util.Set;

public class Main {
	public static void main(String[] args) {
		Set<String> newSet = new HashSet<>();
	}
}
```

When you declare and instantiate a collection using the interface type (`List` or `Set`), you are following the principle of programming to an interface rather than an implementation. This is a fundamental concept in [[OOP]] that promotes loose coupling and flexibility in your code.

It allows you to easily switch the underlying implementation without affecting the rest of your code you can change from an `HashSet` to a `TreeSet`. This applies to every collection type.

### Hierarchy

![[Java_collections_hierarchy.png]]

### HashMap

Is a collection of key, value pairs in [[Java]] also named map or dictionary.

To use it first you have to import it
```java
java.util.HashMap;
```

Then instantiate the object.
It only works with [[Variables#Wrapper classes|reference data types]] as you can see between <>
```java
Hashmap<String, Integer> employees = new Hashmap<>();
```

#### Methods

``put()`` is used to add a element to our map or if the key exists update its value.
```java
employees.put("Jhon", 5341);
```

``get()`` is used to get the value of the passed key
```java
employees.get("Jhon");
```

``containsKey()`` to check if a certain key exists in the map, the output is a ``boolean``
```java
employees.containsKey("Jhon");
```

``containsValue()`` similar to ``containsKey`` but with the values
```java
employees.containsKey(5341);
```

``remove()`` removes the key from the map
```java
employees.remove("Jhon");
```

``replace()`` the difference between replace and put is that if the key does not exist replace do not add it to the map. If exists then updates the value
```java
employees.replace("Jhon", 333);
```

``putIfAbsent()`` Adds a certain key to the map only if does not exist, probably used to avoid updating the value of a key that already exists
```java
employees.putIfAbsent("Steve", 222);
```



### ArrayList

Some of the differences between an [[Array]] and a ArrayList
- Dynamic in size
- Can only store objects or reference data types
- You can access elements with ``.get(0)`` a method and index
- You can dynamically resize them
- ``size()`` method
- can work seamlessly with generics

#### how to create an ArrayList

```java
import java.util.ArrayList; // first you have to import them

ArrayList<String> food = new ArrayList<String>();

food.add("Pizza"); // Add the element to the arraylist

food.get(0) // get the element on that index
food.set(2, "Hotdog"); // with set you replace the value in the index 2 with the new one
food.remove(2); // remove the item in that index
food.clear(); // remove all items in the array

food.indexOf("Hotdog"); // Ouput 2, if the element does not exist -1
food.contains("Hotdog"); // Output true

// Create a 2D ArrayList
ArrayList<ArrayList<String>> grocerylist = new ArrayList<ArrayList<String>>();
```


### HashSet

Hashsets are a set implementation that use HashTables behind the scenes as it storage mechanism 

- Do not maintain the order of the elements like lists
- Do not allow duplicates
- Has almost the same elements of other implementation of a collection

Import statement
```java
import java.util.HashSet;
```

Instantiate the object
```java
HashSet<String> newSet = new HashSet<>();
```

One of the benefits that can bring you to implement sets is for example when you have a list that contains duplicates and you want to eliminate them, you can convert that list into a set.

```java
// The list contains [1, 2, 3, 2, 1]
List<Integer> newList = new ArrayList<>();
Set<Integer> newSet = new HashSet<>();

newSet.addAll(newList); // You can use this method for other collections aswell
// This allows you to copy the elements of the list to the set

// Ouput: [1, 2, 3]

// You can achieve the same behavoir doing
Set<Integer> newSet = new HashSet<>(newList);
```

### LinkedHashSet

Works pretty much the same as a HashSet but maintaining the order of insertion, at the cost of some performance
### TreeSet

Works pretty much the same as a HashSet but sorts the order of the elements in the set at the cost of performance.


### LinkedList

The LinkedList object in Java works as a ``Doubly Linked List``. Here you can see the pros and cons of the time/space complexity when used on [[Data Structures Time and Space Complexity#Operations|operations]] 

