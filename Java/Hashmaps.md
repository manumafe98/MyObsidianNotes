
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

### Methods

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
