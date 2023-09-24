They are like [[Java]] [[Keywords]] and add a layer of security to our programs.
To a better understanding of ``Access Modifiers`` check [[Packages]] and [[OOP#Classes|Classes]]

![[Java_access_modifiers.jpeg]]

So for this example we are going to use this structure

```css
src/
├── package1/
│   ├── A.java
│   └── B.java
└── package2/
    ├── C.java
    └── Asub.java
```

### Private

Only visible by the class that it contains the variable.

```java
package package1;
import package2.*;

public class B {
	private String privateMessage = "This is private";

	public static void main(String[] args) {
		B b = new B();
		System.out.println(b.privateMessage);
	}
}
```

### Public
Anything that is public is available or visible by other packages.

```java
package package2;
import package1.*;

public class C {
	public String publicMessage = "This is public";
}
```

This for example will be visible by all the files in our structure if C is instantiated.

### Protected
Can be accessed by classes in other packages if that class/classes are subclasses of where the protected [[Variables|variable]]/[[Methods|method]] is defined.

```java
package package1;
import package2.*;

public class A {
	protected String protectedMessage = "This is protected;
}
```

```java
package package2;
import package1.*;

public class Asub extends A{
	public static void main(String[] args) {
		
		Asub asub = new Asub();
		System.out.println(asub.protectedMessage());

		// Ouput = This is protected
	}
}
```

Works as well for other classes in the same package.


### No modifier or Default

```java
package package2;
import package1.*;

public class C {
	String defaultMessage = "This is default";
}
```

```java
package package1;
import package2.*;

public class A {
	public static void main(String[] args) {
		C c = new C();
		c.defaultMessage(); // This won't work without a modifier
	}
}
```

That's because variables and methods without modifier can be used within the same package or Class.
So if instead of trying to use it in ``A.java`` you try in ``Asub.java`` it will work correctly.