
[[Java]] arrays are a type of [[Collections]]

- Have a fixed size, you have to specify the size in the creation
- Can store elements of primitive [[Variables#Data Types|data types]] as well as objects
- Elements can be accessed using index (faster)
- Less flexible when you want to resize
- ``length`` property
- don't work well with generics

### How to create an Array

```java
String[] cars = { "Tesla", "Ferrari", "Lamborghini" };
String[] test = new String[3]; //this way you create it empty
// the number is the amount of items that holds the array not the last index

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

### Convert an array into a list

```java
String[] arr = {"1", "2", "3"};

List<String> list = Arrays.asList(arr);
```

This could be useful cause collections has different methods, depending on the situation.