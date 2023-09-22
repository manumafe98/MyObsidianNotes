
How to ask for user input in [[Java]]

```java
import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) throws Exception {
        Scanner scanner = new Scanner(System.in);
        System.out.println("How is your name?");

        // then invoke a method of the variable and asign it to a string
        String name = scanner.nextLine();
        System.out.println("Hello " + name);

        // Good practice to always close the scanner
        scanner.close();
    }
}
```

``nextLine`` is for strings but there are many other methods like ``nextDouble``, ``nextInt``
