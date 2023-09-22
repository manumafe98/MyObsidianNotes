
Loops in [[Java]]

### For Loop

```java
for (int i = 0; i <= 10; i++) {
	System.out.println(i);
}
```

### While Loop

```java
while (is_true) {
	counter++;
	if (counter > 5) {
		is_true = false;
	}
	System.out.println(counter);
}
```

### Do While Loop

```java
do {
	System.out.println("test");
} while (counter == 1);
```

Is essentially the same as the while loop but the block executes as least one time


### For Each

Traversing technique to iterate through the elements in an [[Arrays#Array|array]]/collection [[Arrays#ArrayList|(ArrayList)]] has less steps, it's more readable but less flexible.

```java
for (String animal : animals) { // the ":" is like and in
	System.out.println(animal);
}
```
