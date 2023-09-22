
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


