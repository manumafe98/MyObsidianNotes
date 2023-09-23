
Methods in [[Java]] are a block of code that is executed whenever is called upon (Functions in [[Python]])

Main method, here I'm calling the example methods.
```java
public static void main(String[] args) throws Exception {
	
	hello("Manuel", 25); // Calling hello method
	System.out.println(sum(5, 10));
	
	int x = add(1, 2); // Assign the value of add method to x
	System.out.println(x);
	
	double z = add(1.0, 2.0);
	System.out.println(z);
}
```


We precede the method with static because we are calling it from a static method if that's not the case with ``void hello(){}`` would be enough.
```java
static void hello(String name, int age) {
	System.out.println("Hello " + name);
	System.out.println("You are " + age);
}
```

When you have a return you have to specify the data type so that's why is ``static int`` instead of ``static void``.
```java
static int sum(int x, int y) {
	int total_sum = x + y;
	return total_sum;
}
```

#### Overloaded methods

Are methods that share the same name but have different parameters, could vary the amount of parameters, the [[Variables#Data Types|data type]] of them or even the order.
``method name + parameters = method signature``

```java
static int add(int a, int b) {
	System.out.println("Overloaded method 1");
	return a + b;
}

static int add(int a, int b, int c) {
	System.out.println("Overloaded method 2");
	return a + b + c;
}

static double add(double a, double b) {
	System.out.println("Overloaded method 3");
	return a + b;
}
```
