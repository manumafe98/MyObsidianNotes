
File management in [[Java]].
An abstract representation of file and directory path names.

### File

First you have to import the module
```java
import java.io.File;
```

Then instantiate the object 
```java
File file = new File("test.txt");
```

#### Useful methods 

```java
file.exists(); // Checks if the file exists
```

```java
file.getAbsolutePath(); // Get's the absolute full path

// Ouput: E:\Java Projects\LearningJava\src\FilesJavaFolder\test.txt
```

```java
// Displays true or false if is a file, can be useful to detect directories
file.isFile();
```

```java
file.getPath(); // Get's the path that you defined in the object

// Output: test.txt
```

```java
file.delete(); // deletes the file
```


### FileWriter

Necessary imports to use FileWriter
```java
import java.io.FileWriter;
import java.io.IOException;
```

```java
FileWriter writer = new FileWriter("poem.txt");

try {
	writer.write("Roses are red"); //Overrites what you have currently
	writer.append("Violets are blue"); //Appends to what you have
} catch (IOException e) {
	e.printStackTrace();
} finally {
	writer.close();
}
```


### FileReader

Reads the contents of a file as a stream of characters. 
One by one ``read()`` returns an ``int`` value which contains the byte value.
When ``read()`` returns -1, there is no more data to be read

```java
import java.io.FileReader;
import java.io.IOException;
import java.io.FileNotFoundException;
```

```java
try {
	FileReader reader = new FileReader("test.txt");
	int data = reader.read();
	
	while (data != -1) {
		System.out.print(data);
		data = reader.read();
	}
	reader.close();

} catch(FileNotFoundException e) {
	e.printStackTrace();
} catch(IOException e) {
	e.printStackTrace();
}
```

