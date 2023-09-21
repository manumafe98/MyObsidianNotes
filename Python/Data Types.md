is an attribute of a variable that determines the type of data it can hold. It tells the computer how to interpret the value stored in the variable and what operations can be performed on it.

[[Python]] has some built-in data types:
-   Numbers: integers, floats, and complex numbers
-   Booleans: True and False
-   Strings: sequences of characters
-   Lists: ordered collections of values 
	```python
	my_list = [1, 2, "hello"]
	```
-   Tuples: immutable ordered collections of values
	```python
	my_typle = (1, 2, 3)
	```
-   Sets: unordered collections of unique values
	```python
	my_set = {1, 2, 3}
	```
-   Dictionaries: unordered collections of key-value pairs
	```python
	my_dict = {"a": 1, "b": 2, "c": 3}
	```
-   None: a special object representing absence of a value

You have two types of data types, the mutable ones and the immutable, that means that when you create a variable for example:
``` python
x = 1
# Even if you re asign the variable the object 1 is created and never would be changed
# But in the other hand if you do this
array = []
# You can later add content to it because is mutable
```

#### Immutable
- Numbers
- Strings
- Tuples
- Frozen sets

#### mutable
- Arrays
- Sets
- Dictionaries