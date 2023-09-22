
Some modules in [[Java]]

### Math

```java
int x = 3;
int y = 10;

Math.max(x, y);
Math.min(x, y);
Math.sqrt(y);
```

### Random

Generates pseudo random integers

| Random           | Pseudo-random |
| ---------------- | ------------- |
| true randomness  | deterministic |
| unpredictable    | periodicity   |
| non-reproducible | reproducible  |

Some simple tasks with the module and how to initiate it

```java
import java.util.Random; // First import the module outside the class

Random random = new Random(); // assign the random object to a random variable

int x = random.nextInt();
double y = random.nextDouble();
boolean z = random.nextBoolean();
```

Roll a six dice

```java
int u = random.nextInt(6) + 1; // does not include the 6 and starts with 0
```
