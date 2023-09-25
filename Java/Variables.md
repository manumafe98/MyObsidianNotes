
Variables in [[Java]]

### How to use variables

```java
int x; // variable declaration
x = 123; //variable assignment

int y = 150; // initialization
```


### Data Types

![[Java_data_types.jpeg]]


### Switch variables

```java
String a = "water":
String b = "Coke";

String temp; // declare a temporary string

temp = a; // assign a to temp

// then switch the values
a = b;
b = temp;

System.out.println(w);
```


### Wrapper classes

They provide us a way to use primitive [[Variables#Data Types|data types]] as reference ones
- Pros: 
	- Reference data types contain useful methods
	- Can be used with collections (ex. [[Arrays#ArrayList|ArrayList]])
- Cons:
	- Are a lot slower than primitive

Some examples: 

| Primitive    | Wrapper   |
| ------------ | --------- |
| boolean      | Boolean   |
| char         | Character |
| int          | Integer   |
| double       | Double    |

``Autoboxing`` : the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes
``Unboxing`` : the reverse of autoboxing. Automatic conversion of wrapper class to primitive

```java
Boolean a = true; // autoboxing

if (a == true) {
	System.out.println("This is true");
} // unboxing, because treats the variable as if it is a primitive one

```

### Final keyword

When declaring variables, you then can update the value later in the code. If you precede the variable with the ``final`` keyword then it cannot be changed later in the code, a common practice is to declare the variable in all upper case.

```java
final double PI = 3.14159;
```

### Variable types

``Local`` : declared inside a method only visible to that method
``Global`` : declared outside the method visible to all parts of the class

```java
public class DiceRoller {

	// This are global
    Random random;
    int number = 0;

    DiceRoller() {
	    // Local
	    int x = 1;
        random = new Random();
    }

    void roll() {
        number = random.nextInt(6) + 1;
        System.out.println(number);
    }
}
```

You can also declare local variables and pass them to other methods through arguments.