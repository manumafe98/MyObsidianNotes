
In [[Java]] refers to the process of converting an [[Object|object]]'s state (its fields and data) into a byte stream, which can be easily stored in a file (``.ser``), transmitted over a network, or saved in a database.

To make the object serializable you have to import the ``Serializable`` [[Interfaces|interface]] and implement it to the class.
```java
import java.io.Serializable;

public class User implements Serializable {
	String name;
	String password;
}
```

This are the steps to serialize
```java
public class Main {
	public static void main(String[] args) {
		
		User user = new User();
		user.name = "Lionel";
        user.password = "Messi";

        FileOutputStream fileOut = new FileOutputStream("UserInfo.ser");
        ObjectOutputStream out = new ObjectOutputStream(fileOut);
        out.writeObject(user);
        out.close();
        fileOut.close();
	}
}
```

# Deserialization

The reverse process of converting a byte steam into an object.

First you have to create the object like a copy of the serialized one.
```java
import java.io.Serializable;

public class User implements Serializable {
	String name;
	String password;
}
```

Then make the following steps to ``deserialize``.
```java
public class Main {
	public static void main(String[] args) {
		
		User user = null;

        FileInputStream fileIn = new FileInputStream("PathToFile/file.ser");
        ObjectInputStream in = new ObjectInputStream(fileIn);
        user = (User) in.readObject();
        in.close();
        fileIn.close();
	}
}
```

Then if you print the values of ``name`` and ``password`` you would get the same as when you serialized the object.

# Notes

- Children classes of a parent class that implements ``Serializable`` will do so as well.
- Static fields are not serialized (they belong to the class, not an individual object)
- The class's definition ("class file") itself is not recorded, cast it as the object type
```java
// This is why you cast the class when invoking the readObject
user = (User) in.readObject();
```

- Fields declared as ``transient`` aren't serialized , they're ignored
- ``serialVersionUID`` is a unique version ID

### serialVersionUID

Is a unique ID that functions like a version number, verifies that the sender and receiver of a serialized object, have loaded classes for that object that match.
Ensures that the object will be compatible between machines.
The number must match, otherwise this will cause a ``InvalidClassException``.
The ``SerialVersionUID`` is calculated based on the class properties, members, etc.

To check the serial number
```java
long serialVersionUID = ObjectSteamClass.lookup(user.getClass()).getSerialVersionUID();
```


A serializable class can declare its own ``serialVersionUID`` explicitly. (recommended)
```java
import java.io.Serializable;

public class User implements Serializable {
	
	private static final long serialVersionUID = 1;
	String name;
	String password;
}
```
