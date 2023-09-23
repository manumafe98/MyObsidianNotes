
Array types in [[Java]]

### Array
- Have a fixed size, you have to specify the size in the creation
- Can store elements of primitive [[Variables#Data Types|data types]] as well as objects
- Elements can be accessed using index (faster)
- Less flexible when you want to resize
- ``length`` property
- don't work well with generics

#### How to create an Array

```java
String[] cars = { "Tesla", "Ferrari", "Lamborghini" };
String[] test = new String[3]; //this way you create it empty
int[] nums = { 1, 2, 3 };

// 2D Array
String[][] cars = new String[3][3];
```

- Array of [[OOP#Object|objects]], using as example a Food object.

```java
Food[] food = new Food[3];
// or
Food[] food = {food1, food2, food3};
```

### ArrayList
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

// Create a 2D ArrayList
ArrayList<ArrayList<String>> grocerylist = new ArrayList<ArrayList<String>>();
```
