
Switch in [[Java]] is a statement that allows a variable to be tested for equality against a list of values so if statements are not ideal for this task and you should use switch instead.

```java
switch (day) {
	case "Sunday":
		System.out.println("It's Sunday");
		break;
	case "Monday":
		System.out.println("It's Monday");
		break;
	case "Tuesday":
		System.out.println("It's Tuesday");
		break;
	case "Wednesday":
		System.out.println("It's Wednesday");
		break;
	case "Thursday":
		System.out.println("It's Thursday");
		break;
	case "Friday":
		System.out.println("It's Friday");
		break;
	case "Saturday":
		System.out.println("It's Saturday");
		break;
	// Set a default value if no other values match
	default:
		System.out.println("That's not a day!");
}
```

In a switch you can use ``return`` statements to avoid the break, if comply with what the methods want to do.

Also you can define multiple cases that match the same result like this 
```java
switch (shirtNum) {
	case 5, 6:
		return "Midfielders",
}
```

And also use arrows like this
```java
switch (num) {
	case 1 -> return "one";
}
```

Or to avoid the repetition of ``return``
```java
return switch (num) {
	case 1 -> "one";
}
```
