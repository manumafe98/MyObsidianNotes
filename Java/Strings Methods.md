Some Strings methods in [[Java]]

Checks for equality against a variable and outputs a ``boolean``
```java
String name = "Manuel";

boolean result = name.equals("Manuel");
System.out.println(result);
```

Outputs the length of the [[Variables|variable]]
```java
int total_chars = name.length();
System.out.println(total_chars);
```

#### charAt()

Check for characters at a certain index like a[0] in python
```java
char what_char_at = name.charAt(0);
System.out.println(what_char_at);
```

Checks at what index is the letter "a"
```java
int where_char = name.indexOf("a");
System.out.println(where_char);
```

Check if the variable is empty
```java
boolean is_empty = name.isEmpty();
System.out.println(is_empty);
```

Convert the string into uppercase
```java
String uppercase = name.toUpperCase();
System.out.println(uppercase);
```

Convert the string into lowercase
```java
String lowercase = name.toLowerCase();
System.out.println(lowercase);
```

Eliminates blank spaces before and after the chars like strip in [[Python]]
```java
String non_blank = name.trim();
System.out.println(non_blank);
```

Replaces the char o set of chars for a new value
```java
String new_name = name.replace("el", "");
System.out.println(new_name);
```

#### substring()

Takes two parameters, the beginning index and end index.
```java
String name = "manuel";
String firstLetter = name.substring(0, 1);

// Output = m
```

This for example could be useful to capitalize a name

```java
String name = "manuel";
String firstLetter = name.substring(0, 1).toUppercase();

System.out.println(firstLetter + name.substring(1))

// Ouput = Manuel
```

If you don't specify a end index would take all the string to the end.

#### compareTo()

This method is useful to compare two strings lexicographically (That means who comes first), for example apple < banana, apple is smaller cause the a comes after the b in the dictionary.

This is an example usage of ``compareTo`` 

```java
String apple = "apple";
String banana = "banana";

if (apple.compareTo(banana) < 0) {
	System.out.println("Apple is smaller");
} else if (apple.comapreTo(banana) > 0) {
	System.out.println("Apple is bigger");
}
```

#### split()

Split is a string method that splits the string into a [[Array]] of strings depending on the given the regular expression that you passed as parameters.

```java
String test = "we are testing";
String [] = test.split(" ");

// Output: {"we", "are", "testing"}
```

#### join()

Join an [[Array]] into a String.

```java
String[] strArr = {"A", "B", "C"};
System.out.println(String.join(" ", strArr));

// Ouput: A B C (as a String)
```


#### StringBuilder

it has some other methods, like `append` and ``reverse`` that are pretty useful 

```java
import java.lang.StringBuilder;

StringBuilder str = new StringBuilder("string");
````

