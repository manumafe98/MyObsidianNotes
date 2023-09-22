
Print methods in [[Java]]

### print()

All the statements that you print with this method go in the same line.

```java
System.out.print("test");
System.out.print("test1");

// Output: testtest1
```


### println()

It's like having a \n on the end of the print

```java
System.out.println("Hello, World!");
System.out.println("testing");

// Output:
// Hello, World!
// testing
```

### printf()

An optional method to control, format, and display text to the console window.
It has two arguments = format string + object/variable/value
% [[Print methods#flags|[flags]]] [[Print methods#precision|[precision]]] [[Print methods#width|[width]]] [[Print methods#conversion-character|[conversion-character]]]

#### flags
adds an effect to output based on the flag added to the format specifier
``-`` : left-justify
``+`` : output a plus(+) or minus(-) sign for a numeric value
``0`` : numeric values are zero padded
``,`` : comma grouping separator if number > 1000

#### precision
sets number of digits of precision when outputting floating point values
```java
double myDouble = 3.14000;
System.out.printf("%.3f\n", myDouble);

// Ouput: 3.140
```

#### width
minimum number of characters to be written as output
```java
String myString = "Manu";
System.out.printf("Hello %10s\n", myString);

// Ouput: Hello       Manu
```

#### conversion-character
is proceed by a % and allows to use the variable formatted in the string

```java
boolean myBool = true;
int myInt = 50;
char myChar = '@';
String myString = "Manu";
double myDouble = 3.14000;

System.out.printf("%b", myBool);
System.out.printf("%d", myInt);
System.out.printf("%c", myChar);
System.out.printf("%s", myString);
System.out.printf("%f", myDouble);
```

