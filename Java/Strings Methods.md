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

Checks the character at index 0
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
