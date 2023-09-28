
[[Java]] arrays

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
