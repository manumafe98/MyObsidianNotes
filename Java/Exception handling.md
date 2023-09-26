
Exception handling in [[Java]] is an event during the execution of a program that disrupts the normal flow of instructions 

```java
int[] nums = { 1, 2, 3 };

try {
	int x = nums[3];
	System.out.println(x);
	} catch (ArrayIndexOutOfBoundsException e) {
		System.out.println("Index is out of bounds");
	} catch (Exception e) {
		// Used mainly to catch exception that you may not know can happen
		// is good practice to use the specific exception otherwise
		System.out.println("Something went wrong");
	} finally {
		// Good practice is to close sessions, scanners or files
		System.out.println("This will always print");
	}
```

### Throw

The ``throw`` [[Keywords|keyword]] allow you to create a custom error.
The throw statement is used together with an exception type.

```java
public class Main {
  static void checkAge(int age) {
    if (age < 18) {
      throw new ArithmeticException("Access denied - You must be at least 18 years old.");
    }
    else {
      System.out.println("Access granted - You are old enough!");
    }
  }

  public static void main(String[] args) {
    checkAge(15); // Set age to 15 (which is below 18...)
  }
}
```
