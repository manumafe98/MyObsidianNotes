
Functional programming in [[Java]] [Official docs](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/package-summary.html)
The goal of using functional programming in Java is to write code that is more concise, maintainable, and less error-prone.

### Pure Functional Programming Rules

#### No State
This means that you should avoid changing the value of variables or objects once they are assigned. Instead, you should create new objects or variables with updated values.
```java
// Mutable state - Avoid this
int total = 0;
total += 5;

// Functional approach - Prefer this
int newTotal = add(5, total);
```

#### Pure Functions
A pure function is a function that always returns the same output for the same input and has no side effects. It doesn't modify any external state. Pure functions are deterministic and easy to test.
```java
// Impure function with side effect
int total = 0;
public int impureAdd(int x) {
    total += x; // Modifies external state
    return total;
}

// Pure function
public int pureAdd(int x, int y) {
    return x + y; // No side effects, same output for the same inputs
}
```

#### No Side Effects
Avoid side effects like modifying global variables, changing the state of objects, or performing I/O operations within your functions. Functions should only compute and return values.
```java
// Function with side effect
int globalCounter = 0;
public int incrementAndReturn() {
    globalCounter++; // Modifies global state
    return globalCounter;
}

// Function with no side effect
public int add(int x, int y) {
    return x + y; // No external state modification
}
```

#### Higher Order Functions
are functions that take other functions as arguments or return functions as results. They allow you to abstract over behavior and create more reusable code.
```java
// Higher order function that takes a function as an argument
public static int operate(int x, int y, IntBinaryOperator operation) {
    return operation.applyAsInt(x, y);
}

// Using the higher order function to add two numbers
int result = operate(5, 3, (a, b) -> a + b); // result is 8
```

### Functional interfaces 

A functional interface is an interface that contains only one abstract method.
It's often referred to as a "Single Abstract Method" (SAM) interface or a "functional interface" because it's designed to represent a single unit of behavior, typically a function or a lambda expression. Functional interfaces are a key concept in Java's support for functional programming and the use of lambda expressions.

You can create your own functional interfaces and it is recommended that you add the 
``@FunctionalInterface`` annotation to them so the compiler checks that you only have one method.
```java
@FunctionalInterface
public interface Consumer<T> {
    void accept(T t);
```

This interfaces only accept [[Variables#Data Types|reference data types]] because when using primitives you cannot pass null values.

#### Function
Represents a function that accepts one argument and produces a result.

This is what you normally would do in declarative programming
```java
public static int incrementByOne(int num) {
	return num + 1;
}
```

Instead with function.
```java
static Function<Integer, Integer> incrementByOneFunctions =
	num -> num + 1;
```

Then this is how you pass a value to both [[Methods]] 
```java
public static void main(String[] args) {

	System.out.println(incrementByOne(5));
	System.out.println(incrementByOneFunctions.apply(6));
}
```

There are useful method like ``andThen`` to chain functions.

##### BiFunction
is basically the same but it takes two arguments instead of one.

```java
static BiFunction<Integer, Integer, Integer> multiplyAndAddOne =
	(x, y) -> x * y + 1;
```

When multiply arguments are passed in functional programming there are inside parenthesis, then you apply it in the main method the same way as functions.

#### Consumer
Represents an operation that accepts a single input argument and returns no result.
`Consumer` is expected to operate via side-effects.

This is what you normally would do in declarative programming
```java
static void greetCustomer(Customer customer) {
	System.out.println("Hello "+customer.getCustomerName() + 
	", thanks for registering!");
}
```

But with Consumer you can do this instead
```java
static Consumer<Customer> greeConsumerByConsumer =
	customer -> System.out.println("Hello "+customer.getCustomerName() + 
	", thanks for registering!");
```

Then when you call this methods from the main function
```java
public static void main(String[] args) {

	greetCustomer(new Customer("Maria", "12345"));
	greeConsumerByConsumer.accept(new Customer("Ekko", "5555"));
}
```
For the consumer you use the ``accept`` method

##### BiConsumer
as well as [[Functional Programming#Function#Bifunction|BiFunction]] takes two parameters, but in this case as consumers do not return a value. 

#### Predicate
Represents a predicate (boolean-valued function) of one argument.

This is what you normally would do in declarative programming
```java
static boolean isValidPhoneNumber(String phoneNumber) {
	return phoneNumber.startsWith("07") && phoneNumber.length() == 11;
}
```

But with Predicate you can do this instead
```java
static Predicate<String> isValidPhoneNumberPredicate =
	phoneNumber -> phoneNumber.startsWith("07") && phoneNumber.length() == 11;
```

Then when you call this methods from the main function
```java
public static void main(String[] args) {

	System.out.println(isValidPhoneNumberPredicate.test("07000000000"));
	System.out.println(isValidPhoneNumber("07000000000"));
}
```
For the Predicate you use the ``test`` method

#### Supplier
Represents a supplier of results.
There is no requirement that a new or distinct result be returned each time the supplier is invoked.

This is what you normally would do in declarative programming
```java
static String getDbConnection() {
	return "pgsql://localhost:5432/users";
}
```

But with Suppliers you can do the same like this instead
```java
static Supplier<String> getDbConnectionSupplier =
	() -> "pgsql://localhost:5432/users";
```

Then when you call this methods from the main function
```java
public static void main(String[] args) {

	System.out.println(getDbConnectionSupplier.get());
	System.out.println(getDbConnection());
}
```
For the Supplier you use the ``get`` method.


### Streams
### Lambdas

