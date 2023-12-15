
is a module of [[Java]] that generates pseudo random integers.
To check more [java.util.Random](https://docs.oracle.com/javase/8/docs/api/java/util/Random.html)


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
// so adding 1 makes the roll between 1 and 6 inclusive
```

As you cannot add a minimum number parameter what you can do is identify the maximum number you want to roll and add the initial one.

For example I want to roll between 100 and 200(inclusive).

```java
return random.nextInt(101) + 100;
```

So if it rolls 0 the minimum would be 100 and if rolls 100 the maximum 200.